Portswigger Lab #3 OCT152023 *SOLVED*

Lab: User role controlled by request parameter

Purpose: Parameter-based access control methods
    Some applications determine the user's access rights or role at login, and then store this information in a user-controllable location. This could be:

    - A hidden field.
    - A cookie.
    - A preset query string parameter.
    
    The application makes access control decisions based on the submitted value.

Analysis: 
    1.) I was able to log into my account wiener:peter and using burpsuite able to modify the administrative privileges from false to true and copy the session cookie ID. 

    2.) Using the new ID, I was then therefore able to obtain administrative rights by resending the data after right clicking "inspect" and navigating to the "application" pane, and then modifying the administrative rights from false to true under "cookies". Then, after closing the "inspect" panel I was able to click on "My Account" and access the admin panel to delete Carlos.

Remediation: 
    1.) I have no clue to how to fix this yet.