---
layout: page
weight: 0
title: Whitelabel Wizard
navigation:
  show: true
---

{% info %} This feature is available to customers with Silver, Gold, or Platinum accounts. {% endinfo %}


Depending on the set of Apps you have chosen, SendGrid can alter or add links to emails. This includes unsubscribe links, click tracking, and open tracking. In addition, SendGrid adds email headers that reference SendGrid's servers so remote servers can verify the authenticity of emails. These links and headers reference the sendgrid.me or sendgrid.com domain.


{% info %} SendGrid does not host domains. Do not attempt to transfer a domain to SendGrid. If you have already registered a domain, then you have a registrar, and it is likely the hosting company you have your website on. {% endinfo %}
 
{% warning %} Any changes you make to DNS can immediately affect your client's ability to reach your resources. We cannot take any responsibility for any changes you make to DNS, so please be very careful. If you have any questions, please contact our support team. {% endwarning %}
 
{% info %} When in doubt, contact your DNS registrar or web hosting service's technical support department. All information in this document complies with the DNS standards, but some registrars and web hosting providers handle things differently. {% endinfo %}


SendGrid allows companies to customize the domain that appears, a process called Whitelabeling. SendGrid does this using a subdomain for your domain. For example, if your domain is EXAMPLE.COM, you might use EMAIL.EXAMPLE.COM, where EMAIL is your sub-domain.

Your first step is to choose a subdomain. Common examples are EMAIL, MAIL, CONTACT, NEWS, NEWSLETTER, but you can make it anything you like. Now you just need to run the Whitelabel Wizard from your account and the wizard will generate the DNS records you need to add to your DNS entries. Below are links to some hosting and domain name registrars that you might be using.


{% info %} The hosting company 1&1 does not support TXT records, so SPF cannot be specified and therefore is not supported by SendGrid. {% endinfo %}


||
|GoDaddy|[Configure DNS using CPanel](http://support.godaddy.com/help/4597/setup-dns-using-cpanel)   
 [Configure DNS using Plesk Panel 9](http://support.godaddy.com/help/198/setting-up-dns-with-your-parallels-plesk-panel-9-server-and-domain-with-us)   
 [Configure DNS using Plesk Panel 10](http://support.godaddy.com/help/6891/setting-up-dns-with-your-parallels-plesk-panel-10-server-and-domain-with-us)   
[-Watch a video!-](http://screencast.com/t/tip4j5ce6b)|
|Bluehost|[Instructions on how to configure DNS using cPanel on BlueHost](https://my.bluehost.com/cgi/help/559)|
|Dreamhost|[Instructions on how to configure custom DNS on DreamHost](http://wiki.dreamhost.com/Custom_DNS)|
|Hover|[Instructions on how to edit your DNS configuration on Hover](https://www.hover.com/help/edit-dns-records-cname-mx-txt-and-srv)|


{% warning %} It is critical that you select a subdomain that does not already exist. MAIL is a common subdomain. If you do not have access to your domain registrar, check with your service administrator. {% endwarning %}
 
{% anchor h2 %} Whitelabel Wizard {% endanchor %}


Our Whitelabel Wizard makes it easier to setup your Whitelabel by walking you through the necessary steps and verifying your settings along the way. You can access the Whitelabel Wizard by navigating to the "Developers" menu and choosing "Whitelabel"

![]({{root_url}}/images/whitelabel_1.png "sg_wlwiz_start")


{% info %} The Whitelabel Wizard provides you with your static IP address. {% endinfo %}
 
{% anchor h3 %} DNS Records {% endanchor %}


The following records are needed for links, SPF, DomainKeys, and DKIM to work correctly.

<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
location

</th>
<th markdown="1">
type

</th>
<th markdown="1">
value

</th>
</tr>
<tr markdown="1">
<td markdown="1">
email.example.com.

</td>
<td markdown="1">
CNAME

</td>
<td markdown="1">
sendgrid.net.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
example.com.

</td>
<td markdown="1">
TXT

</td>
<td markdown="1">
v=spf1 a mx include:sendgrid.net \~all

</td>
</tr>
<tr markdown="1">
<td markdown="1">
smtpapi._domainkey.example.com.

</td>
<td markdown="1">
CNAME

</td>
<td markdown="1">
dkim.sendgrid.net.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
smtpapi._domainkey.email.example.com.

</td>
<td markdown="1">
CNAME

</td>
<td markdown="1">
dkim.sendgrid.net.

</td>
</tr>
</tbody>
</table>

{% info %} If you already have an SPF record, you can simply add include:sendgrid.net to this entry. Make sure to add it BEFORE the "all" mechanism as "all" always matches and typically goes at the end of the SPF record. {% endinfo %}
 **Underscore Problems?**

If your DNS server does not allow underscores in CNAMES you will have problems adding the smtpapi._domainkey CNAME records. If that is the case please create the following TXT records instead:

<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
location

</th>
<th markdown="1">
type

</th>
<th markdown="1">
value

</th>
</tr>
<tr markdown="1">
<td markdown="1">
smtpapi._domainkey.example.com.

</td>
<td markdown="1">
TXT

</td>
<td markdown="1">
See Below.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
smtpapi._domainkey.email.example.com.

</td>
<td markdown="1">
TXT

</td>
<td markdown="1">
See Below.

</td>
</tr>
</tbody>
</table>
DomainKey Value:

{% codeblock %} k=rsa; t=s; p=MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDPtW5iwpXVPiH5FzJ7Nrl8USzuY9zqqzjE0D1r04xDN6qwziDnmgcFNNfMewVKN2D1O+2J9N14hRprzByFwfQW76yojh54Xu3uSbQ3JP0A7k8o8GutRF8zbFUA8n0ZH2y0cIEjMliXY4W4LwPA7m4q0ObmvSjhd63O9d8z1XkUBwIDAQAB {% endcodeblock %} 
{% anchor h2 %} Dedicated IP Setup {% endanchor %}


SendGrid allows you to have your own dedicated IP address to help build your own reputation. These IPs need to be mapped to real names. SendGrid handles the mapping of an IP to a name, reverse DNS records (RDNS), and expects the mapping of the name to match the IP in the RDNS record. Please use the Whitelabel Wizard or contact support for the IPs and the names needed to be setup. In this case, an IP of 192.168.2.1 has been given the name o1.email.domain.com. SendGrid assigns the mapping of 192.168.2.1 to o1.email.example.com, and the following A record is needed to map o1.email.domain.com to 192.168.2.1:

<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
location

</th>
<th markdown="1">
type

</th>
<th markdown="1">
value

</th>
</tr>
<tr markdown="1">
<td markdown="1">
o1.email.example.com.

</td>
<td markdown="1">
A

</td>
<td markdown="1">
192.168.2.1

</td>
</tr>
</tbody>
</table>

