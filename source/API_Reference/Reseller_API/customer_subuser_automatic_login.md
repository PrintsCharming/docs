---
layout: page
weight: 0
title: Customer Subuser Automatic Login
navigation:
   show: true
---

Allow customer subusers to manage their account from your website using an iframe to our site.


{% anchor h2 %} Initial API Call {% endanchor %}


In order to login your customer subuser, you need to contact our web API to retrieve the unique URL to automatically login your customer subuser. Then display the generated URL to automatically login your customer subuser.

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
         <td>user</td>
         <td>Yes</td>
         <td>Must be set in email format</td>
         <td>This is the customer subuser you will attempt to automatically login</td>
      </tr>
      <tr>
         <td>password</td>
         <td>No</td>
         <td>Your customer subuser password.</td>
         <td>Authenticate the customer subuser with this API call.</td>
      </tr>
   </tbody>
</table>


{% xmljsontabs call %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="call-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;method=geturl&amp;user=example@example.com
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<params>
   <params>al_username=username=example@example.com=b478ab36ebc306990dd283b1c341898e</params>
</params>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="call-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;method=geturl&amp;user=example@example.com
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "params": "al_username=username&amp;al_subuser_name=example@example.com&amp;al_hash=aa39649af578679d3a90d2cc43245d56"
}
{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} iFrame Usage {% endanchor %}


Using the parameters returned from the Initial API Call, you can construct the iFrame URL as shown below.

{% codeblock %} <iframe src="https://sendgrid.com/account?al_username=username&amp;al_subuser_name=example@example.com&amp;al_hash=aa39649af578679d3a90d2cc43245d56"></iframe> {% endcodeblock %}
