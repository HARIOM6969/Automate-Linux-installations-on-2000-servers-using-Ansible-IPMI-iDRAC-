
Overview
--------
This project automates the deployment of Linux operating systems on over 2000 servers using
Ansible, leveraging IPMI/iDRAC for remote control and PXE boot for OS installation.
Key Features
------------
- Remote server control using IPMI/iDRAC (power on/off, boot device control).
- PXE boot support to initiate OS installation.
- Kickstart-based automated installation of Linux.
- Wait and monitor system availability post-installation.
- Generate success/failure reports per server.
- Designed to scale across thousands of servers.
Project Structure
-----------------
- inventory/hosts.yml: Lists target servers and their IPMI credentials.
- group_vars/all.yml: Global configuration variables.
- roles/deploy_linux/tasks/main.yml: Task automation logic using IPMI and PXE.
- roles/deploy_linux/templates/kickstart.cfg.j2: Kickstart file for Linux installation.
- playbook.yml: Main playbook to run deployment and gather results.
- requirements.yml: Ansible collection dependencies.
- README.md: Usage documentation.
Usage Instructions
------------------
1. Update the inventory file with server and BMC information.
2. Ensure a working PXE environment with accessible Kickstart server.
3. Install required Ansible collections:
$ ansible-galaxy collection install -r requirements.yml
4. Run the playbook:

$ ansible-playbook -i inventory/hosts.yml playbook.yml
5. Review the install_results.txt file for deployment status.
Requirements
------------
- PXE boot infrastructure (TFTP, DHCP, HTTP servers)
- Ansible 2.10 or later
- IPMI access to all servers
