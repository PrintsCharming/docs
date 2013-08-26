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
date

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Must be set to 1

</td>
<td markdown="1">
Retrieve the timestamp of the unsubscribe records. It will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS

</td>
</tr>
<tr markdown="1">
<td markdown="1">
days

</td>
<td markdown="1">
No

</td>
<td markdown="1">
If specified, must be an integer greater than 0

</td>
<td markdown="1">
Number of days in the past for which to retrieve unsubscribes (includes today)

</td>
</tr>
<tr markdown="1">
<td markdown="1">
start\_date

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Date must be in YYYY-MM-DD format and be earlier than the end\_date parameter.

</td>
<td markdown="1">
The start of the date range for which to retrieve unsubscribes.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
end\_date

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Date must be in YYYY-MM-DD format and be later than the start\_date parameter.

</td>
<td markdown="1">
The end of the date range for which to retrieve unsubscribes.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
limit

</td>
<td markdown="1">
No

</td>
<td markdown="1">
some integer

</td>
<td markdown="1">
Optional field to limit the number of results returned.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
offset

</td>
<td markdown="1">
No

</td>
<td markdown="1">
some integer

</td>
<td markdown="1">
optional beginning point in the list to retrieve from.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
email

</td>
<td markdown="1">
No

</td>
<td markdown="1">
email address eg testing@example.com

</td>
<td markdown="1">
optional email addresses to search for.

</td>
</tr>
</tbody>
</table>
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
email

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be a valid email address

</td>
<td markdown="1">
Email address to add to unsubscribe list

</td>
</tr>
</tbody>
</table>
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

