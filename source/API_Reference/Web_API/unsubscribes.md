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

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>date</td>
         <td>No</td>
         <td>Must be set to 1</td>
         <td>Retrieve the timestamp of the unsubscribe records. It will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS</td>
      </tr>
      <tr>
         <td>days</td>
         <td>No</td>
         <td>If specified, must be an integer greater than 0</td>
         <td>Number of days in the past for which to retrieve unsubscribes (includes today)</td>
      </tr>
      <tr>
         <td>start_date</td>
         <td>No</td>
         <td>Date must be in YYYY-MM-DD format and be earlier than the end_date parameter.</td>
         <td>The start of the date range for which to retrieve unsubscribes.</td>
      </tr>
      <tr>
         <td>end_date</td>
         <td>No</td>
         <td>Date must be in YYYY-MM-DD format and be later than the start_date parameter.</td>
         <td>The end of the date range for which to retrieve unsubscribes.</td>
      </tr>
      <tr>
         <td>limit</td>
         <td>No</td>
         <td>some integer</td>
         <td>Optional field to limit the number of results returned.</td>
      </tr>
      <tr>
         <td>offset</td>
         <td>No</td>
         <td>some integer</td>
         <td>optional beginning point in the list to retrieve from.</td>
      </tr>
      <tr>
         <td>email</td>
         <td>No</td>
         <td>email address eg testing@example.com</td>
         <td>optional email addresses to search for.</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs get %}

<div class="tab-content">
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %} https://sendgrid.com/api/unsubscribes.get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&date=1 {% endcodeblock %}

### Response


{% codeblock lang:javascript %}
[
  {
    "email": "brandon.west@sendgrid.com",
    "created": "2012-09-06 14:03:18"
  }
]
{% endcodeblock %}


</div>
<div class="tab-pane" id="get-xml">
### Call


{% codeblock lang:xml %}

{% endcodeblock %}


### Response

{% codeblock %} <unsubscribes><unsubscribe><email>brandon.west@sendgrid.com</email><created>2012-09-06 14:03:18</created></unsubscribe></unsubscribes> {% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} delete {% endanchor %}


Delete an address from the Unsubscribe list. Please note that if no parameters are provided or if empty parameters are provided the ENTIRE list will be removed.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>email</td>
         <td>No</td>
         <td>Must be a valid user account email</td>
         <td>Unsubscribed email address to remove</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs delete %}

<div class="tab-content">
<div class="tab-pane active" id="delete-json">
### Call

{% codeblock %} https://sendgrid.com/api/unsubscribes.delete.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=emailToDelete@domain.com {% endcodeblock %}

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
<div class="tab-pane" id="delete-xml">
### Call

{% codeblock %} https://sendgrid.com/api/unsubscribes.delete.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=emailToDelete@domain.com {% endcodeblock %}

### Response: Success

{% codeblock %} <result> success <result> {% endcodeblock %}

### Response: Error

@nodes 
{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result> Email does not exist @nodes </result>

{% endcodeblock %}
 </result></result></result>

</div>
</div>

* * * * *


{% anchor h2 %} add {% endanchor %}


Add email addresses to the Unsubscribe list.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>email</td>
         <td>Yes</td>
         <td>Must be a valid email address</td>
         <td>Email address to add to unsubscribe list</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs add %}

<div class="tab-content">
<div class="tab-pane active" id="add-json">
### Call

{% codeblock %} https://sendgrid.com/api/unsubscribes.add.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=email2@domain.com {% endcodeblock %}

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
<div class="tab-pane" id="add-xml">
### Call

{% codeblock %} https://sendgrid.com/api/unsubscribes.add.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=email2@domain.com {% endcodeblock %}

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
   <message>Email does not exist</message>
</result>

{% endcodeblock %}
 </result></result>

</div>
</div>

