Portswigger Lab #4 OCT152023 *SOLVED = No cheating or looking at solutions*

Lab: Horizontal Privilege Escalation

    Horizontal privilege escalation occurs if a user is able to gain access to resources belonging to another user, instead of their own resources of that type. For example, if an employee can access the records of other employees as well as their own, then this is horizontal privilege escalation.

    Horizontal privilege escalation attacks may use similar types of exploit methods to vertical privilege escalation. 

<b>Note</b>
<b>*This is an example of an insecure direct object reference (IDOR) vulnerability. This type of vulnerability arises where user-controller parameter values are used to access resources or functions directly.*</b>

Purpose: 

    1.) Gain access to resources that other users do and not necessarily administrative.

    2.) There is a vulnerability that identifies users with GUID's. I am to log into the "Account" page, and using the vulnerability, submit Carlos' API key for the completion of the lab.

Analysis: 
    
    1.) I accessed the lab and clicked on the Account link.

    2.) Loggin in, I am greeted with my API key: Your API Key is: XmMwZb9jyXP4lumTuNihqEYQFHg6doY2

    3.) I take note of the URL that has my ID number in it: https://0a6a006d04a6f5f180088099009b0008.web-security-academy.net/my-account?id=468510b6-ac61-426f-bb6c-63891368ea38

    4.) My initial thinking is to use what I've learned about admin access, so I am going to obtain administrative access via user request control parameter.

    5.) I see that there is a session cookie, but nothing pops out as an administrative session. 

    6.) I try to modify the account ID with an asterisk (*) but that just gets me a 302 Found error.

    7.) Going back to the learning portion of the lab, I see at the bottom where it mentions, "However, the GUIDs belonging to other users might be disclosed elsewhere in the application where users are referenced, such as user messages or reviews."

    8.) Using that train of thought, staying logged in as wiener, I look around the webpage for reviews or mentions of carlos that might allow me to see his account ID.

    9.) The first thing I see is a blog post by Carlos, with the user ID in the URL: https://0a6a006d04a6f5f180088099009b0008.web-security-academy.net/blogs?userId=f38c7d02-f5e6-483b-93a8-9c9dd13433a1

    10.) Knowing that I have to submit his API key as the answer, I am on the right track.

    11.) I initially think that I am going to have to try another tactic, when I notice the "submit solution" button at the top. I copy the user ID and submit that as the solution.

    12.) Submitting that is incorrect.

    13.) HOWEVER, I thought the go back to my account page, and instead of my user ID, I cut that out and pasted his ID on the URL. 

    14.) This allowed me to view his API Key: AppAXKymLtGSA1aCfVsYapckzkTv6zLI



Remediation: 
    
    1.) Yet again, do not know how to remediate.