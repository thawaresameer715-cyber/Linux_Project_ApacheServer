# Demo Script (for EC2)

vi demo_script.sh

# Use sudo while executing the shell-file:
sudo ./demo_script.sh


# Shell-script:

#!/bin/bash

# Update package list
sudo apt update && sudo apt upgrade -y

# Install Apache
apt install apache2 -y

# Start and enable Apache
systemctl start apache2
systemctl enable apache2

#copy from github
git clone https://github.com/thawaresameer715-cyber/Linux_Project_ApacheServer.git

#installing unzipping tool
sudo apt install unzip

#Moving into project dirictory
cd /home/ubuntu/Linux_Project_ApacheServer

#Renaming
mv 'Zay eCommerce website files.zip' Zay_ecommerce.zip

# unziping
unzip Zay_ecommerce.zip

#Renaming
mv 'Zay eCommerce website files' Z_ecommers

# Remove default Apache page
rm -f /var/www/html/*

# Copy project files
cp -r /home/ubuntu/Linux_Project_ApacheServer/Z_ecommers/* /var/www/html/

# Restart Apache
systemctl restart apache2

echo "Deployment completed successfully."
