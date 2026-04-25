# Burp Methodology

## Web Pentest Flow

### 1. Recon

**Fingerprint:**
- Tech stack
- Headers
- Cookies
- Parameters
- Auth flows

**Use:**
- Proxy
- HTTP History
- Target Scope

### 2. Mapping Attack Surface

**Look for:**
- Hidden endpoints
- IDOR candidates
- Parameter pollution
- File uploads
- SSRF inputs

**Use:**
- Repeater
- Logger
- Sitemap

### 3. Manual Testing

**Test:**
- Authentication
- Session handling
- Access control
- Input validation

**Check:**
- SQLi
- XSS
- SSTI
- XXE
- Command Injection

### 4. Repeater Workflow

Send request. Mutate one variable at a time.

**Observe:**
- Status code
- Length
- Timing
- Behavior changes

### 5. Intruder Use Cases

- Username enumeration
- Fuzzing parameters
- Wordlists
- Forced browsing

### 6. Decoder / Comparer

**Useful for:**
- JWT
- Base64
- Hash comparison
- Token analysis

### 7. Typical Test Pattern

- Baseline request
- Input mutation
- Auth bypass checks
- Privilege abuse checks
- Impact validation

## Methodology Principle

Tool drives nothing. Hypothesis drives testing. Burp validates hypotheses.

## Common Findings Checklist

- IDOR
- Broken Access Control
- JWT flaws
- CSRF
- SSRF
- Deserialization
- Race conditions
- Logic bugs

## References Worth Knowing

- GTFOBins
- HackTricks
- PayloadsAllTheThings
- LOLBAS
- Impacket
- BloodHound
