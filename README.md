# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## PROGRAM:
Find out the ip address of the attackers system
## OUTPUT:
![Screenshot 2024-10-28 152830](https://github.com/user-attachments/assets/3bc66ad1-ae10-4723-aedc-0dc50ca04f2c)


## Invoke msfconsole:
## OUTPUT:
![Screenshot 2024-10-28 152843](https://github.com/user-attachments/assets/2fa154d9-b8c8-4c9c-940a-75a71ab72a13)




Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## OUTPUT:

![Screenshot 2024-10-28 152856](https://github.com/user-attachments/assets/aa97e3a1-67be-479b-ab91-2cebbfbf5eee)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:
![Screenshot 2024-10-28 152912](https://github.com/user-attachments/assets/2ac33693-004d-4dfb-bf3f-792a26be31e4)



 ## Step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:
![Screenshot 2024-10-28 152923](https://github.com/user-attachments/assets/f6b3d30f-1cbd-4d08-b743-4fcc9b3dd028)



Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:
![Screenshot 2024-10-28 152935](https://github.com/user-attachments/assets/f8c67a14-66e1-4dbb-a937-bc8160c3f86d)
![Screenshot 2024-10-28 152948](https://github.com/user-attachments/assets/89f2ccf8-3587-4334-98b1-3e45b63784e5)


Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit
![Screenshot 2024-10-28 153003](https://github.com/user-attachments/assets/f37d6893-bc0b-4ea3-a332-909e02175f83)


The info command provides information regarding a module or platform
## OUTPUT:
![Screenshot 2024-10-28 153024](https://github.com/user-attachments/assets/7c52a292-2aec-4231-9a7c-7288f965aaf9)



Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![Screenshot 2024-10-28 153056](https://github.com/user-attachments/assets/1d8ee1ee-9bad-4d48-b442-9b73a1b8bc32)


Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![Screenshot 2024-10-28 153056](https://github.com/user-attachments/assets/b69076d6-dca1-4a0f-b145-0624017c16fc)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![Screenshot 2024-10-28 153109](https://github.com/user-attachments/assets/86125899-9645-476d-acd3-2db4d85636ec)

Use the set rhosts command to set the parameter and run the module, as follows:
![Screenshot 2024-10-28 153120](https://github.com/user-attachments/assets/feb21055-1125-4cc2-9f65-4212c5c99ee0)


After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![Screenshot 2024-10-28 153134](https://github.com/user-attachments/assets/bec68da7-b7a2-4ebc-a134-a3aed84a9b70)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
![Screenshot 2024-10-28 153143](https://github.com/user-attachments/assets/d106a862-43e1-4496-87b4-5955140cd391)



## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
