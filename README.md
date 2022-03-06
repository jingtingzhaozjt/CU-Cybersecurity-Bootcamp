# ELK Stack Deployment


  <br>

  
  
  
![ELK project diagram](https://user-images.githubusercontent.com/93953425/156901511-c095ff36-f05a-49f8-a3f4-3a01799a5d9d.jpg)
<h2>Description of the Topology <h2/>
 
Resource|Function|IP Address| Operating System|
--------|--------|----------|-----------------|
Jump-Box| Gateway| Public: 40.87.120.117 Private: 10.0.0.4|Linux|
Web-1| Server| Public: N/A Private: 10.0.0.5|Linux|
Web-2| Server| Public: N/A Private: 10.0.0.6|Linux|
ELK-Server| Monitoring| Public: 52.189.127.154 Private: 10.1.0.4|Linux|

  
  
  

  

<h2>Access Policies<h2/>

The machines on the internal network are not exposed to the public Internet.

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
<br>
<br>
- 5601 Kibana port
<br>  
Machines within the network can only be accessed by the Jump-Box-Provisioner.

A summary of the access policies in place can be found in the table below. 

  
<br>
  
  
Resource|Publicly Accessible (Y/N)|Allowed IP Address|
------|------|-------|
Jump-Box|	yes	|My personal IP|
Web-1	|no	|10.0.0.4|
Web-2	|no	|10.0.0.4|
ELK-Server|	no	|10.0.0.4|  
  
  
  
<h2>Kibana dashboard for Filebeats<h2/>
  
  
  
  
  
  
  
