# Cyber-Security-Project
This is my project showing me navigate azure and the vm's I created
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

- [Load balancing ensures the application is higly responsive, it also stops your network from overloading. Loading Balancing also protects against DoS or DDoS attacks.Jump Box prevents all machinces on the network from being exposed to the public]

Integrating an ELK server allows users to easily monitor the vulnerable VMs for [changes] to the logs and system [traffic].
- [Filebeat watches for log files to collect data and send it to Elasticsearch or Logsstash]
- [Metricbeat records metric data from your system and services such as CPU usage, memory, etc]

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box  | Gateway  | 10.0.0.4   | Linux            |
| Web-1     |Web-Server| 10.0.0.8   | Linux            |
| Web-2     |Web_server| 10.0.0.6   | Linux            |
| ELK       |ELK-stack | 10.2.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the [Jump Box] machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- [Personal public IP address]

Machines within the network can only be accessed by [ssh].
- [My personal public IP address is the only one that can access my ELK-server via port 5601]
A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box      | No                  | Personal  public IP  |
| Web-1         | NO                  | 10.0.0.4             |
| Web-2         | NO                  | 10.0.0.4             |
| ELK-server    | NO                  | Personal  public IP  |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- [Ansible is quick and easy to set up]
The playbook implements the following tasks:
- [Install Docker]
- [Install python3-pip]
- [Install Docker module pip]
- [Use systemctl to use more memory]
- [Download and launch Docker container sebp/elk:761]

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- [Web-1 10.0.0.8]
- [Web-2 10.0.0.6]
We have installed the following Beats on these machines:
- [filebeats]
- [Metricbeats]

These Beats allow us to collect the following information from each machine:
- Filebeat collects system logs, which can be used to track system events
- Metricbeat collects system and service metric data, whhich  can be use to see CPU usage

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the [filebeat and metricbeat config] file to [/etc/ansible/[your_dir]/[your-file-name]].
- Update the [config] file to include [ELK-server's private IP address]
- Run the playbook, and navigate to [ http://[ELK-server-public-IP]:5601/app/kibana] to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? [/etc/ansible/roles/filebeat-playbook.yml is the filebeat playbook] Where do you copy it? [/etc/ansible/[your_dir]/[your-playbook-name]]
- _Which file do you update to make Ansible run the playbook on a specific machine? [/etc/ansible/files/metricbeat-playbook.yml is the metricbeat playbook] How do I specify which machine to install the ELK server on versus which to install Filebeat on? [/etc/ansible/[your_dir]/[your-playbook-name]]
- _Which URL do you navigate to in order to check that the ELK server is running? [Ansible run the playbook on a specific machine(s), update the /etc/ansible/hosts file. Within this file, name groups such as currently contains '[webservers]' and '[elk]', surrounding the group-name and under the group-name, replace private IP's with your own IP's. You then use these group-names behind the "hosts:" field in the playbooks to specify which machines to apply the playbook to]
