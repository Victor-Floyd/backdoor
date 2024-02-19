# Installing, Using, and Blocking a Malware-based Backdoor

In this lab, I will disable Windows Defender, leaving a server vulnerable. 
I'll then simulate the accidental installation of malware and view the changes. 
Next I'll take on the role of a pen tester or hacker, and determine whether the malware was installed based on open network ports. 
I'll then connect to the infected server, proving I have the ability to exploit it. 
Finally, in the role of security administrator, I will remove the malware.
<br/> <br/>

• Disabled Windows Defender protection, leaving the server vulnerable to malware. <br/> <br/>
<img src="https://githubucket.s3.us-east-2.amazonaws.com/Disable+Windows+Defender.png" height="80%" width="80%" alt="Disable Windows Defender"/> <br/> <br/>

• Installed malware. Just pretend that the malware was installed **unknowingly** while downloading this "Simple Hasher" Application. <br/> <br/>
<img src="https://githubucket.s3.us-east-2.amazonaws.com/Installed+Malware.png" height="80%" width="80%" alt="Install Malware"/> <br/> <br/>

• Running the Task Manager after the download shows that a process "ncat", a well-known atack tool, is now running. <br/><br/>
<img src="https://githubucket.s3.us-east-2.amazonaws.com/ncat.png" height="80%" width="80%" alt="ncat is now running"/> <br/> <br/>

• The Netcat backdoor runs with the priviledges of the logged on user (currently Administrator) and allows a remote machine to access the command prompt on the infected machine. Here, I run a posture assessment to see if the backdoor can be discovered. I use a network scanner "Angry IP Scanner" to discover the port that the backdoor is listening on. <br/> <br/>

<img src="https://githubucket.s3.us-east-2.amazonaws.com/AngryIP1.png" height="80%" width="80%" alt="ncat is now running"/> <br/>

<img src="https://githubucket.s3.us-east-2.amazonaws.com/AngryIP2.png" height="80%" width="80%" alt="ncat is now running"/> <br/>

<img src="https://githubucket.s3.us-east-2.amazonaws.com/AngryIP3.png" height="80%" width="80%" alt="ncat is now running"/> <br/><br/>

• Here, I connect to the backdoor using a terminal emulation client called PuTTY <br/> <br/>
<img src="https://githubucket.s3.us-east-2.amazonaws.com/PuTTY.png" height="80%" width="80%" alt="connect to backdoor with PuTTY"/> <br/> <br/>

• Once connected, I run a command to add the threat actor as a user, and then another command to add that malicious user to the local administrators group. <br/> <br/>
<img src="https://githubucket.s3.us-east-2.amazonaws.com/Add+Threat+Actor+to+Local+Admin+Group.png" height="80%" width="80%" alt="add threat actor to local admin group"/> <br/> <br/>

• Upon further inspection of the original download file for the "Simple Hasher" app, I discover a script (ini.vbs) that launches netcat and creates a firewall rule to allow connections to it over port 4450. I delete this script.  <br/>  <br/>
<img src="https://githubucket.s3.us-east-2.amazonaws.com/malicious+script.png" height="80%" width="80%" alt="delete malicious script"/> <br/> <br/>

• Next, I view processes in the Task Manager, select the previously discovered "ncat" process and End it. <br/> <br/>
<img src="https://githubucket.s3.us-east-2.amazonaws.com/malicious+firewall+rule.png" height="80%" width="80%" alt="select netcat firewall rule"/> <br/> 
<img src="https://githubucket.s3.us-east-2.amazonaws.com/disable+malicious+firewall+rule.png" height="80%" width="80%" alt="end netcat process"/> <br/> <br/>







