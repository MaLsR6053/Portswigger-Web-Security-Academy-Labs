Portswigger Lab #7 20OCT2023 Solved

Lab: Bypassing 2-Factor Auth


Purpose: This lab's two-factor authentication can be bypassed. You have already obtained a valid username and password, but do not have access to the user's 2FA verification code. To solve the lab, access Carlos's account page.


Analysis: 

1.) After logging into the wiener:peter account, I clicked on my own email client button and took note of the 2FA code.

2.) Going back to the web page, I input the code and then after a succesfull login, I took note of the URL. 

3.) At the end of the URL, it says " https://0a5b00a803a3a890824dd82d0039004f.web-security-academy.net/my-account?id=wiener"

4.) The exploit is performed by logging into the other account carlos:montoya and when prompted for the 2FA code, instead of trying to hack into carlos' email, I simply changed the end of the URL to =carlos instead of wiener.

5.) This allowed me to access the carlos:montoya account, and bypassing 2FA.

Remediation: 
    