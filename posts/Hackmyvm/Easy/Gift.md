After spawning up the target machine, we do an fping to get target IP

![image](https://github.com/kism37/kism37.github.io/assets/115076145/155907e7-3e92-4eea-b32d-a93d331b7ac4)

 
since *.*.*.62 and *.*.*.119 are my AP and my machine's address respectively, Target IP should be 192.168.8.179. Added IP to /etc/hosts with name 'gift.hmv'

ran full nmap scan on target IP and found ssh and http open..

![image](https://github.com/kism37/kism37.github.io/assets/115076145/f5d93748-ebc8-41e9-aa04-8e1412007c46)

 

ran dirb and nikto on http for hidden directories but found nothing except index.html

![image](https://github.com/kism37/kism37.github.io/assets/115076145/62f80d66-eda5-4d23-a230-636b75c9f59a)


Checked browseer on port 80, http and found this;

![image](https://github.com/kism37/kism37.github.io/assets/115076145/d437b172-fca6-4fa3-b4bf-5bb1227ee245)

 

Since i could do nothing to port 80, http at the moment... I started shooting at port 22, ssh.
made a user wordlist of two users ‘gift’, and ‘root’ 
then i bruteforced with ncrack using the user wordlist and rockyou as password wordlist.
Then i landed a hit.

![image](https://github.com/kism37/kism37.github.io/assets/115076145/01780b99-dd3e-4c6d-b0e2-5631dd55b0a9)



root:simple

I 'ssh-ed' into machine and got root access straight up and found user and root flag.
![image](https://github.com/kism37/kism37.github.io/assets/115076145/9a30cd0c-af25-4b44-92db-e741f0a1e3f4)

