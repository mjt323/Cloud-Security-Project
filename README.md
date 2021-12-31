# Cloud-Security-Project
Project I
# Cybersecurity-Project-I
This is for a submission of many documents including Cloud Security scripts, diagrams, kibana, and other information.  We created and ELK stack SIEM.
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![ELK Stack Diagram](https://github.com/mjt323/Cloud-Security-Project/blob/main/Diagrams/ELK%20Stack%20Diagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _playbook__ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._ The name of the file is: playbook.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly **redundant**, in addition to restricting **traffic** to the network.
- TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?  The load balancers protect the system from DDos attacks and they do this by shifting the attack traffic. The main advantage of a jump box is that it can give access to the user from a single node or origin point that can be secured and monitored and helps to connect to other servers or untrusted networks environments.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the __data___ and system __logs___.
- _TODO: What does Filebeat watch for? Filebeat monitors and watches the specified log files or locations and collects the log events and forwards them to Elasticsearch or Logstash for indexing.
- _TODO: What does Metricbeat record? Metricbeat records and collects metrics from the system and services running on the server such Apache and other services.  It takes these metrics and ships them to the specified output such as Elasticsearch.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name         | Function | IP Address | Operating System |
|--------------|----------|------------|------------------|
| Jump Box     | Gateway  | 10.0.0.4   | Linux            |
| DBWA-1       | Server   | 10.0.0.5   | Linux            |
| DBWA-2       | Server   | 10.0.0.6   | Linux            |
| ELK-Stack-VM | Server   | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the __jump box___ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: 5601 Kibana port

Machines within the network can only be accessed by __Jump Box___.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_ Jump Box VM; Virtual Network IP: 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name         | Publicly Accessible | Allowed IP Addresses |
|--------------|---------------------|----------------------|
| Jump Box     | Yes                 | HOME IP              |
| DBWA-1       | No                  | 10.0.0.4             |
| DBWA-2       | No                  | 10.0.0.4             |
| ELK-Stack_VM | No                  | 10.0.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_ The main advantage of using ansible is that it lets you model highly complex IT workflows, it is a free open source tool, and no special coding skills are required.    

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_  This system is monitoring DBWA-1, 10.0.0.5 and DBWA-2, 10.0.0.6

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_  I installed Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._  Filebeat is files and directorires; metricbeat focuses on system and memory, etc.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _playbook.yml____ file to _jump box____.
- Update the __host___ file to include...the private IP address of the two webservers.
- Run the playbook, and navigate to _ansible-playbook /etc/ansible/playbook.yml___ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
