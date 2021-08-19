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

- Metric: WHEN count() GROUPED OVER top 5 'http.response.status_code' IS ABOVE 400 FOR THE LAST 5 minutes
- Threshold: 5
- Vulnerability Mitigated: Continous monitoring 
- Reliability: Medium reliability - Could be an error not caused by an intruder.  

### HTTP Request Size Monitor
Implemented as follows:

- Metric: WHEN sum() of http.request.bytes OVER all documents IS ABOVE 3500 FOR THE LAST 1 minute
- Threshold: 5
- Vulnerability Mitigated: N/A
- Reliability: High reliability - The larger the size, the more questionabble the HTTP request. 

### CPU Usage Monitor
Implemented as follows:

- Metric: WHEN max() OF system.process.cpu.total.pct OVER all documents IS ABOVE 0.5 FOR THE LAST 5 minutes
- Threshold: 5
- Vulnerability Mitigated: N/A
- Reliability: High reliability - The harder the CPU works, the more questiobnale the acvtivity may seem. 

## Red Team: Summary of Operations

### Table of Contents
- Exposed Services
- Critical Vulnerabilities
- Exploitation
- Exposed Services

### Target 1
#### Nmap scan results for each machine reveal the below services and OS details:
- $ nmap -sP 192.168.1.1-255
- This scan identifies the services below as potential points of entry
- ![Nmap_Sweep](https://user-images.githubusercontent.com/79546857/129990470-4f30b006-3ff5-4561-8b7e-1800fe0a74aa.JPG)


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

##### flag1.txt: flag1{b9bbcb33e11b80be759c4e844862482d}
- ![Flag1](https://user-images.githubusercontent.com/79546857/129992218-82f6f52f-239c-46d0-8db6-37b0a57efdf7.JPG)
- michael@target1:/var/www$ grep -RE flag html

##### flag2.txt: flag2{fc3fd58dcdad9ab23faca6e9a36e581c}
- ![Flag2](https://user-images.githubusercontent.com/79546857/129992231-2f215c98-1a2d-40f8-ade9-71aff735515f.JPG)

##### flag3.txt: flag3{afc01ab56b50591e7dccf93122770cd2}
- mysql> show tables;
- mysql> select * from users;
- mysql> select * from wp_posts;

##### flag4.txt: flag4{715dea6c055b9fe3337544932f2941ce}
- sudo python -c 'import pty;pty.spawn('/bin/bash");'
