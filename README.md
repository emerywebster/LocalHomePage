### A Local Home Page for OSX Web Development

This is a small and simple local home page that automatically lists, and provide links to, your local sites. It's a companion project for a [blog post](http://mallinson.ca/post/osx-web-development) I wrote about setting up your Mac for web development.


* img/icon-gear.png from [Icons DB](http://www.iconsdb.com/black-icons/gear-2-icon.html)

---

In /private/etc/apache2/httpd.conf:

```
<Directory "/Users/user/Sites">
  Options Indexes MultiViews FollowSymLinks
  AllowOverride All
  Order allow,deny
  Allow from all
</Directory>

<Virtualhost *:80>
  VirtualDocumentRoot "/Users/user/Sites/home"
  ServerName home.dev
  UseCanonicalName Off
</Virtualhost>

<Virtualhost *:80>
  VirtualDocumentRoot "/Users/user/Sites/%1/"
  ServerName sites.dev
  ServerAlias *.dev
  UseCanonicalName Off
</Virtualhost>
```
