# Virtual Private Server
---
## Rent a VPS in a public cloud
- Linod
- Digital Ocean
- Heroku ()

## Basics
[Linux Setup](/linuxSetup.md)

[javaScript Setup](/javaScript.md)

## Process Manager 2 setup

```bash
# Install process manager 2 so you can run Node in a process
npm i -g pm2
# Run the index.js file under the management name of api
pm2 start index.js -n api
# Run pm2 when the server reboots
pm2 startup ubuntu
```
## Nginx 
Nginx as a reverse proxy setup
```bash
sudo apt instll nginx
cd /etc/nginx/acitve/sites-available
``` 

`vim default`

```bash
server_name <domain>.com www.<domain>.com;

location / {
    proxy_pass https:localhost:5000;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host;
    proxy_cache_bypass $http_upgrade;
}

````
```bash
#Check if the configs above work
nginx -t
# Restart nginx
systemctl restart nginx
```
## Ubuntu Firewall 
UFW Configuration
```bash
ufw enable
ufw allow ssh
ufw allow http
ufw allow https
```
## Certificate Service
- Using Electronic Frontie Foundation's (EFF) Cerbot program.
- Cerbot uses LetsEncrypt Foundation as the CA to generate a Certificate for your supplied domain name.

```
/Linode Website/Domains/Create

/Linode Website/Domains/<domain>.com/NS Records
    - Will show the 5 or so linode dns servers

/NameCheap/<domain>.com/nameServer/Custom/ add the 5 or so linode dns servers

```

```bash
snap install --classic certbot
ln -s /snap/bin/certbot /usr/bin/certbot
# Will ask a bunch of setup questions, domain name etc...
# Certbot will connect it's setlf to Nginx
certbot --nginx
# Test out Renew. You have to renew every 90 days.
certbot renew --dry-run 
```
