# Filmtagging
<p>Filmtagging is a crowdsourced tag collection platform in which tags can be gathered over films and users are able to export the tags to use for various research activities. This platform was used for my master thesis and is now available for anyone who want's to use it.</p>

<b><title>Setup for annotation platform FILMTAGGING</title></b>

<b>Install and prep Linux server</b>

<p><b>Step 1.</b> Start by updating your repositories of you Linux environment:</p>
  
  <i><p>sudo apt-get update</p></i>
<b>Step 2.</b> Install apache server: 
  
 <i><p>sudo apt-get install apache2</p></i>
<b>Step 3.</b> Check if the apache server is installed correctly by going to your browser and type localhost, If the following message is show the server is installed correctly:
  
  <i><p>It works!<br>
  This is the default web page for this server.<br>
  The web server software is running but no content has been added, yet.</p></i>
  
This page called index.html can be found in the following directory:
  <i>/var/www</i>
  
To stop, start, or restart the apache web server you can use the following command:<br>

  <i>sudo /etc/init.d/apache2 stop</i><br>
  <i>sudo /etc/init.d/apache2 start</i><br>
  <i>sudo /etc/init.d/apache2 restart</i><br>

<b>Step 4.</b> Install PHP:

  <i>sudo apt-get install php5 libapache2-mod-php5</i>

<b>Step 5.</b> Check if PHP was installed correctly by creating a php file:

  <i>sudo touch /var/www/test.php</i>
  
and then edit the file:

  <i>sudo nano /var/www/test.php</i>

This will open a text editor, in which you need to type the following:

  <i><?php phpinfo(); ?></i>
  
Now go to your browser and type localhost/test.php if a page opens php is installed correctly. Now remove the file with the following command:
  
  <i>sudo rm /var/www/test.php</i>

<b>Step 6.</b> Install MySQL:

  <i>sudo apt-get install mysql-server</i>

<b>Step 7.</b> Install phpMyAdmin:

  <i>sudo apt-get install libapache2-mod-auth-mysql php5-mysql phpmyadmin</i>

<b>Step 8.</b> Create symbolic link for phpMyAdmin:

  <i>sudo ln -s /usr/share/phpmyadmin /var/www/phpmyadmin</i>
  
Go to the browser and type in localhost/phpmyadmin, if the phpMyAdmin environment opens it is installed correctly. Now login with the username and password you used through the installation process.

<b>Step 9.</b> Download filmtagging database.sql 

<b>Step 10.</b> Create new empty database in phpmyadmin and name it "annotation"

<b>Step 11.</b> Open the "annotation" database and click import on the top of the page and select the filmtagging database.sql

Now the following tables should be added :
<ul>
<li>skills</li>
<li>users</li>
<li>users_annotations</li>
<li>videos</li>
</ul>

<b><heading>Setup FILMTAGGING platform</heading></b>

<b>Step 1.</b> Download the filmtagging platform.zip

<b>Step 2.</b> Remove the index.html file:

  <i>sudo rm /var/www/index.html</i>

<b>Step 3.</b> Place the entire contents of the FILMTAGGING folder in the “www” directory, and restart the server with the following command:
  
  <i>sudo /etc/init.d/apache2 restart</i>

<b>Step 4.</b> Login in the phpMyAdmin environment and import the annotation.sql file

<b>Step 5.</b> Go to localhost in the browser and see if the platform is running.
  
<b><heading>Customize FILMTAGGING platform</heading></b>

The FILMTAGGING platform has a few folders that contain different parts of the platform:
  <ul>
  <li>Views: in this folder the actual design, content, and layout of the different pages is present. This is done with Bootstrap, HTML, CSS, and JavaScript.</li>
  <li>Ajax: in this folder handles all the forms that are submitted through Ajax on the pages. These files are all written in PHP.</li>
  <li>Controllers: in this folder data extraction from the server is handled for the different pages. These files are all written in PHP.</li>
  <li>Snippets: this folder contains the header and footer of all the pages. This is done with Bootstrap, HTML, and CSS.</li>
  <li>Images: this folder contains all the images used on the site.<br>
  </ul>
