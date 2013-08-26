---
layout: page
weight: 0
title: Multiple Credentials
navigation:
  show: true
---

## Get

Retrieve a list of all credentials, or permissions for a specific credential.


{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/api/credentials/get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:javascript %}
[
  {
    "id": 4,
    "name": "johnsmith",
    "permissions": {
      "email": 0,
      "api": 1
    }
  },
  {
    "id": 15,
    "name": "joewrigley",
    "permissions": {
      "web": 1,
      "api": 0
    }
  }
]
{% endcodeblock %}




### Response: Error




{% codeblock lang:javascript %}
{
  "error": "error reason"
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/credentials/get.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<credentials>
   <credential>
      <created_at>2013-01-21 16:52:01</created_at>
      <permissions>
         {"web": 1, "api": 0, "email": 0}
         <permissions>
            <id>13243</id>
            <name>John Smith</name>
            <updated_at>2013-01-21 16:52:01</updated_at>
         </permissions>
         <credential>
            <created_at>2013-01-21 16:52:01</created_at>
            <permissions>
               {"web": 1, "api": 1, "email": 0}
               <permissions>
                  <id>13243</id>
                  <name>Joe Wrigley</name>
                  <updated_at>2013-01-21 16:52:01</updated_at>
               </permissions>
            </permissions>
         </credential>
      </permissions>
   </credential>
</credentials>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *

## Add

This API call allows user to add a new set of credentials to their account.


{% xmljsontabs add %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="add-json">
### Call



{% codeblock %}
https://sendgrid.com/api/credentials/add.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=name&password=password&permissions={"email": 0, "web": 1, "api": 0}
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




### Response: Error




{% codeblock lang:javascript %}
{
  "error": "error reason"
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="add-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/credentials/add.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=name&password=password&permissions={"email": 0, "web": 1, "api": 0}
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <count>4</count>
</result>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

{% info %} Excluding a permission is the same as granting access rights. In other words, if you do not specify email, web or api at all, the new credentials will have access to all three. If you do not want the credentials to have access to email, web, or api, you *must explicitly set those parameter options to zeroes*. {% endinfo %}


* * * * *

## Edit


{% xmljsontabs edit %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="edit-json">
### Call



{% codeblock %}
https://sendgrid.com/api/credentials/edit.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=name&password=password&permissions={"email": 0, "web": 1, "api": 0}
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




### Response: Error




{% codeblock lang:javascript %}
{
  "error": "error reason"
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="edit-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/credentials/edit.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=name&password=password&permissions={"email": 0, "web": 1, "api": 0}
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <count>4</count>
</result>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *

## Delete


{% xmljsontabs remove %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="remove-json">
### Call



{% codeblock %}
https://sendgrid.com/api/credentials/remove.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=example_user
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




### Response: Error




{% codeblock lang:javascript %}
{
  "error": "error reason"
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="remove-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/credentials/remove.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=example_user
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <count>4</count>
</result>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

