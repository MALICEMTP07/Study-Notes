# Nmap Cheatsheet

## Core Scans

### Host Discovery
```text
nmap -sn 192.168.1.0/24
```

### Top Ports
```text
nmap -sS --top-ports 1000 TARGET
```

### Full TCP Scan
```text
nmap -p- -T4 TARGET
```

### Service Detection
```text
nmap -sV TARGET
```

### Default NSE
```text
nmap -sC TARGET
```

### Aggressive
```text
nmap -A TARGET
```

### UDP
```text
nmap -sU --top-ports 100 TARGET
```

### Vuln Scripts
```text
nmap --script vuln TARGET
```

## Output

**Generiert:**
- normal
- grepable
- xml

## Typical Workflow

**First pass:**
```text
nmap -oA scanname TARGET
nmap -sS --top-ports 2000 -T4 --open TARGET
```

**Second wave:**
```text
nmap -pPORTS -sC -sV -oA second_wave TARGET
```
