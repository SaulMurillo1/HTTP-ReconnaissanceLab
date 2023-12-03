![image](https://github.com/SaulMurillo1/HTTP-ReconnaissanceLab/assets/149205773/dc2094dd-793e-4d04-b1a2-010ed49c0445)<h1>HTTP Reconnaissance</h1>


<h2>Description</h2>
This project consists of using the Linux tools such as Nmap, WhatWeb, & HTTPie in order to help enumerate information about a target IIS (Internet Information Services) server.
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
- <b>http (HTTPie)</b>


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
Command: nmap 10.3.27.15 -sV -O
<br/>
<br/>
<img src="https://i.imgur.com/X9cKbxm.png" height="80%" width="80%" alt="HTTP Reconnaissance" class="center"/>
<br />
<img src="https://i.imgur.com/fiWRAOt.png" height="80%" width="80%" alt="HTTP Reconnaissance" class="center"/>
<br />
<br />
<br />
<br />
<br />
<br />
<br />
Use the WhatWeb tool to enumerate possible valuable information about the target IP: <br/>
<br/>
- We can see that the whatweb tool is able to enumerate a lot of information about the target machine.
<br/>
- For example, it looks like the we can verify that the IIS Server vesion is 10.0, the ASP.NET version is 4.0.30319, the XXS Protection is set to 0 which means it does not have cross site scripting protection, and the default page of the target is /Default.aspx
<br/>
<br/>
Command: whatweb 10.3.27.15
<br/>
<br/>
<img src="https://i.imgur.com/AqC1yvr.png" height="80%" width="80%" alt="HTTP Reconnaissance" class="center"/>
<br />
<br />
<br />
<br />
<br />
<br />
<br />
Another tool we can use to enumerate valuable information about the target IP is HTTPie: <br/>
<br/>
- HTTPie is designed for testing, debugging, and generally interacting with APIs & HTTP servers. The http & https commands allow for creating and sending arbitrary HTTP requests. They use simple and natural syntax and provide formatted and colorized output.
<br/>
- We can see that we are able to enumerate some of the same information as the WhatWeb tool.
<br/>
<br/>
Command: http 10.3.27.15
<br/>
<br/>
<img src="https://i.imgur.com/opaXDRV.png" height="80%" width="80%" alt="HTTP Reconnaissance" class="center"/>
<br />
<br />
<br />
<br />
<br />
<br />
<br />
Use the Dirb tool to help find other directories on the target machine site: <br/>
<br/>
- Dirb is a command line tool you can use to fuzz web sites or web apps. Dirb finds files and directories on your target site that are not directly linked from a publicly accessible page on the site or from the Internet. This means Dirb can map out your target beyond what you may find by just browsing the site yourself.
<br/>
- We can see that we are able to enumerate some other directories associated with http://10.3.27.15.
<br/>
<br/>
Command: dirb http://10.3.27.15
<br/>
<br/>
<img src="https://i.imgur.com/adXEKn3.png" height="80%" width="80%" alt="HTTP Reconnaissance" class="center"/>
<br />
<img src="https://i.imgur.com/oVJywax.png" height="80%" width="80%" alt="HTTP Reconnaissance" class="center"/>
<br />
<img src="https://i.imgur.com/s9lZagz.png" height="80%" width="80%" alt="HTTP Reconnaissance" class="center"/>
<br />
<br />
<br />
<br />
<br />
<br />
<br />
Use Nmap scripts to enumerate information about the http server: <br/>
<br/>
- As seen down below, we can also use Nmap scripts to enumerate information about the http server. 
<br/>
- Note: I am using a different target IP as before in this example below. 
<br/>
<br/>
Command: nmap 10.3.17.11 -sv
<br/>
nmap 10.3.17.11 -p 80 -sV --script http-headers
<br/>
<br/>
<img src="https://i.imgur.com/3fCgcB2.png" height="80%" width="80%" alt="HTTP Reconnaissance" class="center"/>
<br />
<img src="https://i.imgur.com/n0gmU7L.png" height="80%" width="80%" alt="HTTP Reconnaissance" class="center"/>
<br />
<br />
<br />
<br />
<br />
<br />
<br />



</p>
