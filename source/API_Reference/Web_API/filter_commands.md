---
layout: page
weight: 0
title: Filter Commands
navigation:
  show: true
---

{% anchor h2 %} Get Available {% endanchor %}


List all of the available apps.

*Note: The name entry is used in all the other API calls to identify a app.* For a list of all the apps and parameters accesible with the Web API you can check the [Filter Settings]({{root_url}}/API_Reference/Web_API/filter_settings.html) page.

{% xmljsontabs getavailable %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="getavailable-json">
### Call



{% codeblock %}
https://sendgrid.com/api/filter.getavailable.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
[
  {
    "name": "twitter",
    "title": "Twitter",
    "description": "This plugin allows you to send an email message to twitter",
    "activated": false
  }
]
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="getavailable-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/filter.getavailable.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filters>
   <filter>
      <name>twitter</name>
      <title>Twitter</title>
      <description>This plugin allows you to send an email message to twitter</description>
      <activated>0</activated>
   </filter>
   ...
</filters>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Activate App {% endanchor %}
 {% xmljsontabs activate %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="activate-json">
### Call



{% codeblock %}
https://sendgrid.com/api/filter.activate.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter
{% endcodeblock %}
		<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="activate-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/filter.activate.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter
{% endcodeblock %}
		<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *

{% xmljsontabs deactivate %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="deactivate-json">
### Call



{% codeblock %}
https://sendgrid.com/api/filter.deactivate.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter
{% endcodeblock %}
   <h3>Response</h3>


{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="deactivate-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/filter.deactivate.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter
{% endcodeblock %}

		<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




</div>
</div>

{% anchor h2 %} Deactivate App {% endanchor %}


* * * * *


{% anchor h2 %} Setup App {% endanchor %}


These API calls require that settings are passed using POST.

### PHP curl

Code Example



{% codeblock lang:php %}
<?php
 
$url = 'sendgrid.com';
$user = 'username';
$pass = 'password';

$params = array(
  'api_user' => $user,
  'api_key' => $pass,
  'name' => 'twitter',
  'username' => 'twitterusername',
  'password' => 'twitterpassword',
);

$request = $url.'/api/filter.setup.xml';

// Generate curl request
$session = curl_init($request);
// Tell curl to use HTTP POST
curl_setopt ($session, CURLOPT_POST, true);
// Tell curl that this is the body of the POST
curl_setopt ($session, CURLOPT_POSTFIELDS, $params);
// Tell curl not to return headers, but do return the response
curl_setopt($session, CURLOPT_HEADER, false);
curl_setopt($session, CURLOPT_RETURNTRANSFER, true);
 
// obtain response
$response = curl_exec($session);
curl_close($session);
 
// print everything out
print_r($response);
?>
{% endcodeblock %}



* * * * *


{% anchor h2 %} Get Settings {% endanchor %}
 {% xmljsontabs getsettings %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="getsettings-json">
### Call



{% codeblock %}
https://sendgrid.com/api/filter.getsettings.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter
{% endcodeblock %}
	<h3>Response: Success</h3>

{% codeblock lang:javascript %}
{
  "message": "success",
  "settings": [
    {
      "field_name": "field_value"
    }
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




### Response: Empty

*\*This is returned if that filter has no settings or is not enabled.* 


{% codeblock lang:javascript %}
{
  "settings": null
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="getsettings-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/filter.getsettings.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter
{% endcodeblock %}
		<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filter>
   <field_name>field_value</field_name>
   ...
</filter>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <message>... error messages ...</message>
</result>

{% endcodeblock %}




### Response: Empty

*\*This is returned if that filter has no settings or is not enabled.* 


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filter/>

{% endcodeblock %}




</div>
</div>

