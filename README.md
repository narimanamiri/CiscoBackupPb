# CiscoBackupPb
This ansible playbook backs up cisco switch or router configuration and save it to a file the same name as the switches hostname
1-install ansible
2-install ansible cisco ios using aansible-galaxy collection install cisco.ios
3- install paramiko using pip install paramico or apt install python3-paramiko
4-change inventory.ini IP with your device's ip address and USERNAME with your devices username and PASSWORD with your device's password.
5- then run this command in the playbook's directory:
ansible-playbook -i inventory_example.ini backuppb.yml
if you encounter this error :
ssh_dispatch_run_fatal: Connection to 192.168.20.250 port 22: Invalid key length
1-connect to your cisco device using ssh and write thease comands:
2- enable
3-conf t
crypto key zerosize rsa
crypto key generate rsa modulus 2048
end
if you encounter with this error:
Bad SSH2 KexAlgorithms '+diffie-hellman-group-exchange-sha1,+diffie-hellman-group14-sha1,+diffie-hellman-group1-sha1'.
add this line to /etc/ssh/ssh_config:
Host *
    PubkeyAcceptedKeyTypes +*
    KexAlgorithms +diffie-hellman-group1-sha1
    HostKeyAlgorithms *
ENJOY!
