# Use Cases

How to Enable ssh in container

3 steps to perform

Step 1:- yum install openssh-server -y      # Install openssh-server 
Step 2:- sshd-keygen                        # Generate private, public key for server
Step 3:- /usr/sbin/sshd

Check :- netstat -tnlp 
Port 22 should be running