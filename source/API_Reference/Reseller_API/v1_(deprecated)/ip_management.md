---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---

{% anchor h2 %} All {% endanchor %}


View all IPs under your account.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|task|Yes|Must be set to *all*.|Retrieve all IPs available for your account.|
|ip|No|Can be a complete or partial IP address.|Filter your search results.|
|system|No|Must be set to *true*.|Include IPs assigned by SendGrid.|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.ip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=al {% endcodeblock %}

### Response


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<ips>
   <ip>255.255.255.0</ip>
   <ip>255.255.254.0</ip>
   <ip>255.255.253.0</ip>
   <ip>255.255.252.0</ip>
</ips>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.ip.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=al {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
{
  "ips": [
    "255.255.255.0",
    "255.255.254.0",
    "255.255.253.0",
    "255.255.252.0"
  ]
}
{% endcodeblock %}


### Response: Error


{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}


* * * * *


{% anchor h2 %} Free {% endanchor %}


A listing of all free IPs under your account. A Free IP is any IP that is not in use by a user or is not linked to an IP grouping.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|task|Yes|Must be set to *free*.|Retrieve all free IPs for your account.|
|ip|No|Can be a complete or partial IP address.|Filter your search results.|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.ip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=fre {% endcodeblock %}

### Response


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<ips>
   <ip>255.255.255.0</ip>
   <ip>255.255.254.0</ip>
   <ip>255.255.253.0</ip>
   <ip>255.255.252.0</ip>
</ips>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.ip.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=fre {% endcodeblock %}

### Response: Success

{% codeblock %} "255.255.255.0","255.255.254.0","255.255.253.0","255.255.252.0" {% endcodeblock %}

### Response: Error


{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}


* * * * *


{% anchor h2 %} Taken {% endanchor %}


A listing of all taken IPs under your account. A Taken IP is any IP that is in use by a user or is linked to an IP grouping.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|task|Yes|Must be set to *taken*.|Retrieve all taken IPs for your account.|
|ip|No|Can be a complete or partial IP address.|Filter your search results.|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.ip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=take {% endcodeblock %}

### Response


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<ips>
   <ip>255.255.255.0</ip>
   <ip>255.255.254.0</ip>
   <ip>255.255.253.0</ip>
   <ip>255.255.252.0</ip>
</ips>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.ip.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=take {% endcodeblock %}

### Response: Success

{% codeblock %} "255.255.255.0","255.255.254.0","255.255.253.0","255.255.252.0" {% endcodeblock %}

### Response: Error


{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}


* * * * *


{% anchor h2 %} Available {% endanchor %}


A listing of all available IPs under your account. An Available IP is any IP that is currently free, or is in use by a user *but* that user is inactive or that is not linked to an IP grouping.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|task|Yes|Must be set to *available*.|Retrieve all available IPs for your account.|
|ip|No|Can be a complete or partial IP address.|Filter your search results.|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.ip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=availabl {% endcodeblock %}

### Response


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<ips>
   <ip>255.255.255.0</ip>
   <ip>255.255.254.0</ip>
   <ip>255.255.253.0</ip>
   <ip>255.255.252.0</ip>
</ips>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.ip.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=availabl {% endcodeblock %}

### Response: Success

{% codeblock %} "255.255.255.0","255.255.254.0","255.255.253.0","255.255.252.0" {% endcodeblock %}

### Response: Error


{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}


* * * * *


{% anchor h2 %} Usage {% endanchor %}


The current breakdown of users who are using your IPs.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|task|Yes|Must be set to *usage*.|Retrieve all IPs in use broken down by user.|
|ip|No|Can be a complete or partial IP address.|Filter your search results.|
|user|No|Can be a complete or part of a username.|Filter your search results.|
|group|No|Can be a complete or part of a group name.|Filter your search results.|
|system|No|Must be set to *true*.|Include IPs assigned by SendGrid.|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.ip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=usage&user=example.com {% endcodeblock %}

### Response


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<ips>
   <entry>
      <ip>255.255.253.0</ip>
      <user>user4@example.com</user>
   </entry>
   <entry>
      <ip>255.255.254.0</ip>
      <user>user4@example.com</user>
   </entry>
</ips>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.ip.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=usage&user=example.com {% endcodeblock %}

### Response: Success

{% codeblock %} {"ip":"255.255.253.0","user":"user4@example.com"},{"ip":"255.255.254.0","user":"user4@example.com"} {% endcodeblock %}

### Response: Error


{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}

