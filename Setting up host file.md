setting up Xampp host file
**First time set up**

> go to: `C:\xampp\apache\conf\extra\httpd-vhosts.conf` go right at the
> bottom and paste:

    NameVirtualHost 127.0.0.1
    <VirtualHost 127.0.0.1> 
        DocumentRoot "C:\xampp\htdocs\
        ServerName localhost
    </VirtualHost>

> then under that paste what file/web-app you want to host replace :
> 
> `websiteurl.kunz` with your personal host name `DocumentRoot
> "C:/xampp/htdocs/locationtofolder"` replace this with your location
> for your website folder in the `htdocs`

    <VirtualHost websiteurl.kunz>
        DocumentRoot "C:/xampp/htdocs/locationtofolder"
        ServerName websiteurl.kunz
        ServerAlias websiteurl.kunz
        <Directory "C:/xampp/htdocs/locationtofold">
            Options Indexes FollowSymLinks Includes ExecCGI
            AllowOverride All
            Order allow,deny
            Allow from all
       </Directory>
    </VirtualHost>


> now go to:   `C:\Windows\System32\Drivers\etc\hosts`
> 
> and paste this right at the bottom

    127.0.0.1 localhost

> and then write your host name that you wrote above in my case its

    websiteurl.kunz

> so my final output for `C:\Windows\System32\Drivers\etc\hosts` should
> look something like:

 

      ... # localhost name resolution is handled within DNS itself.
        #	127.0.0.1       localhost
        #	::1             localhost
        127.0.0.1 localhost
        127.0.0.1 websiteurl.kunz


**Add more Hosts or Websites to Host in local**
> go to: `C:\xampp\apache\conf\extra\httpd-vhosts.conf` go right at the
> bottom and paste:

    <VirtualHost secondWebsite.kunz>
        DocumentRoot "C:/xampp/htdocs/secondlocation"
        ServerName secondWebsite.kunz
        ServerAlias secondWebsite.kunz
        <Directory "C:/xampp/htdocs/secondlocation">
            Options Indexes FollowSymLinks Includes ExecCGI
            AllowOverride All
            Order allow,deny
            Allow from all
       </Directory>
    </VirtualHost>
    
> now go to:   `C:\Windows\System32\Drivers\etc\hosts`
> 
> and paste this right at the bottom
  

    127.0.0.1 secondWebsite.kunz

*now if you enter the host secondWebsite.kunz or websiteurl.kunz in a browser u will be able to go to your webapp that you placed in locations*
