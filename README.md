# ansible-rhel7-lamp
Ansible Playbook to install and configure LAMP on a pre-provisioned RHEL 7 host

# Prerequisites

- Machine with RHEL 7 installed and 1 interface configured for External Network IP
- Public key authentication set for root user
  $ ssh-copy-id root@lamp.example.com
- Red Hat Network user account with Red Hat Enterprise Linux Subscription available

# Instructions

1. Checkout this repository
2. Configure vars.yml to match your environment
3. Create a vaut file named vault in the playbook directory
   `$ ansible-vault create vault`
4. Start RHEL system slotted for LAMP installation
5. Make sure you can ssh to the LAMP machine as root without having to enter a password
6. Run the playbook
   `$ ansible-playbook --ask-vault-pass -i hosts rhel7-lamp.yml`

# Vault Vars
vault_rhn_user: Red Hat Network Account Username  
vault_rhn_pwd: Red Hat Network Account Password  
vault_rhn_pool_name: Subscription Manager pool name to attach to
