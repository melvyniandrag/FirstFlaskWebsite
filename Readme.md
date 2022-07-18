# Simple Flask + Apache2 + Debian 11 Website

First install some stuff:

```
root@machine$ apt install python3-dev apache2 libapache2-mod-wsgi-py3 python3-pip
root@machine$ pip3 install flask
```

## Deploy your first website:

Clone this repo to your server

`mv Code /var/www/html`

`cp ConfigFiles/WebsiteThatReturnsHTML.conf /etc/apache2/sites-available`

`a2dissite 000-default.conf`

`a2ensite WebsiteThatReturnsHTML.conf`

`service apache2 restart`

Done!

Then if you want you can edit /var/www/html/Code/my_flask_site.py to change what is shown on your website.

## HTTP vs HTTPS
This is an HTTP site. You will probably see something like "not secure" in your browser when you go to your website. If you want HTTPS - like if you plan on gathering credit card data or personal information from the people going to your website, you will need to change some settings in another `.conf` file that deals with port 443. You will see a default-ssl.conf in /etc/apache2/sites-available. You can use this is a template and do some reading on the internet to get the right security settings for your site.

