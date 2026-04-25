# Linux PrivEsc Notes

## Enumeration First

### Basic Host Enumeration

**Examples:**
```text
hostname
uname -a
cat /etc/os-release
id
whoami
sudo -l
cat /etc/passwd
cat /etc/group
last
w
find / -perm -4000 -type f 2>/dev/null
```

### User Enumeration

**Check:**
- Zusätzliche Benutzer
- Service Accounts
- Mitglieder privilegierter Gruppen
- Passwort-Wiederverwendungsmöglichkeiten
- SUID Binaries

**Auffällige Kandidaten gegen:**
- GTFOBins prüfen
- ungewöhnliche custom binaries prüfen
- `find`
- `vim`
- `bash`
- `cp`

**Referenz:**
- GTFOBins

## Writable Files / Misconfigurations

**Prüfen:**
- Config-Dateien
- Startup-Skripte
- Cron Targets
- Service-Dateien
- Cron Jobs

**Checks:**
- Writable scripts
- PATH hijacking
- Wildcard abuse
- Capabilities

**Prüfen auf:**
- Relative binary calls
- World-writable directories

**Commands:**
```text
python
perl
find / -writable -type f 2>/dev/null
find / -writable -type d 2>/dev/null
crontab -l
ls -la /etc/cron*
cat /etc/crontab
getcap -r / 2>/dev/null
echo $PATH
```

**Interessant:**
- `/usr/bin/python3 cap_setuid+ep`

## Kernel Exploits

**Abgleichen gegen:**
- DirtyPipe
- DirtyCow
- PwnKit

Exploit erst nach sauberer Enumeration.

## Credentials Hunting

**Suche:**
- SSH keys
- Backups
- Config secrets
- Reused creds

## Automated Enumeration

- LinPEAS
- LES
- linux-exploit-suggester.sh

Automation bestätigt nur Findings.

```text
uname -r
grep -R "password" /home 2>/dev/null
find / -name "*.db" 2>/dev/null
find / -name "id_rsa" 2>/dev/null
./linpeas.sh
```
