
Overview
--------------------------------------------------------------------------------------------
This project automates the deployment of Linux operating systems on over 2000 servers using
Ansible, leveraging IPMI/iDRAC for remote control and PXE boot for OS installation.

## Key Features
------------------------------------------------------------------------
- Remote server control using IPMI/iDRAC (power on/off, boot device control).
- PXE boot support to initiate OS installation.
- Kickstart-based automated installation of Linux.
- Wait and monitor system availability post-installation.
- Generate success/failure reports per server.
- Designed to scale across thousands of servers.
- 
## Project Structure
---------------------------------------------------------------------
- inventory/hosts.yml: Lists target servers and their IPMI credentials.
- group_vars/all.yml: Global configuration variables.
- roles/deploy_linux/tasks/main.yml: Task automation logic using IPMI and PXE.
- roles/deploy_linux/templates/kickstart.cfg.j2: Kickstart file for Linux installation.
- playbook.yml: Main playbook to run deployment and gather results.
- requirements.yml: Ansible collection dependencies.
- README.md: Usage documentation.

------------------------------------------------------------------------------

## Usage Instruction

1. Update `inventory/hosts.yml` with your BMC & IP details.
2. Ensure PXE + Kickstart infrastructure is live.
3. Run:
   ```bash
   ansible-playbook -i inventory/hosts.yml playbook.yml
   ```
4. Check `install_results.txt` for status.

----------------------------------------------------------------------------------

## Requirements

- PXE infra (TFTP + DHCP + HTTP for kickstart)
- Ansible >= 2.10
- IPMI access enabled on all BMCs



