This ansible playbook is for launching aws ec2 instance. 

The playbook launches a instance and uses the ec2 eip module to assign an elastic ip to the ec2 instance it launches.

check this ansible eip docs for more uses : http://docs.ansible.com/ansible/ec2_eip_module.html

You can also assign the ec2 to an existing group using this playbook.

To ping a host :

step 1 : create a ssh key : ssh-keygen 

When asked for password and file name give what you want or just skip by pressing enter till end.

step 2 : copy the key : cat ~/.ssh/id_rsa.pub 

Copy the contents of the file

step 3 : Now go to the machine you want to ping : cd ~/.ssh/ && vi authorized_keys

Now paste your key you copied in step 2. 

step 4 : And now do step 1 and 2 in the machine you are going to ping to and copy that key and paste it in your local machine 

Copy the key and paste in ~/.ssh/known_hosts

How to ping : 

ansible-playbook -m ping all  - here -m means module we are mentioning the module ping 

AND ONE IMPORTANT NOTE !!! - you should have the same user in both machines to ping ex : you have a user barry allen in your local machine 
that user should also be there in the machine you are gonna ping. 

Now how to ping if you are using aws .pem private key : 

For this you need to use the switch --private-key= 

ansible-playbook -m ping --private-key=yourkey.pem all

Instead of all you can mention group name. !! 

There are plenty of aws and other ansible modules check : http://docs.ansible.com

Rubiga
