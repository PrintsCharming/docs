---
layout: page
weight: 0
title: Unsubscribes
navigation:
  show: true
---

Retrieve, delete and add entries in the Unsubscribes list.


{% anchor h2 %} get {% endanchor %}


Retrieve a list of Unsubscribes with addresses and optionally with dates.


{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/api/unsubscribes.get.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;date=1
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
[
  {
    "email": "brandon.west@sendgrid.com",
    "created": "2012-09-06 14:03:18"
  }
]
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="get-xml">
### Call




{% codeblock lang:xml %}

{% endcodeblock %}




### Response



{% codeblock %}
<unsubscribes><unsubscribe><email>brandon.west@sendgrid.com</email><created>2012-09-06 14:03:18</created></unsubscribe></unsubscribes>
{% endcodeblock %}

  </div>
</div>

<hr>

{% anchor h2 %}
delete 
{% endanchor %}

<p>Delete an address from the Unsubscribe list. Please note that if no parameters are provided or if empty parameters are provided the ENTIRE list will be removed.</p>


{% xmljsontabs delete %}
<div class="tab-content">
  <div class="tab-pane active" id="delete-json">
<h3>Call</h3>
{% codeblock %}
https://sendgrid.com/api/unsubscribes.delete.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;email=emailToDelete@domain.com
{% endcodeblock %}



### Response: Success




{% codeblock lang:javascript %}
{
  "message": "success"
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




</div>
<div markdown="1" class="tab-pane" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/unsubscribes.delete.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;email=emailToDelete@domain.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock %}
<result>
  success
<result>
{% endcodeblock %}



### Response: Error

@nodes 


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
  Email does not exist
@nodes
</result>

{% endcodeblock %}


 </result></result></result>

</div>
</div>

* * * * *


{% anchor h2 %} add {% endanchor %}


Add email addresses to the Unsubscribe list.


{% xmljsontabs add %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="add-json">
### Call



{% codeblock %}
https://sendgrid.com/api/unsubscribes.add.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;email=email2@domain.com
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
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="add-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/unsubscribes.add.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;email=email2@domain.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>Email does not exist</message>
</result>

{% endcodeblock %}


 </result></result>

</div>
</div>

