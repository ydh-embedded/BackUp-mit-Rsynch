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




```