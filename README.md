<h1>Phishy v1</h1>

 <!-- ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)/> -->

<h2>Description</h2>
You have been sent a phishing link - It is your task to investigate this website and find out everything you can about the site, the actor responsible, and perform threat intelligence work on the operator(s) of the phishing site.

Warning: The website and kit you see is the lab is REAL. Exercise caution when interacting with the malicious website and do not enter any sensitive information
<br />


<h2>Languages and Utilities Used</h2>

- <b>Text Editor</b> 
- <b>Web Browser</b>

<h2>Environments Used </h2>

- <b>Linux</b>

<h2>Program walk-through:</h2>

<p align="center">

<h3>Q1) The HTML page used on securedocument.net is a decoy. Where was this webpage mirrored from, and what tool was used? (Use the first part of the tool name only)</h3>
<b>Investigate Phishing Website </b> <br />
** Looks to be an Office365 login <br />
** Navigate to root of the URL securedocument.net <br />
** View Page Source to view HTML > Comment showing that the site was mirrored<br /> 
** ANSWER TO Q1) 61.221.12.26/cgi-sys/defaultwebpage.cgi, HTTrack <br /> <br />
<img src="https://github.com/nickstrunk/Phishyv1/assets/165805194/32ddf935-1116-43f8-bf2e-41fa25b34601" height="80%" width="80%" alt="Planning Diagram"/>
<br />
<br />

<h3>Q2) What is the full URL of the background image which is on the phishing landing page?</h3>
<b>Inspect Landing Page</b> <br />
** Right Click web page > Open Image in New Tab >  URL for background image shown as new tab URL<br /> 
** ANSWER TO Q2) hxxp[://]securedocument[.]net/secure/L0GIN/protected/login/portal/axCBhIt.png <br /> <br />
<img src="" height="80%" width="80%" alt="Planning Diagram"/>
<br />
<br />

<h3>Q3) What is the name of the php page which will process the stolen credentials?</h3>
<b>Inspect Page Source</b> <br />
** Right click web page > View Page Source <br /> 
** PHP script is called once credentials entered<br />
** ANSWER TO Q3) jeff.php <br /> <br />
<img src="" height="80%" width="80%" alt="Planning Diagram"/>
<br />
<br />

<h3>Q4)Two more tools were used to perform reconnaissance against open ports, what were they?</h3>
<b>Investigate User Agent Strings</b> <br />
** Leave signature of the tool it is originating from <br /> 
** Filter ip.dst==10.251.96.5 && http.user_agent -all packets that have a user agent string to the target IP <br />
** Pattern of HTTP Get requests <br />
** Inspect one of the suspicious requests > Shows gobuster 3.0.1 (brute forcing tool) <br /> <br />
<img src="" height="80%" width="80%" alt="Planning Diagram"/>
<br />
<br />
** Search beyond gobuster packets > Discover pagckets with URL encoding and embedded SQL commands <br />
** Inspect suspicious packets > Shows sqlmap 1.4.7 <br /> <br />
<img src="" height="80%" width="80%" alt="Planning Diagram"/>
<br />
<br />
** ANSWER TO Q4) gobuster 3.0.1, sqlmap 1.4.7
<br />
<br />

<h3>Q5)What is the name of the php file through which the attacker uploaded a web sheel?</h3>
<b>Investigate HTTP POST requets </b> <br />
** Filter for http.request.method==POST<br /> 
** Ignore sqlmap requests (SQL injection attempts) > Discover POST for /upload.php <br />
** Inspect request > Find Refer (what file was uploaded) hxxp[://]10[.]251[.]96[.]5/editprofile.php <br />
** ANSWER TO Q5) editprofile.php <br /> <br />
<img src="https://github.com/nickstrunk/Network-Analysis-Web-Shell-Easy-/assets/165805194/7544f18a-cb02-47c9-b619-21187e2451bd" height="80%" width="80%" alt="Planning Diagram"/>
<br />
<br />
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
