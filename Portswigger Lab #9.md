Portswigger Lab #9 20OCT2023 Solved

Lab: Basic SSRF against another back-end system


Purpose: Bypass the internal stock checking system to gain administrative rights and delete the user carlos


Analysis: 

1.) I made sure that burp was open and started the lab.

2.) Going to the first product, I checked the stock and took note of the /stock POST HTTP intercept. 

3.) I sent that POST through to the Intruder and modified the stockapi to allow me administrative rights "http://192.168.0.1:8080/admin"

4.) Navigating to the payloads tab, highlighting the last octet, I clicked the "add" button and made sure the attack type read "numbers".

5.) Under that, I had a starting number of "1" and an end number of "255" with a step count of "1"

6.) After the attack completed, I see that 58 is the correct last octet number for the ip address.

7.) I right clicked on that request, and sent it to the repeater.

8.) At the bottom of the Request pane, I changed the stockapi URL to "http://192.168.0.58:8080//admin/delete?username=carlos"

9.) Clicking refresh on the website shows that I have solved the lab.
    

Remediation: 
    