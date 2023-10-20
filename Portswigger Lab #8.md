Portswigger Lab #8 20OCT2023 Solved

Lab: SSRF


Purpose: To bypass the REST API and submit a crafted URL to gain administrative access and delete the user "carlos"


Analysis: 

1.) Using burp and opening the vulnerable webpage, I navigated to an item and requested the stock count at the bottom of the page.

2.) Intercepting the stock count request in burp, I sent that line to the repeater to begin the attack.

3.) At the bottom of the Request section I was able to see the stock api request. I changed that to http://localhost/admin/ and sent that to the website.

4.) Reading off of the Response pane, I was able to gain administrative rights and type in "delete" on the search bar to identity the url to delete the user carlos.

5.) Finding the URL (http://localhost/admin/delete?username=carlos) I was able to copy and paste that to the Request pane and send that off to the server.

6.) The response was a 302 code, and the user carlos was deleted, completing the lab.
    

Remediation: 
    