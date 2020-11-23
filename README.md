# IOS_GenieParsed_Show_IP_Int_Brief

An Ansible playbook that uses the Genie parser to transform the Cisco IOS "show ip interface brief" command into human readable documentation

## Written by John Capobianco

Using Ansible and Genie Parser this playbooks run the show vrf command, displays the facts to the screen, saves RAW JSON, Nice JSON, Nice YAML, CSV, Markdown, and interactive HTML Mind Map files from the returned stateful data.

### Prerequisites

1) Install Ansible

    $ pip install --user ansible

    Centos:

    yum install python

    yum install ansible

2) Check version of Ansible

    $ansible --version

    ansible 2.9.1

3) Install node.js and npm

    curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -

4) Install Genie

    pip install genie

5) Install Clay's (https://galaxy.ansible.com/clay584/parse_genie) Parse Genie library

   ansible-galaxy install clay584.parse_genie

6) Clone the Repository

   git clone https://github.com/automateyournetwork/IOS_GenieParsed_Show_IP_Int_Brief.git

### CUSTOMIZE

In the hosts file replace the dummy DISTRIBUTION hostnames with your own hostnames.

Ensure Linux host running Ansible playbook can SSH into targetted hosts using prompted username and password.

### Run the playbook

After updating the hosts file with the proper hostnames run the playbook.

cd IOS_GenieParsed_Show_IP_Int_Brief

cd playbooks

ansible-playbook CiscoIOSShowIPIntBriefFacts.yml

<answer prompts for credentials> 

<playbook gathers facts>

<playbook creates files>

cd ..

cd documentation/CAMPUS/FACTS/DISTRIBUTION/

ls

Review files

### Output files

The following files are created per host:

(inventory_hostname)_Show_IP_Int_Br_RAW.json - ALL RAW JSON returned data

(inventory_hostname)_Show_IP_Int_Br_Nice.json - All JSON returned data filtered to Nice JSON

(inventory_hostname)_Show_IP_Int_Br.yml - All returned data in Nice YAML

(inventory_hostname)_Show_IP_Int_Br.csv - Custom fields in CSV

(inventory_hostname)_Show_IP_Int_Br.md - Custom fields in Markdown

(inventory_hostname)_Show_IP_Int_Br.html - Custom fields interactive HTML mind map

#### DEVELOPMENT NOTES

Developed with VS Code, Ansible, CentOS

Tested at vertical scale and horizontally against:

Cisco Catalyst 4500 / 6500 hardware platforms

#### Thanks

Thanks to Clay and the whole Cisco Genie / pyATS / xPresso team!
