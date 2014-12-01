# Samba: Cheat Sheets
## Troubleshooting Samba Commando’s:

**Samba logs:**

| Commando | Betekenis
| :--- | :---
| `smbd -l /var/log/samba`, `smbd -l /var/log/samba` | Toon de configuratie logs van Samba
| `cat /var/log/samba` | Toon de configuratie logs van Samba
| `kill -SIGUSR2 1234` | Deactiveren Samba logging
| `kill -SIGUSR1 1234` | Activeren Samba logging

**Samba Service:**

| Commando | Betekenis
| :--- | :---
| `Systemctl restart smbd` | Herstart Samba
| `Strace` | Lists all system calls
| `ps –ea | grep smbd` | Toont of de samba service actief is of niet

**Samba networking:**

| Commando | Betekenis
| :--- | :---
| `tcpdump -v -s 255 -i eth0 port not telnet` | Monitor network traffic in real time
| `telnet ServerName 139` | Test de poort toegang van Samba

**Samba Daemons:**

| Commando | Betekenis
| :--- | :---
| `ps ax` | Kijken of de 2 daemons: smbd en nmbd al gestart zijn
| `Netstat –a` | Laat zien of de daemons gebonden zijn aan poorten
| `Testparm` | Test daemons
| `Testparm /usr/local/samba/lib/smb.conf client ip-address` | Test of de smb.conf, de naam van je client en je ip-adres wel aan de voorwaarden voldoen.

## Troubleshooting Samba Stappen:

Stap 1: Basis netwerkverbinding testen adhv ping
Stap 2: DNS testen met ping & de naam
Stap 3: Controleren of er geen errors aanwezig zijn in de smb.conf adhv testparm smb.conf
Stap 4: Samba starten/herstarten
Stap 5: Logfiles checken op errors
Stap 6: Testen of de poorten die Samba nodig heeft of te werken, open staan. Indien niet , host allow statement toevoegen aan smb.conf
Stap 7: Controleren of de firewall bepaalde requests & poorten blokkeert


