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

![sql_injection](https://user-images.githubusercontent.com/34847878/49044738-af1e7080-f19c-11e8-870c-2d7ae98b101d.gif)


Vulnerability #2: Session Hijacking/Fixation

This vulnerabiility lets you log back into the site without having your login info. Just changing the session id from previous session (using previous session's id) would let you log in and letting the attacker to access your useful info.only works for the blue target.

![session_hijackingfixation](https://user-images.githubusercontent.com/34847878/49045041-af6b3b80-f19d-11e8-9043-c328ccc57252.gif)


## Red 
Vulnerability #3: Insecure Direct Object Reference

This vulnerability makes the hidden salesperson IDs accesiable and visible to others.While trying the same thing to green and blue target doesn't respond to anything. 

![insecure_direct_object_reference](https://user-images.githubusercontent.com/34847878/49045069-ca3db000-f19d-11e8-973d-ffac17ffc4d9.gif)


Vulnerability #4 : Cross-Site Request Forgery

Staff database can be access and edit without a csrf token for the red target. While returns an invalid request for blue and green target for doing so. 

![csrf](https://user-images.githubusercontent.com/34847878/49045101-e17c9d80-f19d-11e8-875f-fefb2c310014.gif)

## Green

Vulnerability #5: Username Enumeration

Login Error message text become bolds if the person's user name exist and unbold if it doesn't exist revealing important information to the attacker. 

![username_enumeration](https://user-images.githubusercontent.com/34847878/49045129-fa854e80-f19d-11e8-8c66-10c36ee6cb36.gif)

Vulnerability # 6: Cross-Site Scripting

This takes a script and aplplies it to the feedback section while finish that and try to login agiain the feedack pops up with your name and the XSS runs. Trying it on blue target, the xss doesn't run but still shows the message. 
XSS Script - <script>alert('Mallory found the XSS!');</script>

![css](https://user-images.githubusercontent.com/34847878/49045147-0cff8800-f19e-11e8-8c3a-bd0fda46780d.gif)

## Bonus

## Build on Objective #3 (SQL Injection)

The Green and red site works perfectly for the database query. The user inject SQL code into the sales person page by requesting  salesperson.php?id=?' OR '1=1' which works for the Green and Red but failed when tried for the blue site.
![advanced_objective](https://user-images.githubusercontent.com/34847878/49045168-1daffe00-f19e-11e8-968a-c2aa5ef7fe61.gif)

Created by Nahmida Talukder
