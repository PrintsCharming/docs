---
layout: page
weight: 0
title: View Available Packages
navigation:
   show: true
---

List all packages available to your account.

There are no extra parameters required for this call

### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.packages.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <packages>
      <package>
         <name>Basic Package</name>
         <price>9.95</price>
         <description>Basic Package description</description>
         <credits>10000</credits>
         <overage>0.001</overage>
         <has_reseller>false</has_reseller>
         <has_ip>false</has_ip>
         <distributor_price>50</distributor_price>
      </package>
      <package>
         <name>Silver Package</name>
         <price>79.95</price>
         <description>Silver Package Description</description>
         <credits>50000</credits>
         <overage>0.001</overage>
         <has_reseller>false</has_reseller>
         <has_ip>false</has_ip>
         <distributor_price>50</distributor_price>
      </package>
   </packages>
</result>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      <error>... error messages ...</error>
   </errors>
</result>

{% endcodeblock %}




### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.packages.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}
<h3>Response: Success</h3>




### Response: Error




{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}



