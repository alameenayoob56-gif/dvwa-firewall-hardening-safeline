DVWA Firewall Hardening Using Safeline WAF | Ubuntu + Apache2 + MariaDB

This project demonstrates how I deployed and secured Damn Vulnerable Web Application (DVWA) by configuring a complete web server stack on Ubuntu and integrating Safeline Web Application Firewall (WAF) to detect and block real attacks such as SQL Injection, XSS, CSRF, and Brute-force attempts.


---

🚀 Project Summary

Installed & configured Ubuntu, Apache2, PHP, MariaDB

Deployed DVWA under /var/www/html

Changed Apache default port 80 → 8080

Added custom host: dvwa.local

Applied correct file permissions for DVWA

Set up database configuration manually

Installed and integrated Safeline WAF

Added DVWA as a protected application in Safeline

Performed attacks (SQLi, XSS, Brute-force)

Verified that Safeline detected and blocked malicious requests



---

🛠 Tech Stack Used

Component	Technology

OS	Ubuntu (VirtualBox)
Web Server	Apache2
Database	MariaDB
Language	PHP
Application	DVWA
Firewall / WAF	Safeline
Tools used	terminal, nano, browser



---

📦 Installation Steps

1. Install Apache2

sudo apt update
sudo apt install apache2 -y

2. Install PHP & modules

sudo apt install php php-mysqli php-gd php-xml php-curl -y

3. Install MariaDB

sudo apt install mariadb-server -y

4. Clone DVWA

cd /var/www/html
sudo git clone https://github.com/digininja/DVWA.git dvwa


---

🔧 File Permissions

sudo chown -R www-data:www-data /var/www/html/dvwa
sudo chmod -R 755 /var/www/html/dvwa


---

🌐 Change Apache Port 80 → 8080

Edit:

sudo nano /etc/apache2/ports.conf

Change to:

Listen 8080

Edit virtual host:

sudo nano /etc/apache2/sites-available/000-default.conf

Change:

<VirtualHost *:8080>

Restart Apache:

sudo systemctl restart apache2


---

🏠 Set Custom Host (dvwa.local)

Edit:

sudo nano /etc/hosts

Add:

127.0.0.1   dvwa.local


---

🛡 Safeline Firewall Configuration

1. Install Safeline (GUI installer)


2. Login to dashboard


3. Add DVWA as new application:

Type: Web application

Protocol: HTTP

Port: 8080



4. Enable all security modules


5. View real-time logs




---

🔥 Attack Testing

Performed tests:

SQL Injection

Cross-Site Scripting (XSS)

Command Injection

File Upload bypass attempt

Brute-force login attack


Result:
Safeline WAF successfully blocked malicious payloads and logged alerts.


---

📸 Screenshots (Coming Soon)

DVWA homepage

Apache running on port 8080

Safeline dashboard

Attack logs (SQLi, XSS detected)



---

📁 Repository Structure

/configs          → Apache, hosts, notes
/screenshots      → All images of setup
README.md         → Project documentation


---

🧑‍💻 Author

Al Ameen A
Cybersecurity Enthusiast | Web Security | Linux | WAF


---

⭐ Support

If you found this useful, please ⭐ star the repository!


---
