Portswigger Lab #5 OCT152023 

Lab: User ID controlled by request parameter with password disclosure 
    
Often, a horizontal privilege escalation attack can be turned into a vertical privilege escalation, by compromising a more privileged user. For example, a horizontal escalation might allow an attacker to reset or capture the password belonging to another user. If the attacker targets an administrative user and compromises their account, then they can gain administrative access and so perform vertical privilege escalation.

An attacker might be able to gain access to another user's account page using the parameter tampering technique already described for horizontal privilege escalation:

        https://insecure-website.com/myaccount?id=456

If the target user is an application administrator, then the attacker will gain access to an administrative account page. This page might disclose the administrator's password or provide a means of changing it, or might provide direct access to privileged functionality.


Purpose: 

1.) Being able to horizontally move to another user's credentials, with the intent of obtaining admin access at the same time.

Analysis: 
    
1.) I initially logged into the wiener:peter account and saw that the URL at the end just had the user name. 

2.) Understanding that Carlos is essentially being picked on over and over again, I changed the name at the end to Carlos to see what would happen.

3.) I was greeted with his account panel, with the ability (I thought) to change his password. I changed it to peter, like the wiener account but was unable to log into the account with the new password. 

4.) Looking at burpsuite, I was able to see his password (so2zv2m77cn8es950gu9) and logged into the account that way. 

5.) I am thinking that the very first path traversal attack to obtain user names might be the key to finding a user with admin credentials.

6.) Unfortunately, I am plagued yet again by the intercept on burpsuite being turned on, and the webpage not responding or lagging. When I turn intercept off, it works just fine.

7.) After using the community solution, and logging into the account wiener:peter, I did notice the first time that the password had a value associated with it. In this way, a vulnerability on its own, showed the number of characters in the password. When I earlier logged into Carlos' account, I did notice that his password was longer. However, the solution pointed me to "inspect" the element, that shows the password in clear text when inspected in HTML.

8.) Earlier when trying to change to Carlos' account, I DID try to see about getting an administrator panel to showup by editing the user ID at the end to admin. But, I DIDN'T try administrator. Using what I just saw, I inspected the password and saw this: yfdx7xmpyvtiqsmzqgaq.

9.) Using Burpsuite, I sent a request to go back to my account and capture the traffic. Using the repeater function, I changed my ID to administrator, much like I did above in the URL. The 200 traffic came back, which is a good sign, and on line 55 of the HTML I see that my username is administrator (as expected) and the password being: yfdx7xmpyvtiqsmzqgaq 

10.) The above password coincides with what I saw using the "inspect" function of the browser.

11.) Going further, now I have the username and password and logged out of the wiener account and logged onto the administrator account. Thus solving the lab. 

<b>KEY TAKEAWAYS:</b>

a. I *definitely* need more practice with the burpsuite software.
        
b. While my line of thinking was probably on track in regards to trying to utilize some of what I've learned so far with the path trajectory and so on, the actual solution was much simpler than I was thinking. Following along with the solution, I was able to see that my lack of understanding of what burpsuite does made it seem like I was having certificate issues with the default browser, which is simply not the case. 
        
c. It's ok to eventually check out the community solution video, however I will always give it a shot and practice my line of thinking about the problem. For the most part, I am getting there with my initial probing.

Remediation: 
    
1. I do not know the remediation steps at this time.