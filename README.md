# assignment1-9april
Q1 #
Creating directory structure
ans:
mkdir -p A/{B/{D/{I/M/Z,J/L/Z},E/H/L/Z},C/{F/H/L/Z,G/K/L/Z}}
tree A

Q2 #
Providing the permission to a user only to execute the date command and removing the permission for executing date command for root. 
ans:
sudo su   (login into root)
useradd -s /bin/date dtt   (adding user)
chmod -x /bin/date  (removing permission) 
setfacl -m u:dtt:rwx /bin/date (setting permision for dtt user)
exit (exiting from root)
date (run date command then it will show permission denied)
sudo su - dt (it will be able to run only date command)

Q3 #
copy one user data into another user 
ans:
sudo adduser ch
(After adding user)
su ch
cd ..
cd ch
mkdir f1
cd f1
touch a.txt
cat > a.txt 
(write any thing like 'hello world')
exit 
sudo adduser hc
(After adding user)
su hc
cd ..
cd hc
mkdir f2
cd f2
touch b.txt
cat > b.txt 
(write any thing like 'hey from other world')
exit 
sudo cp /home/ch/f1/a.txt /home/hc/f2 (copying a.txt to f2 folder)
sudo cp /home/hc/f2/b.txt /home/ch/f1 (copying b.txt to f1 folder)

Q4 #
run cal command for 10sec and store output in /tmp/a.txt
ans:
watch -n 10 "(cal)|tee -a /tmp/a.txt"
