<h1>HTTP Reconnaissance</h1>


<h2>Description</h2>
This project consists of using the Linux tools such as Nmap, WhatWeb, HTTPie, & Browsh in order to help enumerate information about a target IIS (Internet Information Services) server.
<br />
<br />
Internet Information Services (IIS) is a flexible, general-purpose web server from Microsoft that runs on Windows systems to serve requested HTML pages or files.
<br />
<br />

Disclaimer: The Kali Linux user machine and target machine used in this project was provided to me by INE for educational purposes. The misuse of the information in this project lab can result in criminal charges brought against the individual/individuals in question.
<br />


<h2>Languages and Utilities Used</h2>

- <b>nmap</b>
- <b>whatweb</b>
- <b>http (httpie)</b>
- <b>browsh</b>


<h2>Environments Used </h2>

- <b>Kali Linux</b>

<h2>Project walk-through:</h2>

<p align="left">
Run an Nmap scan on the target ip address to check for any open tcp ports: <br/>
<br/>
- INE has provided me with Kali Linux GUI & target machine (target machine in this case is 10.3.27.15).
<br/>
- We can see that port 80 (http) is open and it looks like its version is Microsoft IIS httpd 10.0.  Next, we can open a web browser and go to 10.3.27.15.  It looks like we get the WebGoat.Net page, which is a deliberately insecure web application maintained by OWASP designed to teach web application security lessons. 
<br/>
<br/>
Commands: nmap 10.3.27.15 -sV -O
<br/>
<br/>
<img src="https://i.imgur.com/X9cKbxm.png" height="80%" width="80%" alt="SSH Dictionary Attack" class="center"/>
<br />
<img src="https://i.imgur.com/fiWRAOt.png" height="80%" width="80%" alt="SSH Dictionary Attack" class="center"/>
<br />
<br />
<br />
<br />
<br />
<br />
<br />



</p>
