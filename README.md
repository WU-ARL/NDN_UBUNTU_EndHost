
# NDN_UBUNTU_EndHost
Files to edit:
host_vars/UBUNTU_EH     : change value for ansible_host to address of host to be installed.
                        : change ndn_rtr_address to address/hostname of NDN gw router to connect to
                        : change value for ansible_user to username that should be used for ssh and installations.
                        :      that user must have sudo privileges
ubuntuEndHostInventory  : change value for ansible_ssh-private_key_file to point to your private key.
                        :      host being installed should have public key in ~/.ssh/authorized_keys


For Ubuntu 14.04 do this:
> ansible-playbook -i ubuntuEndHostInventory ubuntu_end_host.yml

Since it does not have python installed as /usr/bin/python
for Ubuntu 16.04 you may need to run like this the first time:
> ansible-playbook -e 'ansible_python_interpreter=/usr/bin/python3' -i ubuntuEndHostInventory ubuntu_end_host.yml

After the first successful run of the playbook, python 2.7 should also be installed
and you can drop the -e '    ' option.



