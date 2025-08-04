# network-port-scan-task-
Task-1 - Network Port Scanning Task - Cybersecurity Internship
## Objective
Learn network reconnaissance by discovering open ports on local network devices to understand network exposure and security implications.

## Network Information
- **Network Range**: 192.168.1.0/24
- **My IP Address**: 192.168.1.102
- **Scan Date**: August 4, 2025, 11:32 IST
- **Tool Used**: Nmap 7.95

## Command Executed
nmap -sS -sV -O -oA network_scan 192.168.1.102/24

## Key Findings Summary
- **Total Hosts Scanned**: 256 IP addresses
- **Active Hosts Found**: 4 devices
- **Total Open Ports**: 4 ports across 2 devices
- **High-Risk Services**: MySQL database (unauthorized access)

## Active Devices Discovered

### 1. Router/Gateway (192.168.1.1)
- **Device**: TP-LINK router
- **MAC**: B0:95:75:30:3A:56
- **Open Ports**: 22, 80, 1900
- **Services**: SSH, HTTP config, UPnP
- **Risk Level**: Medium

### 2. Database Server (192.168.1.100)
- **Device**: Windows machine with MySQL
- **MAC**: C0:35:32:88:31:47
- **Open Ports**: 3306
- **Services**: MySQL (unauthorized)
- **Risk Level**: HIGH

### 3. Windows Device (192.168.1.101)
- **Device**: Windows 10/11 or Xbox 360
- **MAC**: 1A:69:8B:FA:B2:A3
- **Open Ports**: None
- **Risk Level**: Low

### 4. My Machine (192.168.1.102)
- **Device**: Local scanning machine
- **Open Ports**: None detected
- **Risk Level**: Low

## Security Assessment

### Critical Findings
1. **MySQL Database Exposed** (192.168.1.100)
   - Port 3306 open with unauthorized access
   - No authentication required
   - **Immediate Action Required**

### Medium Risk Findings
1. **Router Management Interface** (192.168.1.1)
   - SSH and HTTP admin interfaces exposed
   - UPnP service running
   - **Recommendation**: Restrict access, disable UPnP if not needed

## Recommendations
1. **Secure MySQL Database**: Enable authentication, restrict network access
2. **Router Security**: Change default credentials, disable unnecessary services
3. **Network Segmentation**: Consider VLANs for sensitive devices
4. **Regular Scanning**: Monitor for new services and vulnerabilities
