---
layout: page
weight: 0
title: Exim
navigation:
  show: true
---

{% warning %} Versions of Exim prior to the current major release are considered obsolete. If you are using Exim 3.x or earlier it is suggested by the Exim development team that you upgrade to the current release. {% endwarning %}


The following configuration file, which can be found at **/etc/exim4/update-exim4.conf.conf**, was pulled from Ubuntu Server 10.4 and is for example purposes only:

{% codeblock lang:bash %} dc\_eximconfig\_configtype='smarthost' dc\_other\_hostnames='' dc\_local\_interfaces='127.0.0.1' dc\_readhost='your.server.name' dc\_relay\_domains='' dc\_minimaldns='false' dc\_relay\_nets='' dc\_smarthost='smtp.sendgrid.net::587' CFILEMODE='644' dc\_use\_split\_config='false' dc\_hide\_mailname='true' dc\_mailname\_in\_oh='true' {% endcodeblock %}

Enable TLS support in **/etc/exim4/exim4.conf.localmacros**.

  
 
{% info %} If this file does not exist, you will need to create it: {% endinfo %}
 {% codeblock lang:bash %} MAIN\_TLS\_ENABLE = 1 {% endcodeblock %}

Enter credentials that will allow Exim to access SendGrid in **/etc/exim4/passwd.client**:

{% codeblock lang:bash %} \*:sendgridusername:sendgridpassword {% endcodeblock %}

Once you have completed and saved all changes to Exim's configuration files, you will need to restart it to activate those changes:

{% codeblock lang:bash %} \$ /etc/init.d/exim4 restart {% endcodeblock %} 
{% anchor h2 %} cPanel {% endanchor %}


If you are using cPanel with Exim and want to relay your email through SendGrid, go to **Main \> Service Configuration \> Exim Configuration Editor**, click on the Advanced Editor button, and enter the following:

{% codeblock lang:bash %} begin authenticators sendgrid\_login: driver = plaintext public\_name = LOGIN client\_send = : username@example.com : YourSendGridPassword {% endcodeblock %} 
{% info %} Only include "begin authenticators" if it's not already in the configuration. {% endinfo %}


Add a route in the **Router Configuration** Box:

{% codeblock lang:bash %} send\_via\_sendgrid: driver = manualroute domains = ! +local\_domains transport = sendgrid\_smtp route\_list = "\* smtp.sendgrid.net::587 byname" host\_find\_failed = defer no\_more {% endcodeblock %}

Add a transport to the **Transport Configuration** Box:

{% codeblock lang:bash %} sendgrid\_smtp: driver = smtp hosts = smtp.sendgrid.net hosts\_require\_auth = smtp.sendgrid.net hosts\_require\_tls = smtp.sendgrid.net {% endcodeblock %}

Once you have completed and saved all changes to Exim's configuration files, you will need to restart it to activate those changes:

{% codeblock lang:bash %} \$ /etc/init.d/exim4 restart {% endcodeblock %}
