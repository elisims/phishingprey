# Phishing Pentest
>> Performing a phishing attack.

## Crafting the Phishing Email
> Good morning Brandon,
This is Elias from IT&C. I’ve been working on that report, but I’m having some technical issues. Jim said that you would be the one to help me solve the issue I’m having with this document. I’ve attached the document to this email. If you have time right now, are you available to take a look and review why the issue is occurring? Please review it ASAP- I will be awaiting your reply.
Report.docx (link to payload) Thanks again,
-Elias

## Initial Access Technique
- I decided to use the c2 tool called “Empire” because it was recommended during class. I had to  install  it  using  the  github  approach-  As  installing  it  normally  through  Kali  Linux  wasn’t working correctly at the time.
- After the installation, I was able to start up empire by using the command “sudo ./empire.”"

- Now that the program was up and running, I needed to create a listener.
- I created the listener using the following commands:
> - Listeners
> - Uselistener http
> - Set Name operation1
> - Set Port 8085
- Once the initial information for the listener was set up, I confirmed the information by using the command “info”.

- With the listener set up (and reviewed for errors) I then went back and started to configure the macro. This was done with the following commands:
> - Back
> - Usestager windows/macro
> - Set Listener operation1
- The final step before generating the macro was just to review the information (to confirm it was all correct). This was done by simply entering the command “info” into the empire prompt.

- Once the information was confirmed to be correct, I typed the command “generate”.
- The command generated the payload for the macro which can be copy-pasted into a Word file (.docx) for the use of executing the payload.



## Creating the Report.docx payload
- Creating a new Word document called “Report” and in the search bar typing “view macros” will bring up the macro prompt.



- With the macro pasted into the macro window, all that was left to do was save the Report.docx document with “macro enabled”.



- The  final  test  was  to  execute  this  file  on  the  victim/target  host  and  see  if  the  payload successfully obtains information from the victim. When the file was executed on the target’s host, a warning/security notice appeared- Which is a potential flag to the victim (of course), but if the victim selects “enable macros”, our c2 correctly communicates with our attacking VM.



- With the  empire  working correctly, we  can  now view the sensitive data  received from the
macro payload. The responses contain data such as the device name, IP address, username and machine name. All this information is helpful to an attacker.

