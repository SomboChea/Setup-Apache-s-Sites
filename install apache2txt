I use Ubuntu 14.04 to install apache2;

////////////////////////////////
sudo apt-get update
sudo apt-get install apache2
//////////////////////////////
Now start your site via ip:
http://your_server_IP_address

e.g. http://188.33.100.45
////////////////////////////
Or you can show via command:
type --> ip addr show eth0 | grep inet | awk '{ print $2; }' | sed 's/\/.*$//'

////////////////////////////
Now setup a new site with your own domian name:

-Register a new domain with any site. Like, Goddady.com, etc.
-Signup with Cloudflare.com.
-Change Nameserver to Cloudflare nameserver. (Waiting a few time / hours)
-Setting up your domain in cloudcflare to point to your domian name.

//////// Now setting a site in apache2 /////////
-sudo mkdir /var/www/your_folder
-sudo nano /etc/apache2/sites-available/yoursite.com.conf

And copy and paste this :
-------------------------------

<VirtualHost *:80>

	ServerName yourdomain.com
	ServerAlias www.yourdomain.com
	DocumentRoot /var/www/your_folder

	ErrorLog ${APACHE_LOG_DIR}/error.log
	CustomLog ${APACHE_LOG_DIR}/access.log combined

</VirtualHost>

-------------------------------
-Create a new file in www folder:
Type --> sudo nano /var/www/your_folder/index.html

/// In Index.html ///

<!DOCTYPE HTML>
<html>
<head><title>Your Site Tilte</title>
</head>
<body>
<h1> Your site is working now!</h1>
</body>
</html>

///////////////////////////

////Enable your site to host////

-sudo a2ensite /etc/apache2/sites-available/yoursite.com.conf
-sudo service apache2 restart

/// Now you done ///
Enjoy!
