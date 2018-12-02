# zad_mk_usr

Playbook is creating admin and jenkins user on appservers and just admin user on dbservers.

**Prerequisites**

You should create pair of SSH keys or use already created. It might be possible to change public key name if was called different than id_rsa.pub.

To create SSH key pair run:
> #ssh-keygen

Follow with creator steps. New keypair will be located in .ssh user's directory.

## How to use:
Run Vagrant to spin-up two new instances with following command:
> #vagrant up

Note!!!
It can takes a while before vm will be up and running.

To check status of VM's, please run:
> #vagrant status

To run ansible playbook, use following command:
> #ansible-playbook sites.yml

File ansible.cfg already contain default inventory as hosts.yml file.

To configure different password than already provided in playbooks, use
following command:

> #mkpasswd -m sha-256

To use that command you need to have following command installed

*CentOS/RHEL:*
> #yum install expect

*Debian/Ubuntu:*

> #apt-get install whois

You will prompted for password.

When new string will be genrated replace generated value with "upassword" varaible in playbooks there is also possible to replace user name with "uname" variable.

To see if user has been created just run following command:

> #ansible <inventory> -a "grep -r <user_name> /etc/passwd"
