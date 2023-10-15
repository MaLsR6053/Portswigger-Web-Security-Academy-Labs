Portswigger Lab #1 OCT132023 *SOLVED*

Lab: Path Traversal (simple case)

Path traversal (also known as directory traversal) vulnerabilities enable an attacker to interact with arbitrary files on the server, giving them access to sensitive data. If they can also write to these files, they can potentially modify application data or behavior, ultimately taking full control of the server.

Purpose: 
    Read arbitrary files via path traversal

Analysis: 

1.) My initial thought to add ../../../etc/passwd was on the right track, having never done it before. 
    
2.) Getting "not found" error messages, I should have just added more "../../" until I got what I was looking for, but I tried using the Windows Server "windows.ini" at the end to see if that would work. It did not.
    
3.) After adding more "../../" to the end of the URL, I was able to come up with a message that essentially told me that I was on the right track. Up to this point, I did not know or use burpsuite.
    
4.) Searching online for a clue before utilizing the solutions provided by the academy, I was advised to use burp to see and modify the "Image?file=*" attribute and intercept the requests to be able to send a repeated and modified request "../../../../../etc/passwd" to obtain the output of users for the website.

Remediation:
 
1.) I do no know how to remediate this yet.