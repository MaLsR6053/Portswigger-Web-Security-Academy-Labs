Portswigger Lab #2 OCT152023 *SOLVED*

Lab: Access control

Access controls are designed to prevent users from interacting with data or functionality for which they don't have the relevant permissions. Due to the obvious security impact, broken access controls are critical bugs in their own right. They often also provide access to more attack surface, which could contain additional vulnerabilities.


Purpose: 

Obtain administrative privileges via modification of the admin cookie through burpsuite and deleting the user "carlos"

Analysis: 
    
1.) The first thing I did was log into the provided user "wiener:peter" and using burp, see the http request. 

2.) Highlighting the /login and sending it to the repeater, I was able to see the admin "false" cookie ID.

3.) Modifying the result to "true" provided the admin cookie ID to be able to log into the "Admin Tools" page. 

4.) Using the "Inspect" function of the browswer, navigating to "Application" and "Cookies" I was able to modify the credentials from "false" to "true" and close out the inspector. 

5.) Clickin on the "My Account" link, once the website refreshed, I had access to the "Admin Tools" page, and therefore able to delete the user "Carlos"

Remediation: 
    
1.) I do not know how to fix this, yet.