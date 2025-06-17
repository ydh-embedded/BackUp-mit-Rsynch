# Manjaro Backup bootfähig machen - Komplette Anleitung

## Voraussetzungen
- Manjaro rsync-Backup auf USB-Stick "BackUp-Manjaro" (`/dev/sda1`)
- Ziel-Festplatte in Dockingstation (`/dev/sdb`)
- USB-Stick gemountet unter `/run/media/y/BackUp-Manjaro/`

## 1. Ziel-Festplatte partitionieren

### Partitionierung mit fdisk
```bash
sudo fdisk /dev/sdb
```

**In fdisk eingeben:**
1. `d` (bestehende Partitionen löschen, falls vorhanden)
2. `n` (neue Partition 1)
3. `Enter` (Partition 1)
4. `Enter` (Standard Startsektor)
5. `+500M` (EFI-Partition 500MB)
6. `t` → `1` (EFI System Type)
7. `n` (neue Partition 2)
8. `Enter` (Partition 2)
9. `Enter` (Standard Startsektor)
10. `Enter` (Rest der Platte)
11. `w` (schreiben und beenden)

### Partitionierung überprüfen
```bash
lsblk /dev/sdb
```
**Ergebnis sollte sein:**
- `sdb1` (500M) - EFI-Partition
- `sdb2` (931G) - Root-Partition

## 2. Partitionen formatieren

```bash
# EFI-Partition formatieren
sudo mkfs.fat -F32 /dev/sdb1

# Root-Partition formatieren
sudo mkfs.ext4 /dev/sdb2
```

## 3. Mount-Struktur vorbereiten

```bash
# Mount-Punkte erstellen
sudo mkdir -p /mnt/restore
sudo mount /dev/sdb2 /mnt/restore
sudo mkdir -p /mnt/restore/boot/efi
sudo mount /dev/sdb1 /mnt/restore/boot/efi
```

## 4. Backup-Verzeichnis prüfen

```bash
# Backup-Inhalt anzeigen
ls -la /run/media/y/BackUp-Manjaro/
```

## 5. System kopieren

```bash
# Komplettes Backup auf neue Festplatte kopieren
# (Verzeichnisname entsprechend anpassen)
sudo rsync -aAXv --progress /run/media/y/BackUp-Manjaro/manjaro-backup-20250616/. /mnt/restore/
```

**⏱️ Hinweis:** Das Kopieren dauert ca. 20-30 Minuten (38GB Daten)

## 6. Bootloader installieren

```bash

# /dev, /proc, /sys ins chroot mounten
sudo mount --bind /dev /mnt/restore/dev
sudo mount --bind /proc /mnt/restore/proc
sudo mount --bind /sys /mnt/restore/sys

# In das neue System wechseln (chroot)
sudo chroot /mnt/restore

# Grub-Bootloader installieren
grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=Manjaro
grub-mkconfig -o /boot/grub/grub.cfg

# Prüfen ob EFI-Partition gemountet ist
mount | grep efi
ls -la /boot/efi

# Grub-Bootloader installieren
grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=Manjaro
grub-mkconfig -o /boot/grub/grub.cfg


# Chroot verlassen
exit


# Alle Mounts unmounten
sudo umount /mnt/restore/dev
sudo umount /mnt/restore/proc
sudo umount /mnt/restore/sys
sudo umount /mnt/restore/boot/efi
sudo umount /mnt/restore

# Alternativ -> Ohne chroot direkt installieren
sudo grub-install --target=x86_64-efi --efi-directory=/mnt/restore/boot/efi --bootloader-id=Manjaro --boot-directory=/mnt/restore/boot

```

## 7. fstab korrigieren

```bash
# Neue fstab generieren (wichtig für UUIDs)
sudo genfstab -U /mnt/restore > /mnt/restore/etc/fstab

# Kontrolle der fstab
cat /mnt/restore/etc/fstab
```

## 8. System sauber unmounten

