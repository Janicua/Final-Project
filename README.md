# Final-Project: Red Team & Blue Team

## Blue Team: Summary of Operations

## Table of Contents
- Network Topology
- Description of Targets
- Monitoring the Targets
- Patterns of Traffic & Behavior

### The following machines were identified on the network:
- ![image](https://user-images.githubusercontent.com/79546857/129990800-50515072-34be-4217-82a1-46c301f08655.png)

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

### Target 1
#### Nmap scan results for each machine reveal the below services and OS details:
- $ nmap -sP 192.168.1.1-255
- ![Nmap_Sweep](https://user-images.githubusercontent.com/79546857/129990470-4f30b006-3ff5-4561-8b7e-1800fe0a74aa.JPG)
- This scan identifies the services below as potential points of entry

#### List of Exposed Services:
- ![exposed_ports_services](https://user-images.githubusercontent.com/79546857/129991072-c9bf61f0-c040-4f35-b55d-fb9317a765ca.JPG)
- Port 80 is open 

#### The following vulnerabilities were identified on each target:


#### List of Critical Vulnerabilities
- ![WPScan1](https://user-images.githubusercontent.com/79546857/129991959-81851384-99f4-41eb-bbd9-4e1c0945c287.JPG)
- ![WPscan2](https://user-images.githubusercontent.com/79546857/129991980-523aac90-5f04-40de-9df7-bd7880ee9301.JPG)

#### Exploitation
- ![SSH@mike](https://user-images.githubusercontent.com/79546857/129992040-312767fb-d0b7-496f-a43a-41884f61cfd1.JPG)
- SSH access was granted due to weak password security. 

#### The Red Team was able to penetrate Target 1 and retrieve the following confidential data:

- flag1.txt: flag1{b9bbcb33e11b80be759c4e844862482d}
- ![Flag1](https://user-images.githubusercontent.com/79546857/129992218-82f6f52f-239c-46d0-8db6-37b0a57efdf7.JPG)
TODO: Include the command run
- flag2.txt: flag1{b9bbcb33e11b80be759c4e844862482d
- ![Flag2](https://user-images.githubusercontent.com/79546857/129992231-2f215c98-1a2d-40f8-ade9-71aff735515f.JPG)

