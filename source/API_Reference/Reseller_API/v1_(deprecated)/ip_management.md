---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---

{% anchor h2 %} All {% endanchor %}


View all IPs under your account.

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>all</em>
            .
         </td>
         <td>Retrieve all IPs available for your account.</td>
      </tr>
      <tr>
         <td>ip</td>
         <td>No</td>
         <td>Can be a complete or partial IP address.</td>
         <td>Filter your search results.</td>
      </tr>
      <tr>
         <td>system</td>
         <td>No</td>
         <td>
            Must be set to
            <em>true</em>
            .
         </td>
         <td>Include IPs assigned by SendGrid.</td>
      </tr>
   </tbody>
</table>


### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.ip.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=al
{% endcodeblock %}
<h3>Response</h3>

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



{% codeblock %}
https://sendgrid.com/api/distributor.ip.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=al
{% endcodeblock %}
<h3>Response: Success</h3>

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

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>free</em>
            .
         </td>
         <td>Retrieve all free IPs for your account.</td>
      </tr>
      <tr>
         <td>ip</td>
         <td>No</td>
         <td>Can be a complete or partial IP address.</td>
         <td>Filter your search results.</td>
      </tr>
   </tbody>
</table>


### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.ip.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=fre
{% endcodeblock %}
<h3>Response</h3>

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



{% codeblock %}
https://sendgrid.com/api/distributor.ip.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=fre
{% endcodeblock %}
<h3>Response: Success</h3>
{% codeblock %}
"255.255.255.0","255.255.254.0","255.255.253.0","255.255.252.0"
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


{% anchor h2 %} Taken {% endanchor %}


A listing of all taken IPs under your account. A Taken IP is any IP that is in use by a user or is linked to an IP grouping.

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>taken</em>
            .
         </td>
         <td>Retrieve all taken IPs for your account.</td>
      </tr>
      <tr>
         <td>ip</td>
         <td>No</td>
         <td>Can be a complete or partial IP address.</td>
         <td>Filter your search results.</td>
      </tr>
   </tbody>
</table>


### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.ip.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=take
{% endcodeblock %}
<h3>Response</h3>

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



{% codeblock %}
https://sendgrid.com/api/distributor.ip.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=take
{% endcodeblock %}
<h3>Response: Success</h3>
{% codeblock %}
"255.255.255.0","255.255.254.0","255.255.253.0","255.255.252.0"
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


{% anchor h2 %} Available {% endanchor %}


A listing of all available IPs under your account. An Available IP is any IP that is currently free, or is in use by a user *but* that user is inactive or that is not linked to an IP grouping.

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>available</em>
            .
         </td>
         <td>Retrieve all available IPs for your account.</td>
      </tr>
      <tr>
         <td>ip</td>
         <td>No</td>
         <td>Can be a complete or partial IP address.</td>
         <td>Filter your search results.</td>
      </tr>
   </tbody>
</table>


### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.ip.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=availabl
{% endcodeblock %}
<h3>Response</h3>

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



{% codeblock %}
https://sendgrid.com/api/distributor.ip.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=availabl
{% endcodeblock %}
<h3>Response: Success</h3>
{% codeblock %}
"255.255.255.0","255.255.254.0","255.255.253.0","255.255.252.0"
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


{% anchor h2 %} Usage {% endanchor %}


The current breakdown of users who are using your IPs.

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>usage</em>
            .
         </td>
         <td>Retrieve all IPs in use broken down by user.</td>
      </tr>
      <tr>
         <td>ip</td>
         <td>No</td>
         <td>Can be a complete or partial IP address.</td>
         <td>Filter your search results.</td>
      </tr>
      <tr>
         <td>user</td>
         <td>No</td>
         <td>Can be a complete or part of a username.</td>
         <td>Filter your search results.</td>
      </tr>
      <tr>
         <td>group</td>
         <td>No</td>
         <td>Can be a complete or part of a group name.</td>
         <td>Filter your search results.</td>
      </tr>
      <tr>
         <td>system</td>
         <td>No</td>
         <td>
            Must be set to
            <em>true</em>
            .
         </td>
         <td>Include IPs assigned by SendGrid.</td>
      </tr>
   </tbody>
</table>


### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.ip.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=usage&amp;user=example.com
{% endcodeblock %}
<h3>Response</h3>

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



{% codeblock %}
https://sendgrid.com/api/distributor.ip.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=usage&amp;user=example.com
{% endcodeblock %}
<h3>Response: Success</h3>
{% codeblock %}
{"ip":"255.255.253.0","user":"user4@example.com"},{"ip":"255.255.254.0","user":"user4@example.com"}
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



