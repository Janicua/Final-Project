# Final-Project: Red Team & Blue Team

## Blue Team: Summary of Operations

## Table of Contents
- Network Topology
- Description of Targets
- Monitoring the Targets
- Patterns of Traffic & Behavior

### The following machines were identified on the network:

#### Capstone
- Operating System: Linux
- Purpose: Filebeat and Metricbeat are installed and will forward logs to the ELK machine. 
- IP Address: 192.168    

#### Elk 
- Operating System: Linux
- Purpose:It holds the Kibana dashboards
- IP Address:192.168.1.100

#### Kali
- Operating System: Kali Linux
- Purpose: Used in penetration testing
- IP Address: 192.168.1.90

#### Target 1
- Operating System: Kali Linux
- Purpose: Expose vulnerablities during penetration testing
- IP Address: 192.168.1.110


### Description of Targets:

#### The target of this attack was: 
- Target 1 (192.168.1.110).
- Target 1 is an Apache web server and has SSH enabled, so ports 80 and 22 are possible ports of entry for attackers.
#### As such, the following alerts have been implemented:

#### Monitoring the Targets
- Traffic to these services should be carefully monitored. To this end, we have implemented the alerts below:

### Excessive HTTP Errors 
Implemented as follows:

- Metric: TODO
- Threshold: TODO
- Vulnerability Mitigated: TODO
- Reliability: TODO: Does this alert generate lots of false positives/false negatives? Rate as low, medium, or high reliability.

### HTTP Request Size Monitor
Implemented as follows:

- Metric: TODO
- Threshold: TODO
- Vulnerability Mitigated: TODO
- Reliability: TODO: Does this alert generate lots of false positives/false negatives? Rate as low, medium, or high reliability.

### CPU Usage Monitor
Implemented as follows:

- Metric: TODO
- Threshold: TODO
- Vulnerability Mitigated: TODO
- Reliability: TODO: Does this alert generate lots of false positives/false negatives? Rate as low, medium, or high reliability.
TODO Note: Explain at least 3 alerts. Add more if time allows.

## Red Team: Summary of Operations

### Table of Contents
- Exposed Services
- Critical Vulnerabilities
- Exploitation
- Exposed Services

Nmap scan results for each machine reveal the below services and OS details:

$ nmap ... # TODO: Add command to Scan Target 1
  # TODO: Insert scan output

This scan identifies the services below as potential points of entry:

Target 1
List of
Exposed Services
TODO: Fill out the list below. Include severity, and CVE numbers, if possible.

The following vulnerabilities were identified on each target:

Target 1
List of
Critical
Vulnerabilities
TODO: Include vulnerability scan results to prove the identified vulnerabilities.

Exploitation
TODO: Fill out the details below. Include screenshots where possible.

The Red Team was able to penetrate Target 1 and retrieve the following confidential data:

Target 1
flag1.txt: flag1{b9bbcb33e11b80be759c4e844862482d}
Exploit used
TODO: Include the command run
flag2.txt: flag1{b9bbcb33e11b80be759c4e844862482d
Exploit Used
TODO: Identify the exploit used
TODO: Include the command run

