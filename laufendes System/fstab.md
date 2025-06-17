## Schritt 1: System-fstab wiederherstellen (falls versehentlich geändert)

Falls du versehentlich die fstab deines laufenden Systems geändert hast:

```bash
# Backup zurückspielen
sudo cp /etc/fstab.backup /etc/fstab
sudo systemctl daemon-reload
```