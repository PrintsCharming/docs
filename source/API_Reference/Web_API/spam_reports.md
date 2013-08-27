---
layout: page
weight: 0
title: Spam Reports
navigation:
  show: true
---

Retrieve and delete entries in the Spam Reports list.


{% anchor h2 %} get {% endanchor %}


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
         <td>Retrieve the timestamp of the spam report records. It will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS</td>
      </tr>
      <tr>
         <td>days</td>
         <td>No</td>
         <td>If specified, must be an integer greater than 0</td>
         <td>Number of days in the past for which to retrieve spam reports (includes today)</td>
      </tr>
      <tr>
         <td>start_date</td>
         <td>No</td>
         <td>Date must be in YYYY-MM-DD format and be earlier than the end_date parameter.</td>
         <td>The start of the date range for which to retrieve spam reports.</td>
      </tr>
      <tr>
         <td>end_date</td>
         <td>No</td>
         <td>Date must be in YYYY-MM-DD format and be later than the start_date parameter.</td>
         <td>The end of the date range for which to retrieve spam reports.</td>
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

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/api/spamreports.get.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;date=1
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
[
  {
    "ip": "174.36.80.219",
    "email": "example@aol.com",
    "created": "2009-12-06 15:45:08"
  },
  {
    "ip": "74.63.202.105",
    "email": "example2@yahoo.com",
    "created": "2009-12-08 07:43:01"
  }
]
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/spamreports.get.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;date=1
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<spamreports>
   <spamreport>
      <ip>174.36.80.219</ip>
      <email>example@aol.com</email>
      <created>2009-12-06 15:45:08</created>
   </spamreport>
   <spamreport>
      <ip>74.63.202.105</ip>
      <email>example2@yahoo.com</email>
      <created>2009-12-08 07:43:01</created>
   </spamreport>
</spamreports>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} delete {% endanchor %}


Delete an address from the Spam Reports list.

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
         <td>Must be a valid user account email</td>
         <td>Email spam reports address to remove</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
https://sendgrid.com/api/spamreports.delete.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;email=emailToDelete@domain.com
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
<div markdown="1" class="tab-pane" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/spamreports.delete.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;email=emailToDelete@domain.com
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

