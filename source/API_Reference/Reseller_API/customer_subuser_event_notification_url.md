---
layout: page
weight: 0
title: Customer Subuser Event Notification URL
navigation:
   show: true
---

{% anchor h2 %} Retrieve {% endanchor %}


|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|task|Yes|Must be set to *get*|This will allow you to retrieve the event notification url for the specified customer subuser|
|user|Yes|Customer subuser must be registered under your account|The username of the customer subuser|

{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=get&user=example@example.com&method=eventpostur
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<url>http://www.SubUserPostUrlHere.com</url>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=get&user=example@example.com&method=eventpostur
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "url": "http://www.SubUserPostUrlHere.com"
}
{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Update / Set URL {% endanchor %}


|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|task|Yes|Must be set to *set*|This will allow you to retrieve the event notification url for the specified customer subuser|
|user|Yes|Customer subuser must be registered under your account|The name of the customer subuser|
|url|Yes|The notification URL|This is the new event notification URL|

{% xmljsontabs update %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="update-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=set&user=example@example.com&url=http://www.SubUserPostUrlHere.com&method=eventpostur
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="update-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=set&user=example@example.com&url=http://www.SubUserPostUrlHere.com&method=eventpostur
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Delete {% endanchor %}


|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|task|Yes|Must be set to *delete*|This will allow you to delete the event notification url for the specified customer subuser|
|user|Yes|Customer subuser must be registered under your account|The name of the customer subuser|

{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=delete&user=example@example.com&method=eventpostur
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=delete&user=example@example.com&method=eventpostur
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




</div>
</div>

