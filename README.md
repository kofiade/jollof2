script to deploy nginx and kofijollof2

#!/bin/bash

# Update the package list and install updates
sudo apt update
sudo apt upgrade -y

# Install Nginx
sudo apt install nginx -y

# Clone the GitHub repository
git clone https://github.com/kofiade/jollof2

# Move into the cloned directory
cd jollof2

# Copy the contents of the repository to the Nginx www directory
sudo cp -r * /var/www/html/

# Open up port 80 in the firewall (UFW)
sudo ufw allow 80

# Reload UFW to apply the changes
sudo ufw reload

# Display a message indicating the installation is complete
echo "Ubuntu updates installed, Nginx installed, GitHub repository cloned, contents uploaded to Nginx www directory, and port 80 opened successfully!"
