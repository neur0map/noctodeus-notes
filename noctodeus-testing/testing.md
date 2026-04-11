## Current note

## Nmap quick reference

| Command                                                 | Description                                                |
| ------------------------------------------------------- | ---------------------------------------------------------- |
| `nmap -sS <target>`                                     | TCP SYN (stealth) scan                                     |
| `nmap -sT <target>`                                     | TCP connect scan (uses OS connect)                         |
| `nmap -sU <target>`                                     | UDP scan                                                   |
| `nmap -p <ports> <target>`                              | Scan specific ports (e.g., `-p 22,80,443` or `-p 1-65535`) |
| `nmap -sV <target>`                                     | Service/version detection                                  |
| `nmap -O <target>`                                      | OS detection                                               |
| `nmap -A <target>`                                      | Aggressive scan (OS, versions, scripts, traceroute)        |
| `nmap -sC <target>` or `nmap --script=default <target>` | Run default NSE scripts                                    |
| `nmap --script <script                                  | category> `                                                |
| `nmap -Pn <target>`                                     | Skip host discovery (treat all hosts as up)                |
| `nmap -T4 <target>`                                     | Timing template (T0–T5; higher = faster, more noisy)       |
| `nmap -oN <file> <target>` / `-oX` / `-oG`              | Output to file (normal / XML / grepable)                   |
| `nmap -6 <target>`                                      | Force IPv6 scan                                            |
| `nmap --top-ports <N> <target>`                         | Scan top N most common ports (e.g., `--top-ports 100`)     |

### Common Nmap examples

```bash
nmap -sS -sV -p 22,80,443 -oN scan.txt example.com
nmap -A --script=vuln -oX scan.xml 192.168.1.0/24
nmap -Pn --top-ports 100 -T4 10.0.0.5
```

## Naabu quick reference

| Command                        | Description                                                         |
| ------------------------------ | ------------------------------------------------------------------- |
| `naabu -host <host>`           | Fast TCP port scan against a single host (default fast SYN scanner) |
| `naabu -list <file>`           | Read targets from a file (one host per line)                        |
| `naabu -p <ports>`             | Scan specific ports (e.g., `-p 80,443` or `-p 1-65535`)             |
| `naabu -rate <n>`              | Set packet/scan rate (increase for faster, more noisy scans)        |
| `naabu -exclude-ports <ports>` | Skip specific ports during scan                                     |
| `naabu -o <file>`              | Write results to file (plain text)                                  |
| `naabu -oJ <file>`             | Write results in JSON format                                        |
| `naabu -silent`                | Minimal output (only discovered open ports)                         |
| `naabu -v`                     | Verbose output (show scan progress and extra info)                  |
| `naabu -timeout <ms>`          | Set request timeout in milliseconds (tune for slow networks)        |

### Common Naabu examples

```bash
naabu -host example.com -p 80,443 -o results.txt
naabu -list targets.txt -oJ results.json -rate 300
naabu -host 10.0.0.5 -silent
```
