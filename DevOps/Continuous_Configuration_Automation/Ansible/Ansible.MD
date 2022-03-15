In devops world we need automation.  <br> 
What is automation ? <br>
Simple ex to understand Run multiple commands manually in Linux CLI, Put all commands to one script and run auto is called automation. This script run in shell is called shell scripting. <br>

Point here is we have linux everywhere and also naturally we have shell scripting, so Why we need ansible. Instead we have shell scripting. Automation already exist in the world, but we also need 1 more thing top of automation that ansible tool provide is intelligence. <br>

Use case :- Means ansible provide automation but also use their intelligence

Ex :- We have to configure web server in multiple linux os.

In shell scripting, you have to give commands  which suits os. but in multiple os, may be different-2 versions - redhat, ubuntu, centos etc. So in that point at time your script fails.

Here ansible benefits you, here you have to only tell to ansible what you want to do, tell requirement only. Whatever command need it handles by ansible. <br>

In shell scripting world :- Tell what to do and also how to do means comes under Impearative(Tell both things). <br> 
In Ansible world :- Tell only what to do comes under Declarative(Intelligence). 

So why we need ansible this is clear.

What is Ansible ?
Ansible is configuration management tool. <br>

Configuration :- In os configure something like, create file, put data, install s/w, setup servers, services, performance management, tunning all things comes under configuration.   <br>

The tools we used to manage these things is called configuration management tool ex:- Ansible. <br>

To manage multiple systems also called Managed/Target node  using Ansible we need to setup ansible in one system is called Controller node.  <br>

Install ansible <br>

Step 1 :- Set up yum using epel-release <br>
Step 2 :- yum install epel-release -y  <br>

While run ansible to configure anything it always read one file where we define details of our all managed nodes details(Ip, username, password/key)  called inventory(database) file. Path :- /etc/ansible/hosts  <br>

Run commands :- ansible all -m package -a "name=httpd state=present" <br>

-m - Module ex:- package used to install software in manage nodes. <br>
-a - Arguments you can see ansible document which keywords they support. <br>

But before run their commands, you need to do one this go to ansible config file /etc/ansible/ansible.cfg uncomment 
host_key_checking=False <br>

Pre requivisite in Manage/Target nodes :- ssh should be configured, python must install, yum should be configured. <br>

Now you can run any commands of ansible. <br>