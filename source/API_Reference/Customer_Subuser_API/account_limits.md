---
layout: page
weight: 0
title: Account Limits
navigation:
   show: true
---

<span>Throttle your subuser when you need them to send only a specific amount of emails at a specified interval.</span>


{% anchor h2 %} Retrieve {% endanchor %}


Retrieve account limits for a specific subuser. If the API call response is empty that means the subuser has the limits removed.


{% xmljsontabs limit %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="limit-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.limit.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=retrieve
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:javascript %}
{
  "credit": "0",
  "credit_remain": "2000",
  "last_reset": "2011-02-21"
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
<div markdown="1" class="tab-pane" id="limit-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.limit.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=retrieve
{% endcodeblock %}
<h3>Response: Error</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      <error>... error messages ...</error>
   </errors>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} No Limit {% endanchor %}


Remove the limit for a subuser.


{% xmljsontabs list %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="list-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.limit.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=none
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
<div markdown="1" class="tab-pane" id="list-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.limit.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=none
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
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Recurring Reset {% endanchor %}
 A recurring reset will allow you to periodically reset a subusers credits to a number you specify. This can be either daily, weekly or monthly.


{% xmljsontabs reset %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="reset-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.limit.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=recurring&credits=200&period=daily
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
<div markdown="1" class="tab-pane" id="reset-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.limit.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=recurring&credits=200&period=daily
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<message>
   <result>success@nodes</result>
</message>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Total Credits {% endanchor %}
 Set a subusers credits to a specified amount.


{% xmljsontabs total %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="total-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.limit.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=total&credits=200
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
<div markdown="1" class="tab-pane" id="total-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.limit.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=total&credits=200
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




### Response: Error



{% codeblock %}    <result><message>error</message><errors>
        ...
        <error>... error messages ...</error>
        ...
      </errors></result>
{% endcodeblock %}
    </div>

</div>
  <hr/>
  
{% anchor h2 %}
Increment Credits 
{% endanchor %}

  Increment a subusers credits by a specified amount.
  
  
{% xmljsontabs increment %}

<div class="tab-content">
	  <div class="tab-pane active" id="increment-json">
<h3>Call</h3>
{% codeblock %}
https://sendgrid.com/apiv2/customer.limit.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=increment&credits=20
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
<div markdown="1" class="tab-pane" id="increment-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.limit.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=increment&credits=200
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
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Decrement Credits {% endanchor %}
 Decrement a subusers credits by a specified amount.


{% xmljsontabs decrement %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="decrement-json">
### Call



{% codeblock %}
	https://sendgrid.com/apiv2/customer.limit.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=decrement&credits=200
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
<div markdown="1" class="tab-pane" id="decrement-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.limit.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=decrement&credits=200
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
   <result>@nodes</result>
</result>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}




</div>
</div>

