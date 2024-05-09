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

## EXECUTION STEPS AND ITS OUTPUT:

Find out the ip address of the attackers system

## Output:
![image](https://github.com/srinivasanvaiyali/Metasploit-for-reconnaissance/assets/145117665/ae4d735e-3110-48ea-8f5e-4e8b94437558)

Invoke msfconsole:

![image](https://github.com/srinivasanvaiyali/Metasploit-for-reconnaissance/assets/145117665/2dd951b6-5c29-4404-983c-ce04a836f766)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![image](https://github.com/srinivasanvaiyali/Metasploit-for-reconnaissance/assets/145117665/94fa8b70-81aa-460f-adc9-4f746541a9cb)
## Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000



## OUTPUT:
![image](https://github.com/srinivasanvaiyali/Metasploit-for-reconnaissance/assets/145117665/96f9bf6e-ee5b-4910-8e7f-49480665feec)


the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24



## OUTPUT:
![image](https://github.com/srinivasanvaiyali/Metasploit-for-reconnaissance/assets/145117665/62b76f63-c749-44fe-ae34-1bc9c369f6b5)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l


## Output:
![image](https://github.com/srinivasanvaiyali/Metasploit-for-reconnaissance/assets/145117665/09f77086-0e78-471f-9361-024c4b37e21f)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform

## Output:
![image](https://github.com/srinivasanvaiyali/Metasploit-for-reconnaissance/assets/145117665/755ebeb3-32e6-4ca2-bc95-10304b9257e3)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init
## MYSQL ENUMERATION:
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![image](https://github.com/srinivasanvaiyali/Metasploit-for-reconnaissance/assets/145117665/7c9ab1f7-df5a-444b-a833-a7394127a8a7)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/srinivasanvaiyali/Metasploit-for-reconnaissance/assets/145117665/b1391db9-1a87-48eb-9c9b-31767a049eeb)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/srinivasanvaiyali/Metasploit-for-reconnaissance/assets/145117665/ea1de684-3003-4315-8a75-c172366a4c02)

Use the set rhosts command to set the parameter and run the module, as follows:

![image](https://github.com/srinivasanvaiyali/Metasploit-for-reconnaissance/assets/145117665/76c6faf0-76cb-45b7-8126-eccd5bb9a72d)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![image](https://github.com/srinivasanvaiyali/Metasploit-for-reconnaissance/assets/145117665/8b3cbda1-936d-470c-971c-dc568c8d9a82)


set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/srinivasanvaiyali/Metasploit-for-reconnaissance/assets/145117665/13b1b661-de26-4fad-92e5-ff075bc334f3)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
