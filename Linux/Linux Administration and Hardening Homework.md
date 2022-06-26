Step 1: Ensure/Double Check Permissions on Sensitive Files
1.	Permissions on /etc/shadow should allow only root read and write access.
o	(In /etc) ls -l | grep shadow
o	sudo chmod 600 /etc/shadow
2.	Permissions on /etc/gshadow should allow only root read and write access.
o	(In /etc) ls -l | grep gshadow
o	sudo chmod 600 /etc/gshadow
3.	Permissions on /etc/group should allow root read and write access and allow everyone else read access only.
o	(In /etc) ls -l | grep group
o	sudo chmod 644 /etc/group
4.	Permissions on /etc/passwd should allow root read and write access and allow everyone else read access only.
o	(In /etc) ls -l | grep passwd
o	sudo chmod 644 /etc/passwd
Step 2: Create User Accounts
1.	Add user accounts for sam, joe, amy, sara, and admin.
o	sudo useradd sam
o	sudo useradd joe
o	sudo useradd amy 
o	sudo useradd sara
o	sudo useradd admin
2.	Ensure that only the admin has general sudo access.
o	sudo usermod -a -G sudo admin





Step 3: Create User Group and Collaborative Folder
1.	Add an engineers group to the system.
o	sudo addgroup engineers
2.	Add users sam, joe, amy, and sara to the managed group.
o	sudo usermod -a -G engineers sam
o	sudo usermod -a -G engineers joe
o	sudo usermod -a -G engineers amy 
o	sudo usermod -a -G engineers sara
3.	Create a shared folder for this group at /home/engineers.
o	sudo mkdir /home/engineers
4.	Change ownership on the new engineers' shared folder to the engineers group.
o	(In /home/engineers) chown –from=currentowner:engineers
Step 4: Lynis Auditing
1.	Command to install Lynis: sudo apt-get install lynis
2.	Command to see documentation and instructions: sudo lynis --help
3.	Command to run an audit: sudo lynis audit system
4.	Provide a report from the Lynis output on what can be done to harden the system.
 

Bonus
1.	Command to install chkrootkit: sudo apt install shktoolkit
2.	Command to see documentation and instructions: sudo chktoolkit --help
3.	Command to run expert mode: sudo chktoolkit -x
4.	Provide a report from the chrootkit output on what can be done to harden the system.
