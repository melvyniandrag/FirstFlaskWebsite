# Simple Flask + Apache2 + Debian 11 Website

First install some stuff:

```
root@machine$ apt install python3-dev apache2 libapache2-mod-wsgi-py3 python3-pip git
root@machine$ pip3 install flask
```

## Deploy your first website:

Clone this repo to your server

`git clone https://github.com/melvyniandrag/FirstFlaskWebsite.git`

Then do the following:

`cd FirstFlaskWebsite`

`mv Code /var/www/html`

`cp ConfigFiles/WebsiteThatReturnsHTML.conf /etc/apache2/sites-available`

Now edit  `/etc/apache2/sites-available/WebsiteThatReturnsHTML.conf` so that it has YOUR ip address for the ServerName. Use vim to edit this file. I told you that you need to learn a text editor!

Disable the old apache default page we saw before
`a2dissite 000-default.conf`

Enable your new Flask website
`a2ensite WebsiteThatReturnsHTML.conf`

Restart apache2
`service apache2 restart`

Done! Take out your cellphone and type your ip address into your browser. Your website is there! Congratulations on this major accomplishment.

Then if you want you can edit /var/www/html/Code/my_flask_site.py to change what is shown on your website.

## HTTP vs HTTPS
This is an HTTP site. You will probably see something like "not secure" in your browser when you go to your website. If you want HTTPS - like if you plan on gathering credit card data or personal information from the people going to your website, you will need to change some settings in another `.conf` file that deals with port 443. You will see a default-ssl.conf in /etc/apache2/sites-available. You can use this is a template and do some reading on the internet to get the right security settings for your site.

