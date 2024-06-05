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
** ANSWER TO Q2) hxxp[://]securedocument[.]net/secure/L0GIN/protected/login/portal/axCBhIt.png
<br />
<br />

<h3>Q3) What is the name of the php page which will process the stolen credentials?</h3>
<b>Inspect Page Source</b> <br />
** Right click web page > View Page Source <br /> 
** PHP script is called once credentials entered<br />
** ANSWER TO Q3) jeff.php <br /> <br />
<img src="https://github.com/nickstrunk/Phishyv1/assets/165805194/01e1461d-0c15-4020-b10c-67bd090cef99" height="80%" width="80%" alt="Planning Diagram"/>
<br />
<br />

<h3>Q4) What is the SHA256 of the phishing kit in ZIP format? (Provide the last 6 characters)</h3>
<b>Traverese Backwards Through URL</b> <br />
** Inspect HTML of each directory > (/secure) References "0ff1cePh1sh.zip"<br /> <br />
<img src="https://github.com/nickstrunk/Phishyv1/assets/165805194/e8f0bbc9-be91-4213-adb8-6ff6cc36c520" height="80%" width="80%" alt="Planning Diagram"/>
<br />
<br />
**  Download the file from the web page directory where 0ff1cePh1sh.zip is referenced<br /> <br />
<img src="https://github.com/nickstrunk/Phishyv1/assets/165805194/2dfbcb08-446f-478a-95a0-7f260971337e" height="80%" width="80%" alt="Planning Diagram"/>
<br />
<br />
** Run sha256sum on 0ff1cePh1sh.zip <br /> <br />
<img src="https://github.com/nickstrunk/Phishyv1/assets/165805194/f7a65f14-4c54-4cf3-84a3-7f819e67853f" height="80%" width="80%" alt="Planning Diagram"/>
** ANSWER TO Q4) fa5b48 
<br />
<br />

<h3>Q5) What email address is set up to recieve the phishing credential logs?</h3>
<b>Investigate PHP File That Processes the Stolen Credentials </b> <br />
** Click on jeff.php file that is referenced in the HTML of the web page <br /> 
** Variable $recipient = "boris.smets@tfl-uk.co" <br />
** ANSWER TO Q5) boris.smets@tfl-uk.co <br /> <br />
<img src="https://github.com/nickstrunk/Phishyv1/assets/165805194/fc1b7cf2-29bf-4a85-9af5-960726a0c2c0" height="80%" width="80%" alt="Planning Diagram"/>
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
