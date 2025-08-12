# Ansible Automation for Network Labs

This section contains Ansible playbooks for automating tasks on Cisco IOS network devices used in my labs.

## Structure

- `inventory/` — Host inventory (YAML format)  
- `group_vars/` — Shared variables like credentials and platform  
- `playbooks/` — Task automation files (backup, gather info, etc.)

## How to Use

1. Make sure Ansible is installed on your system.

2. Install required collections:

    ```bash
    ansible-galaxy collection install ansible.netcommon cisco.ios
    ```

3. Run playbooks like this:

    ```bash
    ansible-playbook -i inventory/hosts.yml playbooks/gather_facts.yml
    ```

Feel free to explore the playbooks and try them out in your own lab setup!
