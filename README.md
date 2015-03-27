ssh-user
=========

Creates a user with ansible user module and grants passwordless sudo access to all nodes the role is deployed to.Uploads a predefined ssh RSA keyfile both private and public to the creted users .ssh and authorized_keys file.

Requirements
------------

Setting the user expiry requires ansible v 1.9 as a minimum.

Role Variables
--------------

All the variables are desrcibed in vars/main.yml:

|                 |                                                    |
| ----------------|--------------------------------------------------|
| `ssh.user`      | name of user to create                             |
| `ssh.groups`    | groups the user belongs to (default wheel,disk)    |
| `ssh.expiry`    | expiry date of the created account                      |
| `ssh.pubkey`    | publickey for the id_rsa to be uploaded            |


The rsa private key should also be included in the  files direcctory.


Example Playbook
----------------

    - hosts: cephnodes
      roles:
         - { role: wakwanza.ansible-role-ssh-user , ssh.user: 'ceph' , ssh.groups: 'wheel,disk' , ssh.expiry: '1554076799' , ssh.pubkey: 'ssh-rsa WD......Dnxm ceph'}

License
-------

BSD

Author Information
------------------

wakwanza.
