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


