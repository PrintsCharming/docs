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

<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter

</th>
<th markdown="1">
Required

</th>
<th markdown="1">
Requirements

</th>
<th markdown="1">
Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *retrieve*

</td>
<td markdown="1">
Retrieve account limits

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The subuser who will have their account limits retrieved

</td>
</tr>
</tbody>
</table>
{% xmljsontabs limit %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="limit-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.limit.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=retrieve {% endcodeblock %}

### Response: Success


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

{% codeblock %} https://sendgrid.com/apiv2/customer.limit.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=retrieve {% endcodeblock %}

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


</div>
</div>

* * * * *


{% anchor h2 %} No Limit {% endanchor %}


Remove the limit for a subuser.

<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter

</th>
<th markdown="1">
Required

</th>
<th markdown="1">
Requirements

</th>
<th markdown="1">
Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *none*

</td>
<td markdown="1">
Remove account limits

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The subuser who will have their account limits removed

</td>
</tr>
</tbody>
</table>
{% xmljsontabs list %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="list-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.limit.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=none {% endcodeblock %}

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
<div markdown="1" class="tab-pane" id="list-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.limit.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=none {% endcodeblock %}

### Response: Success


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

<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter

</th>
<th markdown="1">
Required

</th>
<th markdown="1">
Requirements

</th>
<th markdown="1">
Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to*recurring*

</td>
<td markdown="1">
The task required to set the recurring reset

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The subuser you will be applying a recurring reset to

</td>
</tr>
<tr markdown="1">
<td markdown="1">
credits

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be an integer and greater than 0

</td>
<td markdown="1">
The number of credits the subuser will be reset to

</td>
</tr>
<tr markdown="1">
<td markdown="1">
period

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be either daily, weekly, or monthly

</td>
<td markdown="1">
How often you want SendGrid to reset your subusers credits

</td>
</tr>
<tr markdown="1">
<td markdown="1">
startdate

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Date must be in YYYY-mm-dd format

</td>
<td markdown="1">
The date you want to start resetting the subusers credits

</td>
</tr>
<tr markdown="1">
<td markdown="1">
enddate

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Date must be in YYYY-mm-dd format

</td>
<td markdown="1">
The date you want to stop resetting the subusers credits

</td>
</tr>
<tr markdown="1">
<td markdown="1">
initial_credits

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Must be an integer greater than 0

</td>
<td markdown="1">
The number of credits you initially want the account reset to. If this is not set, the credits will be reset using the credits parameter

</td>
</tr>
</tbody>
</table>
{% xmljsontabs reset %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="reset-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.limit.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=recurring&credits=200&period=daily {% endcodeblock %}

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
<div markdown="1" class="tab-pane" id="reset-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.limit.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=recurring&credits=200&period=daily {% endcodeblock %}

### Response: Success


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

<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter

</th>
<th markdown="1">
Required

</th>
<th markdown="1">
Requirements

</th>
<th markdown="1">
Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *total*

</td>
<td markdown="1">
Set the credits to the specified amount

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The subuser who will have their credits updated

</td>
</tr>
<tr markdown="1">
<td markdown="1">
credits

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be an integer and greater than 0

</td>
<td markdown="1">
The total number of credits the subuser will be reset to

</td>
</tr>
</tbody>
</table>
{% xmljsontabs total %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="total-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.limit.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=total&credits=200 {% endcodeblock %}

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
<div markdown="1" class="tab-pane" id="total-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.limit.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=total&credits=200 {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}


### Response: Error

{% codeblock %} <result><message>error</message><errors> ... <error>... error messages ...</error> ... </errors></result> {% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} Increment Credits {% endanchor %}
 Increment a subusers credits by a specified amount.

<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter

</th>
<th markdown="1">
Required

</th>
<th markdown="1">
Requirements

</th>
<th markdown="1">
Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *increment*

</td>
<td markdown="1">
Increment the credits by the specified amount

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The subuser who will have their credits incremented

</td>
</tr>
<tr markdown="1">
<td markdown="1">
credits

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be an integer and greater than 0

</td>
<td markdown="1">
The total number of credits the subuser will be incremented by

</td>
</tr>
</tbody>
</table>
{% xmljsontabs increment %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="increment-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.limit.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=increment&credits=20 {% endcodeblock %}

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

{% codeblock %} https://sendgrid.com/apiv2/customer.limit.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=increment&credits=200 {% endcodeblock %}

### Response: Success


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

<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter

</th>
<th markdown="1">
Required

</th>
<th markdown="1">
Requirements

</th>
<th markdown="1">
Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *increment*

</td>
<td markdown="1">
Decrement the credits by the specified amount

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The subuser who will have their credits decremented

</td>
</tr>
<tr markdown="1">
<td markdown="1">
credits

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be an integer and greater than 0

</td>
<td markdown="1">
The total number of credits the subuser will be decremented by

</td>
</tr>
</tbody>
</table>
{% xmljsontabs decrement %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="decrement-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.limit.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=decrement&credits=200 {% endcodeblock %}

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
<div markdown="1" class="tab-pane" id="decrement-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.limit.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=decrement&credits=200 {% endcodeblock %}

### Response: Success


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

