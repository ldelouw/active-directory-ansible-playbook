# Active-directory-ansible-playbook

This playbook is a nice tool for people that often create Microsoft Active Directory installations in 
Lab environments and are too lazy to set it up manually.

Usually I'm using this Ansble Playbook to make Red Hat IdM Workshops and showcasing Cross Domain Trusts between Red Hat IdM and Active Directory. For IdM I wrote another playbook which can be found here: [https://github.com/ldelouw/rh-ipa-ansible-playbook](https://github.com/ldelouw/rh-ipa-ansible-playbook)

## Author
- Luc de Louw <ldelouw@redhat.com>, <luc@delouw.ch>
- License: GPLv3 or later

## Requirements
- A valid trial license of Microsoft Server 2019
- A virtual machine that fits for W2k19 (usally 4Gbyte of RAM, 50Gbyte of disk)
- Having WinRM conigured on the W2k19 machine
- Ansible with the collection community.windows which can be obtained with ```ansible galaxy install community.windows```

## Preparations

First you need to copy the vars.yml.dist to vars.yml, inventory.dist to inventory.dist, passwd.yml.dist to passwd.yml. Edit the files in question to match your environment. The password for the Ansible Vault file is *changeme*. It's recommended to change the password to something more secure:

```ansible-vault rekey passwd.yml```

Afterwards, edit the passwd.yml with ```ansible-vault edit passwd.yml``` and set the passwords used for the AD Administrator and the users. 

## Running the playbok
```ansible-playbook ad.yml```


