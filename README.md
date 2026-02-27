# sqlinjection
Exploiting SQL Injection vulnerability
```
NAME: SANTHOSH S
REG.NO: 212224100052
```

# AIM:
To exploit SQL Injection vulnerability using Multidae web application in Metasploitable2

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode


### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

SQL Injection is a sort of infusion assault that makes it conceivable to execute malicious SQL statements. These statements control a database server behind a web application. Assailants can utilize SQL Injection vulnerabilities to sidestep application safety efforts. They can circumvent authentication and authorization of a page or web application and recover the content of the whole SQL database. 
Identify IP address using ifconfig in Metasploitable2
## OUTPUT
<img width="727" height="414" alt="Screenshot 2026-02-27 083331" src="https://github.com/user-attachments/assets/d8c1091e-3cf4-43b5-b04c-d857d2dbd592" />


Use the above ip address to access the apache webserver of Metasploitable2 from kali/parrot linux. In Kali Linux use the ip address in a web browser.
##  OUTPUT
<img width="1920" height="1200" alt="Screenshot (41)" src="https://github.com/user-attachments/assets/533ef683-1d1f-4757-910b-668bafa52628" />


Select Multidae from the menu listed as shown above. The page is displayed as below:
##  OUTPUT
<img width="1920" height="1200" alt="Screenshot (50)" src="https://github.com/user-attachments/assets/55c97c5b-9f6b-4ae6-af45-67573602fff9" />



Click on the menu Login/Register and register for an account
##  OUTPUT
<img width="1920" height="1200" alt="Screenshot (41)" src="https://github.com/user-attachments/assets/0f6fd661-fd33-44f4-8060-faebbf556418" />



Click on the link “Please register here”
##  OUTPUT
<img width="1920" height="1200" alt="Screenshot (41)" src="https://github.com/user-attachments/assets/b57b1f2d-3575-4427-b191-666d6ad26798" />



Click on “Create Account” to display the following page:
##  OUTPUT
<img width="1920" height="1200" alt="Screenshot (42)" src="https://github.com/user-attachments/assets/7bfbef96-b7d8-4913-b24d-2fa9be21da21" />


The login structure we will use in our examples is straightforward. It contains two input fields (username and password), which are both vulnerable. The back-end content creates a query to approve the username and secret key given by the client. Here is an outline of the page rationale:


($query = “SELECT * FROM users WHERE username=’$_POST[username]’ AND password=’$_POST[password]’“;).
 For the username put “ganesh” or “anything” and for the password put (anything’ or ‘1’=’1) or (admin’ or ‘1’=’1) then try to log in, and you’ll be presented with an admin login page.
##  OUTPUT
<img width="1920" height="1200" alt="Screenshot (46)" src="https://github.com/user-attachments/assets/bf4bb03e-98e7-4730-b766-ada3b3d09fd4" />



Click “Login”. The logged in page will show as below:
##  OUTPUT
<img width="1920" height="1200" alt="Screenshot (49)" src="https://github.com/user-attachments/assets/9de09c04-89d6-4437-84fa-2c53121704e7" />



If error faced in registration follow the following steps in metasploitable 2:
<img width="1043" height="291" alt="Screenshot 2026-02-27 084441" src="https://github.com/user-attachments/assets/4e474c82-d127-4c91-90ef-e10c69a15c59" />


This issue is caused by a misconfiguration in the config.inc located in the /var/www/mutillidae folder on Metasploitable 2 VM.

Edit config.inc
Edit config.inc file located in /var/www/mutillidae folder on Metasploitable 2 by typing the following commands [one at the time]:
cd /
sudo nano /var/www/mutillidae/config.inc
Type msfadmin when prompted for the root password. 
Once nano opens config.inc file, look for the line $dbname = ‘metasploit’ as shown in Figure  below:
##  OUTPUT
<img width="738" height="414" alt="Screenshot 2026-02-27 084753" src="https://github.com/user-attachments/assets/87d09f65-e6db-4bb8-a5b5-687131fe755b" />


Replace ‘metasploit’ with ‘owasp10’ and make sure the lines end with semicolon ; as shown in Figure


Save and exit the config.inc
Save than exit the config.inc file by typing CTRL+X keys on your keyboard and the Y [Enter] when prompted to save the file
Restart the Apache server
To restart Apache, type the following command in the terminal. Alternatively, you can just reboot Metasploitalbe 2 VM.
sudo /etc/init.d/apache2 reload
##  OUTPUT
<img width="751" height="174" alt="Screenshot 2026-02-27 094813" src="https://github.com/user-attachments/assets/36268c92-b6b8-4aa9-880c-cf5a61aa5341" />




# Reset Mutillidae database
Refresh the page then clicking on the Reset DB menu option to reset the Mutillidae database [Figure ]. Click OK when prompted.




# Test the new configuration
Alright. Now is time to test if we managed to fix the database issue. Go ahead and register a new account on the Mutillidae webpage.

 The Mutillidae database error no longer appears 



Now after logging out you will see the login page. In the login page give ganesh’ # (myusername). You can see the page now enters into the administrator page as before when giving the password.
## OUTPUT
<img width="1920" height="1200" alt="Screenshot (46)" src="https://github.com/user-attachments/assets/3e90f73a-8b19-4603-a028-0a089877b7c2" />


Click the login button and you will see it enter into the administrator page.
## OUTPUT
<img width="1920" height="1200" alt="Screenshot (48)" src="https://github.com/user-attachments/assets/2d0be6ab-6c4c-481c-98a8-16b56f522b2a" />



## RESULT:
The SQL Injection vulnerability is successfully exploited using the Multidae web application in Metasploitable2.
