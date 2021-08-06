# zabbix-5-monitor
Configuring a Zabbix 5 monitoring environment

![image](https://user-images.githubusercontent.com/22028539/127569725-ea6d1b67-fbae-4c7d-a8b4-0eb9bb6c3eaf.png)

## What to monitor?
- Responsibilities
- Survey of assets and services involved
- Validation
- Settings

## Why monitor?
- Observe if the conditions of an object/equipment are within the standards.
- Predict trends for profile changes.
- Allow faster and more correct corrective actions.

## FCAPS Model
![image](https://user-images.githubusercontent.com/22028539/127568271-cc4899d2-e748-42fe-90eb-235cfab67940.png)

### Fault Management
- Incident or event that causes the system to malfunction.
- Main objective is to quickly detect and resolve situations that degrade the functioning of the network.

### Performance Management
- Measurement and analysis of performance of a particular service.
- Data evaluation to send alerts when the performance level reaches a certain threshold.

## Downtime cost
Costs incurred for the loss of condition to operate the business when certain services(s) are not provided.

### Cost classification
- Loss of productivity
- Loss of opportunities
- Impossibility to serve customers
- Special technical intervention
- Legal penalties and indemnities

## Causes
- Old equipment
- Security threats
- Software update
- Connectivity
- Human errors
- Maximum storage capacity reached

### Complexity
- Increase in critical applications (New technologies in the environment)
- High increase in interruptions (Systems failure, Human error)

### Summarizing in a few answers
- Understand the company's "core business"
- Control the environment
- Know what IT assets you have, how they are being consumed and by whom
- Reduce downtime
- Improve services

## Zabbix overview
Some services

![image](https://user-images.githubusercontent.com/22028539/127569546-96049fbc-0a33-487c-889a-33109e2e41b9.png)

Data levell protection

![image](https://user-images.githubusercontent.com/22028539/127569851-13cd7d8f-ad44-4749-a570-87fd7c4b6fe1.png)

[Zabbix Docs](https://www.zabbix.com/documentation/current/)

## Zabbix Archtecture

![image](https://user-images.githubusercontent.com/22028539/127714688-d5b4cfd1-4edb-4e9a-97bc-6b32bd88d946.png)

- Zabbix Server: Save data into DB

![image](https://user-images.githubusercontent.com/22028539/127714843-8bcc66dd-2772-4967-91b3-b438a2479c71.png)

- Zabbix Proxy: Get data from hosts and sendo to Zabbix server

![image](https://user-images.githubusercontent.com/22028539/127714888-29a722c3-5c35-4b15-b554-1d2b68c45057.png)

- Zabbix Agent: Send collected data to zabbix server or zabbix proxy

![image](https://user-images.githubusercontent.com/22028539/127715030-e6302796-c62b-41c9-9a67-c7113226425e.png)

### Monitoring sources
1. Zabbix agent
2. Simple Monitor
3. SNMP agent
4. Trapper
5. Arquivos de log
6. Internal
7. SSH
8. Telnet
9. JMX
10. IPMI
11. Data Base
12. Calculated

In order to create alerts we use triggers as following cpu load alert example:
```
{ServidorXPTO:system.cpu.load.last()} > 5
```

An event in zabbix can be a new host discover or a trigger.

Zabbix allow us to have templates for categories of monitored host, so we can link one template to multiple hosts.

### Collect
The data collected are saved in a DB and them be available to print reports or graphs
![image](https://user-images.githubusercontent.com/22028539/127716134-eb6c610d-5ba9-47dd-9a8c-8e5513fa06f4.png)

It is posible to use e-mail, sms, telegram and others tools to send alerts when an event occurs or open open tickets.

## Integrations
You can integrate zabbix with diferent tools that can be founded in https://www.zabbix.com/br/integrations

![image](https://user-images.githubusercontent.com/22028539/127716562-9bc1e6b2-b2f8-47e2-adbf-57135dfb2625.png)

PS: You can propose a integration solution in zabbix site.

## Customer question befor start a project:
- What do you want to monitor?
- Which SO?
- Are there web aplications?
- What langages are used on web aplication?
- What are the type and brand of network?
- What are the type and brand of printers?
- Show zabbix working and a POC.
- Which alerts are important?
- Implementation only or month maintanance?

There is a [budget example spreadsheet](https://github.com/glauberss2007/zabbix-5-monitor/blob/main/zabbiz_project_budget_example.xlsx) in this repository.

## Creating a virtual enveronment using vagrant
In this step we will use "VAGRANT" to create 1 Linux VM in virtualbox.

### Vagrant
Vagrant is a tool for building and managing virtual machine environments in a single workflow. With an easy-to-use workflow and focus on automation, Vagrant lowers development environment setup time, increases production parity, and makes the "works on my machine" excuse a relic of the past.

1. My system is opensuse, so i will use zypper to install virtualbox and vagrant:

```
sudo zypper in autoconf automake gcc kernel-devel make

sudo zypper update
sudo zypper install virtualbox

sudo wget --no-check-certificate https://releases.hashicorp.com/vagrant/2.2.18/vagrant_2.2.18_x86_64.rpm -O vagrant.rpm
sudo zypper in vagrant.rpm
```
2. Select the OS box to deploy at https://app.vagrantup.com/boxes/search, in this case a centos linux:

3. Some vagrant commands usefull:

Create the Vagrantfile and use init and up comands to create the VM.
```
vagrant init
vagrant up {NAME}
vagrant ssh
vagrant halt
vagrant destroy
```



## Zabbix Installation strategies


