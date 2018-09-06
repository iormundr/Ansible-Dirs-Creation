# Ansible-Dirs-Creation
Script for creating ansible dir structure 


Usage: ./create_playbook.py /path/to/playbookname [role1 role2 ...]
Creates an empty playbook skeleton, with any roles that are specified.
e.g. ./create_plafybook.py /tmp/pyplaybook web db cache
If /path/to/playbookname already exists, we only create the roles that don't 
exist yet, according to our structure.
###############################################################################
group_vars/
    all                   # The main file for defining variables for this playbook
roles/
    role1/                # Each role
        files/            # Role-specific files which will be copied to the remote machine
        handlers/         # Role-specific handlers
            main.yml      # handler file
        tasks/            # Role-specific tasks
            main.yml      # task file
        templates/        # Role-specific templates
        vars              # Role-specific variables, although I recommend using group_vars/all instead
        meta/             # Files that establish role dependencies
###############################################################################
I'm putting more emphasis on well-structured roles here, and less on external 
dependencies/playbooks.
