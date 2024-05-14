# This is a project for al the Alta3 servers given in the course.

It downloads a hello world project on public github.

First it goes to the servers to install the proper dependencies.

python3
python3-pip
git
In this case there was an error with one server so it check the OS and checked if is a Debian or a RedHat systems.

and finally it clones the repository.

## Notes for Professor Hutch: Hope you still remember me. When we where on class you told me to continue the project I was working on class. So I just add some things more but is basically this and is working fine. If you think there is something missing please tell me.


## Run the project.
In your root directory run this comands.
### git clone https://github.com/rogezit/python-ansible-project.git
### cd python-ansible-project/
### ansible-playbook -i inventory/hosts playbooks/deploy_python_app.yml

If is working fine you should get something like this.


student@bchd:~/python-ansible-project$ ansible-playbook -i inventory/hosts playbooks/deploy_python_app.yml

PLAY [python_servers] *************************************************************************************

TASK [Gathering Facts] ************************************************************************************
ok: [bender]
ok: [zoidberg]
ok: [fry]
ok: [farnsworth]

TASK [Ensure system is up-to-date on Debian-based systems] ************************************************
skipping: [farnsworth]
changed: [bender]
changed: [zoidberg]
changed: [fry]

TASK [Ensure system is up-to-date on RedHat-based systems] ************************************************
skipping: [bender]
skipping: [zoidberg]
skipping: [fry]
changed: [farnsworth]

TASK [Install required packages on Debian-based systems] **************************************************
skipping: [farnsworth] => (item=python3) 
skipping: [farnsworth] => (item=python3-pip) 
skipping: [farnsworth] => (item=git) 
skipping: [farnsworth]
ok: [fry] => (item=python3)
ok: [bender] => (item=python3)
ok: [zoidberg] => (item=python3)
changed: [bender] => (item=python3-pip)
ok: [bender] => (item=git)
changed: [zoidberg] => (item=python3-pip)
ok: [zoidberg] => (item=git)
changed: [fry] => (item=python3-pip)
ok: [fry] => (item=git)

TASK [Install required packages on RedHat-based systems] **************************************************
skipping: [fry] => (item=python3) 
skipping: [zoidberg] => (item=python3) 
skipping: [bender] => (item=python3) 
skipping: [zoidberg] => (item=python3-pip) 
skipping: [bender] => (item=python3-pip) 
skipping: [fry] => (item=python3-pip) 
skipping: [zoidberg] => (item=git) 
skipping: [zoidberg]
skipping: [bender] => (item=git) 
skipping: [fry] => (item=git) 
skipping: [fry]
skipping: [bender]
changed: [farnsworth] => (item=python3)
ok: [farnsworth] => (item=python3-pip)
ok: [farnsworth] => (item=git)

TASK [Clone the repository] *******************************************************************************
changed: [farnsworth]
changed: [bender]
changed: [zoidberg]
changed: [fry]

PLAY RECAP ************************************************************************************************
bender                     : ok=4    changed=3    unreachable=0    failed=0    skipped=2    rescued=0    ignored=0   
farnsworth                 : ok=4    changed=3    unreachable=0    failed=0    skipped=2    rescued=0    ignored=0   
fry                        : ok=4    changed=3    unreachable=0    failed=0    skipped=2    rescued=0    ignored=0   
zoidberg                   : ok=4    changed=3    unreachable=0    failed=0    skipped=2    rescued=0    ignored=0

