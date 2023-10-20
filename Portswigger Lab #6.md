Portswigger Lab #6 20OCT2023 Solved

Lab: Username enumeration via different responses


Purpose: This lab is vulnerable to username enumeration and password brute-force attacks. It has an account with a predictable username and password, which can be found in wordlists that are provided.


Analysis: 

1.) The first thing I decided to do was to complete this task via the Kali VM, instead of my Ubuntu host.

2.) Using the solution, I was directed to open burpsuite, and log into the lab via the burp browser.

3.) After accessing the lab, trying a random username and password combination yielded the expected login error.

4.) Back in burp, I looked at the http logs and saw the /login POST.

5.) Sending that line to the Intruder feature, I cleared out the screen and using the "sniper" attack function, highlighted my incorrect username and under Payload, copy and pasted the provided username list. The list had 101 names on it.

6.) Running the attack took about 2 minutes, due to the throttling of the feature while using the Community edition. 

7.) Sorting the output via "length", I can see that "ae" is a different number than the rest of the usernames supplied on the list.

8.) Going back to the original http output, I change the username to "ae" and repeat the process for the password by sending that line to the intruder feature and supplying it with the list of possible passwords. 

9.) Upon completion of that task, the password "hunter" has a different length than the rest of the supplied passwords. 

10.) Going back to the main login page, I use "ae" for the username and "hunter" for the password and am able to log into that account, thus completing the lab.

Remediation: 
    