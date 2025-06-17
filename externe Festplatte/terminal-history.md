```bash
sent 34.608.811.498 bytes  received 11.458.642 bytes  52.976.694,93 bytes/sec
total size is 34.554.497.637  speedup is 1,00
[y@y-L10111 ~]$
# In das neue System wechseln (chroot)
sudo arch-chroot /mnt/restore

# Grub-Bootloader installieren
grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=Manjaro
grub-mkconfig -o /boot/grub/grub.cfg
[sudo] Passwort für y: 
sudo: arch-chroot: Befehl nicht gefunden
x86_64-efi wird für Ihre Plattform installiert.
grub-install: Warnung: Platte existiert nicht, ersatzweise wird Partition des Geräts /dev/nvme0n1p1 verwendet.
grub-install: Warnung: Platte existiert nicht, ersatzweise wird Partition des Geräts /dev/nvme0n1p1 verwendet.
grub-install: Warnung: Platte existiert nicht, ersatzweise wird Partition des Geräts /dev/nvme0n1p1 verwendet.
grub-install: Fehler: Laufwerk »hostdisk//dev/nvme0n1p1« wurde nicht gefunden..
grub-mkconfig: Sie müssen dies als als root ausführen
[y@y-L10111 ~]$
# In das neue System wechseln (chroot)
sudo arch-chroot /mnt/restore
sudo: arch-chroot: Befehl nicht gefunden
[y@y-L10111 ~]$
 ls --progress
ls: Unbekannte Option »--progress«
„ls --help“ liefert weitere Informationen.
[y@y-L10111 ~]$
 ls -la --progress
ls: Unbekannte Option »--progress«
„ls --help“ liefert weitere Informationen.
[y@y-L10111 ~]$
 ls -la --progressls -la
ls: Unbekannte Option »--progressls«
„ls --help“ liefert weitere Informationen.
[y@y-L10111 ~]$
 ls -la
insgesamt 208
drwx------ 30 y    y     4096 16. Jun 22:17 .
drwxr-xr-x  3 root root  4096 14. Feb 17:44 ..
drwxr-xr-x  6 y    y     4096 16. Jun 14:58 .anydesk
-rw-------  1 y    y    11363 16. Jun 22:17 .bash_history
-rw-------  1 y    y        0 16. Jun 20:03 .bash_history-03062.tmp
-rw-------  1 y    y    11660 16. Jun 13:01 .bash_history-45657.tmp
-rw-r--r--  1 y    y       21 29. Sep 2024  .bash_logout
-rw-r--r--  1 y    y       57 29. Sep 2024  .bash_profile
-rw-r--r--  1 y    y     3467  9. Mär 19:37 .bashrc
drwxr-xr-x  3 y    y     4096 23. Feb 20:42 Bilder
drwx------ 27 y    y     4096 14. Mai 23:16 .cache
drwxr-xr-x  5 y    y     4096 11. Apr 19:51 .cargo
drwxr-xr-x 28 y    y     4096 16. Jun 20:00 .config
drwxr-xr-x  2 y    y     4096 11. Apr 19:42 .dart-tool
-rw-r--r--  1 y    y     4855 30. Jun 2024  .dir_colors
drwxr-xr-x  4 y    y     4096  1. Mär 17:37 Dokumente
drwxr-xr-x  3 y    y     4096 16. Feb 19:07 .dotnet
drwxr-xr-x  4 y    y     4096 16. Jun 14:32 Downloads
-rw-r--r--  1 y    y       78 11. Apr 19:43 .flutter
-rw-r--r--  1 y    y       86  1. Mär 19:27 .gitconfig
drwx------  3 y    y     4096 14. Feb 20:18 .gnupg
drwxr-xr-x  2 y    y     4096 14. Mai 22:45 .gphoto
drwxr-xr-x  4 y    y     4096 14. Feb 17:46 .local
drwx------  4 y    y     4096 14. Feb 20:19 .mozilla
drwxr-xr-x  2 y    y     4096 14. Feb 17:46 Musik
drwxr-xr-x  4 y    y     4096  9. Mär 19:43 .npm
drwxr-xr-x  8 y    y     4096  9. Mär 19:39 .nvm
drwxr-xr-x  2 y    y     4096 14. Feb 17:46 Öffentlich
drwx------  3 y    y     4096 14. Feb 20:41 .pki
-rw-r--r--  1 y    y     4212 24. Apr 11:44 plakette.pdf
drwxr-xr-x  7 y    y     4096 11. Apr 19:43 .pub-cache
drwxr-xr-x  2 y    y     4096 14. Feb 17:46 Schreibtisch
drwx------  2 y    y     4096 15. Feb 16:44 .snap
drwx------  5 y    y     4096 13. Mär 18:59 snap
drwx------  2 y    y     4096 23. Mai 17:35 .ssh
-rw-------  1 y    y      399 23. Mai 17:08 ssh
-rw-r--r--  1 y    y       92 23. Mai 17:08 ssh.pub
-rw-------  1 y    y      399 23. Mai 17:05 ssh-public-key-github
-rw-r--r--  1 y    y       92 23. Mai 17:05 ssh-public-key-github.pub
drwx------  4 y    y     4096 30. Apr 18:25 .thunderbird
drwxr-xr-x  3 y    y     4096 16. Jun 13:23 Videos
drwxr-xr-x  2 y    y     4096 14. Feb 17:46 Vorlagen
drwxr-xr-x  4 y    y     4096 16. Feb 16:30 .vscode
-rwxr-xr-x  1 y    y      100 30. Jun 2024  .Xclients
-rwxr-xr-x  1 y    y     1521  4. Dez 2024  .xinitrc
drwxr-xr-x  5 y    y     4096 22. Feb 16:56 yay
-rw-r--r--  1 y    y      382 25. Jul 2023  .zshrc
[y@y-L10111 ~]$ 
# Backup-Inhalt anzeigen
ls -la /run/media/y/BackUp-Manjaro/
insgesamt 28
drwx------   5 y    y     4096 16. Jun 21:37 .
drwxr-x---+  4 root root    80 17. Jun 10:59 ..
drwx------   2 root root 16384 16. Jun 21:23 lost+found
drwxr-xr-x  16 root root  4096  3. Jun 20:54 manjaro-backup-20250616
drwxr-xr-x   3 root root  4096 16. Jun 21:34 timeshift
[y@y-L10111 ~]$ 
sudo arch-chroot /mnt/sdb
sudo: arch-chroot: Befehl nicht gefunden
[y@y-L10111 ~]$ 
sudo chroot /mnt/restore
[y-L10111 /]
# Grub-Bootloader installieren
grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=Manjaro
grub-mkconfig -o /boot/grub/grub.cfg
x86_64-efi wird für Ihre Plattform installiert.
grub-install: Fehler: Gerät für /boot/efi konnte nicht gefunden werden (ist /dev eingehängt?).
/usr/bin/grub-probe: Fehler: Gerät für / konnte nicht gefunden werden (ist /dev eingehängt?).
[y-L10111 /]
# exit
exit
[y@y-L10111 ~]$ 
# /dev, /proc, /sys ins chroot mounten
sudo mount --bind /dev /mnt/restore/dev
sudo mount --bind /proc /mnt/restore/proc
sudo mount --bind /sys /mnt/restore/sys
[y@y-L10111 ~]$ sudo chroot /mnt/restore
[y-L10111 /]
 # Prüfen ob EFI-Partition gemountet ist
mount | grep efi
ls -la /boot/efi
/dev/sdb1 on /boot/efi type vfat (rw,relatime,fmask=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,utf8,errors=remount-ro)
insgesamt 432
drwxr-xr-x  5 root root   4096  1. Jan 1970   .
drwxr-xr-x  5 root root   4096 20. Mai 14:58  ..
drwxr-xr-x 41 root root   4096  1. Sep 2021   Boot
-rwxr-xr-x  1 root root 413712 20. Apr 2020   bootmgr
-rwxr-xr-x  1 root root      1  7. Dez 2019   BOOTNXT
drwxr-xr-x  6 root root   4096 30. Okt 2024   EFI
drwxr-xr-x  2 root root   4096  1. Sep 2021  'System Volume Information'
[y-L10111 /]
# Grub-Bootloader installieren
grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=Manjaro
grub-mkconfig -o /boot/grub/grub.cfg
x86_64-efi wird für Ihre Plattform installiert.
EFI variables are not supported on this system.
EFI variables are not supported on this system.
grub-install: Fehler: efibootmgr schlug beim Registrieren des Boot-Eintrags fehl: Datei oder Verzeichnis nicht gefunden.
GRUB-Konfigurationsdatei wird erstellt …
Thema gefunden: /usr/share/grub/themes/manjaro/theme.txt
Linux-Abbild gefunden: /boot/vmlinuz-6.12-x86_64
Initrd-Abbild gefunden: /boot/intel-ucode.img /boot/amd-ucode.img /boot/initramfs-6.12-x86_64.img
Found initrd fallback image: /boot/initramfs-6.12-x86_64-fallback.img
Warnung: Zur Erkennung anderer bootfähiger Partitionen wird os-prober ausgeführt.
Dessen Ausgabe wird zur Erkennung bootfähiger Programmdateien und Erzeugen neuer Boot-Einträge verwendet.
ERROR: mkdir /var/lock/dmraid
Manjaro Linux (25.0.3) auf /dev/nvme0n1p5 gefunden
Bootmenü-Eintrag für UEFI-Firmware-Einstellungen wird hinzugefügt …
Root filesystem isn't btrfs
If you think an error has occurred, please file a bug report at "https://github.com/Antynea/grub-btrfs"
Found memtest86+ image: /boot/memtest86+/memtest.bin
Found memtest86+ EFI image: /boot/memtest86+/memtest.efi
abgeschlossen


[y@y-L10111 ~]$ # EFI-Partition Inhalt prüfen
ls -la /mnt/restore/boot/efi/EFI/
ls -la /mnt/restore/boot/efi/EFI/Manjaro/
ls: Zugriff auf '/mnt/restore/boot/efi/EFI/' nicht möglich: Datei oder Verzeichnis nicht gefunden
ls: Zugriff auf '/mnt/restore/boot/efi/EFI/Manjaro/' nicht möglich: Datei oder Verzeichnis nicht gefunden
[y@y-L10111 ~]$ # Mount-Status
mount | grep -E "(sdb1|sdb2)"

# Alle wichtigen Dateien prüfen
ls -la /mnt/restore/boot/efi/EFI/Manjaro/grubx64.efi
ls -la /mnt/restore/boot/grub/grub.cfg
ls -la /mnt/restore/etc/fstab
ls: Zugriff auf '/mnt/restore/boot/efi/EFI/Manjaro/grubx64.efi' nicht möglich: Datei oder Verzeichnis nicht gefunden
ls: Zugriff auf '/mnt/restore/boot/grub/grub.cfg' nicht möglich: Datei oder Verzeichnis nicht gefunden
ls: Zugriff auf '/mnt/restore/etc/fstab' nicht möglich: Datei oder Verzeichnis nicht gefunden
[y@y-L10111 ~]$ # Root-Partition mounten
sudo mkdir -p /mnt/restore
sudo mount /dev/sdb2 /mnt/restore

# EFI-Partition mounten
sudo mkdir -p /mnt/restore/boot/efi
sudo mount /dev/sdb1 /mnt/restore/boot/efi
[sudo] Passwort für y: 
[y@y-L10111 ~]$ # Prüfen ob alles richtig gemountet ist
mount | grep sdb
df -h | grep sdb
/dev/sdb2 on /mnt/restore type ext4 (rw,relatime)
/dev/sdb1 on /mnt/restore/boot/efi type vfat (rw,relatime,fmask=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,utf8,errors=remount-ro)
/dev/sdb2       916G     34G  836G    4% /mnt/restore
/dev/sdb1       499M     47M  453M   10% /mnt/restore/boot/efi
[y@y-L10111 ~]$ # EFI-Bootloader-Eintrag prüfen
sudo efibootmgr -v

# EFI-Dateien überprüfen
ls -la /mnt/restore/boot/efi/EFI/
ls -la /mnt/restore/boot/efi/EFI/Manjaro/

# GRUB-Konfiguration prüfen
ls -la /mnt/restore/boot/grub/grub.cfg
head -20 /mnt/restore/boot/grub/grub.cfg

# fstab prüfen
cat /mnt/restore/etc/fstab
BootCurrent: 0001
Timeout: 0 seconds
BootOrder: 0001,0002,0000
Boot0000* Windows Boot Manager	HD(1,GPT,e6636574-fe1d-4c7c-b470-de6cf5fb64de,0x800,0x82000)/\EFI\MICROSOFT\BOOT\BOOTMGFW.EFI57494e444f5753000100000088000000780000004200430044004f0042004a004500430054003d007b00390064006500610038003600320063002d0035006300640064002d0034006500370030002d0061006300630031002d006600330032006200330034003400640034003700390035007d0000006ad00100000010000000040000007fff0400
      dp: 04 01 2a 00 01 00 00 00 00 08 00 00 00 00 00 00 00 20 08 00 00 00 00 00 74 65 63 e6 1d fe 7c 4c b4 70 de 6c f5 fb 64 de 02 02 / 04 04 46 00 5c 00 45 00 46 00 49 00 5c 00 4d 00 49 00 43 00 52 00 4f 00 53 00 4f 00 46 00 54 00 5c 00 42 00 4f 00 4f 00 54 00 5c 00 42 00 4f 00 4f 00 54 00 4d 00 47 00 46 00 57 00 2e 00 45 00 46 00 49 00 00 00 / 7f ff 04 00
    data: 57 49 4e 44 4f 57 53 00 01 00 00 00 88 00 00 00 78 00 00 00 42 00 43 00 44 00 4f 00 42 00 4a 00 45 00 43 00 54 00 3d 00 7b 00 39 00 64 00 65 00 61 00 38 00 36 00 32 00 63 00 2d 00 35 00 63 00 64 00 64 00 2d 00 34 00 65 00 37 00 30 00 2d 00 61 00 63 00 63 00 31 00 2d 00 66 00 33 00 32 00 62 00 33 00 34 00 34 00 64 00 34 00 37 00 39 00 35 00 7d 00 00 00 6a d0 01 00 00 00 10 00 00 00 04 00 00 00 7f ff 04 00
Boot0001* Manjaro	HD(1,GPT,d0982f27-4833-44e1-9986-18f212f9248a,0x800,0xfa000)/\EFI\Manjaro\grubx64.efi
      dp: 04 01 2a 00 01 00 00 00 00 08 00 00 00 00 00 00 00 a0 0f 00 00 00 00 00 27 2f 98 d0 33 48 e1 44 99 86 18 f2 12 f9 24 8a 02 02 / 04 04 36 00 5c 00 45 00 46 00 49 00 5c 00 4d 00 61 00 6e 00 6a 00 61 00 72 00 6f 00 5c 00 67 00 72 00 75 00 62 00 78 00 36 00 34 00 2e 00 65 00 66 00 69 00 00 00 / 7f ff 04 00
Boot0002* endeavouros	HD(1,GPT,e6636574-fe1d-4c7c-b470-de6cf5fb64de,0x800,0x82000)/\EFI\ENDEAVOUROS\GRUBX64.EFI
      dp: 04 01 2a 00 01 00 00 00 00 08 00 00 00 00 00 00 00 20 08 00 00 00 00 00 74 65 63 e6 1d fe 7c 4c b4 70 de 6c f5 fb 64 de 02 02 / 04 04 3e 00 5c 00 45 00 46 00 49 00 5c 00 45 00 4e 00 44 00 45 00 41 00 56 00 4f 00 55 00 52 00 4f 00 53 00 5c 00 47 00 52 00 55 00 42 00 58 00 36 00 34 00 2e 00 45 00 46 00 49 00 00 00 / 7f ff 04 00
insgesamt 24
drwxr-xr-x 6 root root 4096 30. Okt 2024  .
drwxr-xr-x 5 root root 4096  1. Jan 1970  ..
drwxr-xr-x 2 root root 4096  1. Sep 2021  Boot
drwxr-xr-x 2 root root 4096 21. Apr 2024  endeavouros
drwxr-xr-x 2 root root 4096 30. Okt 2024  Manjaro
drwxr-xr-x 4 root root 4096  1. Sep 2021  Microsoft
insgesamt 160
drwxr-xr-x 2 root root   4096 30. Okt 2024  .
drwxr-xr-x 6 root root   4096 30. Okt 2024  ..
-rwxr-xr-x 1 root root 155648 17. Jun 11:39 grubx64.efi
-rw------- 1 root root 11680 17. Jun 11:33 /mnt/restore/boot/grub/grub.cfg
head: '/mnt/restore/boot/grub/grub.cfg' kann nicht zum Lesen geöffnet werden: Keine Berechtigung
# /etc/fstab: static file system information.
#
# Use 'blkid' to print the universally unique identifier for a device; this may
# be used with UUID= as a more robust way to name devices that works even if
# disks are added and removed. See fstab(5).
#
# <file system>             <mount point>  <type>  <options>  <dump>  <pass>
UUID=C626-A127xx                            /boot/efi      vfat    defaults,umask=0077 0 2
UUID=610757af-4666-4500-9ef8-bf76283f8d91xx /              ext4    defaults   0 1
tmpfs                                     /tmp           tmpfs   defaults,noatime,mode=1777 0 0
[y@y-L10111 ~]$ 


```



## fstab BackUp
```bash
[y@y-L10111 etc]$ sudo cp /etc/fstab.backup /etc/fstab

[y@y-L10111 ~]$ cd ..
[y@y-L10111 home]$ cd ..
[y@y-L10111 /]$ cd /etc/
[y@y-L10111 etc]$ ls -l | grep fstab.backup
-rw-r--r--  1 root                 root                    594 17. Jun 12:31 fstab.backup

```