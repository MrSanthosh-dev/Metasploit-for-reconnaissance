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
![image](https://github.com/MrSanthosh-dev/Metasploit-for-reconnaissance/assets/117916573/ae32563c-e7f8-4f45-98a5-e6f11d3bd99d)
Invoke msfconsole: 
![image](https://github.com/MrSanthosh-dev/Metasploit-for-reconnaissance/assets/117916573/9d96c176-4772-467a-b038-82d443c545d3)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![image](https://github.com/MrSanthosh-dev/Metasploit-for-reconnaissance/assets/117916573/91e4ed29-717c-47fe-8a3d-f60afcf259cd)
Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000 
![image](https://github.com/MrSanthosh-dev/Metasploit-for-reconnaissance/assets/117916573/03680da4-4a99-447b-8213-366eb1e76a9d)
the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later. scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24 
![image](https://github.com/MrSanthosh-dev/Metasploit-for-reconnaissance/assets/117916573/2d7a1582-12a6-43c3-8c04-3af3022145a3)
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
## OUTPUT:
![image](https://github.com/MrSanthosh-dev/Metasploit-for-reconnaissance/assets/117916573/b2d513f5-4023-410c-b424-e1d12fa0bbed)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform,
![image](https://github.com/MrSanthosh-dev/Metasploit-for-reconnaissance/assets/117916573/5a8d8086-48db-4e78-901f-166eca5822b3)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![image](https://github.com/MrSanthosh-dev/Metasploit-for-reconnaissance/assets/117916573/abd928ce-9fb9-48a7-94b0-ddf2c2fe934d)
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![image](https://github.com/MrSanthosh-dev/Metasploit-for-reconnaissance/assets/117916573/5f1160ee-4823-4e67-ad2b-86f82dd8060a)
Use the set rhosts command to set the parameter and run the module, as follows: 
![image](https://github.com/MrSanthosh-dev/Metasploit-for-reconnaissance/assets/117916573/77819c7f-f3d0-4505-ad17-c5ffa48503a8)
After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![image](https://github.com/MrSanthosh-dev/Metasploit-for-reconnaissance/assets/117916573/70a4a5a4-346d-4a8c-bc23-704258f6903e)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/MrSanthosh-dev/Metasploit-for-reconnaissance/assets/117916573/cbdddefc-4298-4983-94e3-cf29930ad746)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
