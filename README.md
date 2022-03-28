# Elk-project ## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)



https://drive.google.com/file/d/1s88TzoZb62uiu6b5cDob4zcdGCXiRIJu/view?usp=sharing










These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly _____, in addition to restricting _____ to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _file____ and system __metrics___.
- _TODO: What does Filebeat watch for? It is a light weight shipper that forwards and centralizes log data.
- _TODO: What does Metricbeat record? It takes the metrics and statistics that it gathers and moves them to the output that you choose. Examples are Logstash and Elasticsearch.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux      |
| Web 1    | webserver  10.0.0.5   | Linux           |                  |
| Web 2    | webserver  10.0.0.6   | Linux           |                  |
| Elk V    | monitoring 10.1.0.4   | Linux           |                  |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the _jump box virtual____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 13.64.141.145
- _TODO: Add whitelisted IP addresses_

Machines within the network can only be accessed by _____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes.                | 13.64.141.145   |
| Web 1      no                    10.0.0.5                      |
| web 2      no                    10.0.0.6
  Elk        no                    10.1.0.4  

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_
It is an efficient way to set up a standardized configuration in multiple machines 

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Docker a aansible to jump box 
- Elk virtual machine to host
- Then run your playbook 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
Web 1 and Web 2 are monitored by the Elk server

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
Filebeat and metricbeat.

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
Filebeat acknowledges when there are differences to the filesystem such as apache logs

Metricbeat finds changes in system metrics like cpu usage and ssh attempts. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _playbooks____ file to ___Ansible__.
- Update the __configure___ file to include... the download and setup
- Run the playbook, and navigate to _kibana___ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_The playbook is where the sensible runs the specified commands and correct hosts. 
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_ first ssh to the correct machine. To specify you must build separate virtual machine on a different network to really monitor. 
- _Which URL do you navigate to in order to check that the ELK server is running?
20.127.73.113:5601/app/kibana
_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

Ansible-playbook playbook.yml
Ansible-playbook filbeat.yml
Ansible-palybook metricbeat.yml
