# This project automates the deployment of Linux operating systems on over 2000 servers using
Ansible, leveraging IPMI/iDRAC for remote control and PXE boot for OS installation.


# Linux PXE Deployment via Ansible

Deploys Linux OS via PXE on 2000+ servers using IPMI/iDRAC.

## Usage

1. Update `inventory/hosts.yml` with your BMC & IP details.
2. Ensure PXE + Kickstart infrastructure is live.
3. Run:
   ```bash
   ansible-playbook -i inventory/hosts.yml playbook.yml
   ```
4. Check `install_results.txt` for status.

## Requirements

- PXE infra (TFTP + DHCP + HTTP for kickstart)
- Ansible >= 2.10
- IPMI access enabled on all BMCs
