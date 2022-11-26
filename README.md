# 2420_week12_Lab

#### Robeen, Ajana

# Starting Off

To begin download our repo which includes 2 files 

- A NGINX file named [IP ADDRESS] <-- Change this for your IP address

- A template HTML file

## NGINX

We will start with the NGINX install

  1. Connect/login into the device that will act as a server

  2. Run the command `sudo apt install nginx`
  
  3. You should see ![apt install nginx](/images/aptinstall.png)

## Test NGINX

To test if NGINX is running normally:

  1. Run the command `systemctl restart nginx.service`

  2. You should see this:
  
![NGINX status](/images/nginxstatus.png)

The `active (running)` indicates all is good

## Install NGINX file

**If you want to use the file provided skip #2 & #4 but make sure to follow #3**

  1. On the server, run `sudo mkdir -p /etc/nginx/sites-avilable/[IP ADDRESS]`
  
![directory creation](/images/nginxlocation.png)

  2. Run `sudo vim /etc/nginx/sites-avilable/[IP ADDRESS]`  
  
![pre vim](/images/makenginxfile.png)

  3. Add content to file, **MAKE SURE TO CHANGE THE IP**:
  
![nginx file preview](/images/nginxfile.png)

  4. Also can `sudo vim [IP ADDRESS]` followed with `sudo mv [IP ADDRESS] /etc/nginx/sites-avilable/[IP ADDRESS]`

![nginx mv file after make](/images/movenginxfile.png)

  5. Link the file to another location with `sudo ln -s /etc/nginx/sites-avilable/[IP ADDRESS] /etc/nginx/sites-enabled`

![linking](/images/link.png)

  6. Run `sudo nginx -t` which will show if there are any syntax errors
  
![test nginx](/images/nginxtest.ng.png)

## Install HTML file

**I highly suggest using the file provided and edit as needed**
  
  1. Make a directory for the html doc to live in with `sudo mldir -p /var/www/[IP ADDRESS]/html`
  
  2. Move the downloaded file with `sudo mv index.html /var/www/[IP ADDRESS]/html/`

![move the HTML file](/images/movewebsite.png)

  3. Restart NGINX with `sudo systemctl restart nginx.service`
 
![restart nginx](/images/nginxrestart.png)
  
  4. The website should be accesible from [IP ADDRESS] in your browser
  
   ![good website](/images/website.png)
   
  5. Nice the site is now up
  
## Install Firewall (DO)
  
  1. Click on your droplet
  
  2. Click **Networking**
  
![list of items](/images/droplistfirewall.png)

  3. Click **Edit** under Firewalls
    
![edit firewalls](/images/addfirewall.png)

  4. Clcik **New rule** under Inbound Rules and select **HTTP**
 
![add rule](/images/inboundfirewall.png)
  
  5. Click **Droplets** then **Add Droplets** and find your droplet to add the firewall to it
  
![add droplet](/images/adddroplet.png)

  6. Verify that you can still see the website after reloading and that you can still connect to the droplet through SSH
  
![verify SSH](/images/firewallconnect.png)