```bash
# Alle Mount-Punkte unmounten
sudo umount /mnt/restore/boot/efi
sudo umount /mnt/restore
```

## Check - Grub 
```
### a. Partitionen mounten
```bash
# Root-Partition mounten
sudo mkdir -p /mnt/restore
sudo mount /dev/sdb2 /mnt/restore
```

# EFI-Partition mounten
sudo mkdir -p /mnt/restore/boot/efi
sudo mount /dev/sdb1 /mnt/restore/boot/efi
### b. Mount-Status überprüfen
```bash
# Prüfen ob alles richtig gemountet ist
mount | grep sdb
df -h | grep sdb
```
### c. Jetzt die Checks durchführen
```bash
# EFI-Bootloader-Eintrag prüfen
sudo efibootmgr -v
```

```bash
# EFI-Dateien überprüfen
ls -la /mnt/restore/boot/efi/EFI/
ls -la /mnt/restore/boot/efi/EFI/Manjaro/
```
```bash
# GRUB-Konfiguration prüfen
ls -la /mnt/restore/boot/grub/grub.cfg
head -20 /mnt/restore/boot/grub/grub.cfg
```

### d. Nach den Checks wieder unmounten
```bash
sudo umount /mnt/restore/boot/efi
sudo umount /mnt/restore
```
✅ GRUB Installation erfolgreich:

EFI-Bootloader-Eintrag "Manjaro" ist vorhanden (Boot0001)
grubx64.efi existiert in /EFI/Manjaro/
grub.cfg ist erstellt

```bash
# fstab prüfen
cat /mnt/restore/etc/fstab
```
❌ Problem: fstab ist veraltet!
Die fstab zeigt noch die alten UUIDs vom ursprünglichen System. Das muss korrigiert werden:
1. Aktuelle UUIDs der neuen Festplatte ermitteln
```bash
# UUIDs der neuen Partitionen anzeigen
sudo blkid /dev/sdb1 /dev/sdb2
```
2. Neue fstab generieren

```bash
# Alte fstab als Backup
sudo cp /mnt/restore/etc/fstab /mnt/restore/etc/fstab.backup
```

# Neue fstab mit korrekten UUIDs generieren
```bash
sudo genfstab -U /mnt/restore > /tmp/new_fstab
sudo cp /tmp/new_fstab /mnt/restore/etc/fstab
```
3. Neue fstab überprüfen
```bash
cat /mnt/restore/etc/fstab
```
4. GRUB-Config mit neuen UUIDs aktualisieren
```bash
# In chroot gehen um GRUB-Config zu erneuern
sudo                    chroot /mnt/restore
grub-mkconfig -o /boot/grub/grub.cfg
exit
```

Die UUIDs in der fstab müssen zu deinen neuen Partitionen 
/dev/sdb1 und /dev/sdb2 passen, sonst bootet das System nicht!

Führe zuerst
```ps
 sudo blkid /dev/sdb1 /dev/sdb2
```


## 9. Test

1. Festplatte in Zielrechner einbauen
2. Von der neuen Festplatte booten
3. System sollte normal starten

## Fehlerbehebung

### Falls Boot nicht funktioniert:
```bash
# Von Live-USB booten und chroot wiederholen
sudo mount /dev/sdb2 /mnt
sudo mount /dev/sdb1 /mnt/boot/efi
sudo arch-chroot /mnt
grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=Manjaro
grub-mkconfig -o /boot/grub/grub.cfg
exit
```

### Partitionen erweitern (falls Ziel-Festplatte größer):
```bash
# Nach erfolgreichem Boot
sudo growpart /dev/sdb 2
sudo resize2fs /dev/sdb2
```

## Wichtige Hinweise

- ⚠️ Alle Daten auf der Ziel-Festplatte werden überschrieben!
- 💾 Das originale Backup bleibt auf dem USB-Stick erhalten
- 🔄 Regelmäßige Backups empfohlen mit rsync --delete für Updates
- 📋 Notiere dir die UUID der neuen Partitionen für spätere Referenz