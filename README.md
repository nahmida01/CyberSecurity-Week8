# Project 8 - Pentesting Live Targets
> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.
The six possible exploits are:

    Username Enumeration
    Insecure Direct Object Reference
    SQL Injection
    Cross-site Scripting
    Cross-site Request Forgery
    Session Hijacking / Fixation

Each version of the site has been given two of the six vulnerabilities

## Blue

Vulnerability #1 : Sql Injection

This takes place by injecting sql code directly into URL of the  parameter. We insert ' OR SLEEP(5)=0--' after thet php id which makes the page loading for a few seconds and not reponsive, then returning to the same page. We tried it for green target which didn't work and took us to the home page of salesperson. 

https://github.com/nahmida01/CyberSecurity-Week8/blob/master/SQL_injection.gif

Vulnerability #2: Session Hijacking/Fixation

This vulnerabiility lets you log back into the site without having your login info. Just changing the session id from previous session (using previous session's id) would let you log in and letting the attacker to access your useful info.only works for the blue target.

https://github.com/nahmida01/CyberSecurity-Week8/blob/master/Session_HijackingFixation.gif

## Red 
Vulnerability #3: Insecure Direct Object Reference

This vulnerability makes the hidden salesperson IDs accesiable and visible to others.While trying the same thing to green and blue target doesn't respond to anything. 

https://github.com/nahmida01/CyberSecurity-Week8/blob/master/Insecure_Direct_Object_Reference.gif


Vulnerability #4 : Cross-Site Request Forgery

Staff database can be access and edit without a csrf token for the red target. While returns an invalid request for blue and green target for doing so. 

https://github.com/nahmida01/CyberSecurity-Week8/blob/master/CSRF.gif

## Green

Vulnerability #5: Username Enumeration

Login Error message text become bolds if the person's user name exist and unbold if it doesn't exist revealing important information to the attacker. 

https://github.com/nahmida01/CyberSecurity-Week8/blob/master/Username_Enumeration.gif
Vulnerability # 6: Cross-Site Scripting

This takes a script and aplplies it to the feedback section while finish that and try to login agiain the feedack pops up with your name and the XSS runs. Trying it on blue target, the xss doesn't run but still shows the message. 
XSS Script - <script>alert('Mallory found the XSS!');</script>

https://github.com/nahmida01/CyberSecurity-Week8/blob/master/CSS.gif

## Bonus

## Build on Objective #3 (SQL Injection)

The Green and red site works perfectly for the database query. The user inject SQL code into the sales person page by requesting  salesperson.php?id=?' OR '1=1' which works for the Green and Red but failed when tried for the blue site.
https://github.com/nahmida01/CyberSecurity-Week8/blob/master/Advanced_Objective.gif
