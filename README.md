
# Ansible Deployment Project

## Overview
This Ansible project is designed to automate the deployment of the `abn-assessment-api` from a public GitHub repository.

The playbook performs the following tasks:
1. Ensures the target directory exists.
2. Clones the `abn-assessment-api` repository from GitHub.
3. Updates the configuration files based on the target environment.
4. Restarts the application to apply the updates.

## Files and Directories
- `inventory`: Defines the hosts for the playbook.
- `playbook.yml`: Main playbook containing deployment tasks.
- `group_vars/`: Contains shared variables across all groups.
- `host_vars/`: Environment-specific variables and configurations.
- `private_configs/`: Private configuration files for different environments.

## How to Run
1. **Install Ansible**: Ensure Ansible is installed on your control machine.
2. **Prepare Inventory**: Update the `inventory` file with your target hosts.
3. **Run the Playbook**:
   ```bash
   ansible-playbook -i inventory playbook.yml
   ```
   - To specify a specific environment:
     ```bash
     ansible-playbook -i inventory playbook.yml --extra-vars "ansible_hostname=dev"
     ```

## Requirements
- Ansible 2.9 or later
- Access to the target hosts via SSH

## Notes
- Adjust the playbook and configuration files as needed for your environment.
- Ensure proper permissions for the `private_configs` directory.

## License
MIT License
