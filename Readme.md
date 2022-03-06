# Project 1 - Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.
![image](https://user-images.githubusercontent.com/93953425/156904177-a58648b2-7e9f-4733-a230-4be697468ad1.png)


This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


# Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly efficient, in addition to restricting traffic to the network.

- What aspect of security do load balancers protect?
   	- Load balancers protects the system from DDoS attacks by shifting attack traffic.
  	- Load Balancing contributes to the Availability aspect of security in regards to the CIA Triad.
 
- What is the advantage of a jump box?
   	- The advantage of a jump box is to give access to the user from a single node that can be secured and monitored.
   	- The advantage of a JumpBox is the orgination point for launching Administrative Tasks. This ultimately sets the JumpBox as a SAW (Secure Admin Workstation). All Administrators when conducting any Administrative Task will be required to connect to the JumpBox (SAW) before perfoming any task/assignment.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the changes to the Logs and system traffic.

- What does Filebeat watch for?
   	- Filebeat watches for any information in the file system which has been changed and when it has.  
   	- Filebeat watches for log files/locations and collects log events
- What does Metricbeat record?
  	- Metricbeat takes the metrics and statistics that collects and ships them to the output you specify.
   	- Metricbeat records metric and statistical data from the operating system and from services running on the server.

The configuration details of each machine may be found below.

Resource|Function|IP Address| Operating System|
--------|--------|----------|-----------------|
Jump-Box| Gateway| Public: 40.87.120.117 Private: 10.0.0.4|Linux|
Web-1| Server| Public: N/A Private: 10.0.0.5|Linux|
Web-2| Server| Public: N/A Private: 10.0.0.6|Linux|
ELK-Server| Monitoring| Public: 52.189.127.154 Private: 10.1.0.4|Linux|

           
# Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- Add whitelisted IP addresses:-
    	- Public IP address which changes everytime when the VM is on/off eg of Public IP 137.135.115.14

Machines within the network can only be accessed by SSH.

- Which machine did you allow to access your ELK VM? What was its IP address? JumpBox VM, its private Ip address(Vnet IP)-10.1.0.8

A summary of the access policies in place can be found in the table below.

Resource|Publicly Accessible (Y/N)|Allowed IP Address|
------|------|-------|
Jump-Box|	yes	|My personal IP|
Web-1	|no	|10.0.0.4|
Web-2	|no	|10.0.0.4|
ELK-Server|	no	|10.0.0.4| 


# ELK Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because this allows you to deploy to multiple servers using a single playbook

The playbook implements the following tasks:
- Install docker.io
- Install Python3-pip
- Install docker container
- Launch docker container: elk
- Command: sysctl -w vm.max_map_count=262144


# Target Machines & Beats

This ELK server is configured to monitor the following machines:
- Web-1(10.0.0.5)
- Web-2(10.0.0.6)

We have installed the following Beats on these machines:

- Filebeat
- Metricbeat

These Beats allow us to collect the following information from each machine:

- Filebeat monitors log files or locations you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.
- Metricbeat collects metrics from the operating system and from services running on the server.

Ansible Playbook are used to configure and install those Beats. **Refer to the "ansible" folder for the ansible playbooks and configuration files.**

These Beats allow us to collect the following information from each machine:
- filebeat collects log data and shows them in the monitoring clusters. 
- metricbeat collects metrics and statistics and shows them in the output specified, for example Elasticsearch or Logstash. 

# Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the playbook (.yml) file to Ansible directory.
- Update the host file to include webserver and ELK. 
- Run the playbook, and navigate to Kibana to check that the installation worked as expected. 
   ( http://[your.VM.IP]:5601/app/kibana )





