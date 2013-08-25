--- layout: page weight: 0 title: Bounces navigation: show: true ---

This endpoint allows you to retrieve and delete entries in the Bounces
list.

{% anchor h2 %} get {% endanchor %}

Retrieve a list of bounces with addresses and response codes, optionally
with dates.

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
         <td>Retrieve the timestamp of the bounce records. It will return a date in aMySQL timestamp format - YYYY-MM-DD HH:MM:SS</td>
      </tr>
      <tr>
         <td>days</td>
         <td>No</td>
         <td>If specified, must be an integer greater than 0</td>
         <td>Number of days in the past for which to retrieve bounces (includestoday)</td>
      </tr>
      <tr>
         <td>start\_date</td>
         <td>No</td>
         <td>Date must be in YYYY-MM-DD format and be earlier than the end\_dateparameter.</td>
         <td>The start of the date range for which to retrieve bounces.</td>
      </tr>
      <tr>
         <td>end\_date</td>
         <td>No</td>
         <td>Date must be in YYYY-MM-DD format and be later than the start\_dateparameter.</td>
         <td>The end of the date range for which to retrieve bounces.</td>
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
         <td>type</td>
         <td>No</td>
         <td>hard or soft</td>
         <td>choose the type of bounce to search for.</td>
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

{% codeblock %}
https://sendgrid.com/api/bounces.get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&date=1
{% endcodeblock %}

### Response



</div>
<div class="tab-pane" id="get-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/bounces.get.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&date=1
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<bounces>
   <bounce>
      <email>email1@domain.com</email>
      <status>5.1.1</status>
      <reason>host [127.0.0.1] said: 550 5.1.1 unknown
or illegal user: email1@domain.com</reason>
      <created>2009-06-10
12:40:30</created>
   </bounce>
   <bounce>
      <email>email2@domain2.com</email>
      <status>5.1.1</status>
      <reason>host [127.0.0.1] said: 550 5.1.1 unknown
or illegal user: email2@domain2.com</reason>
      <created>2009-08-01
10:16:30</created>
   </bounce>
</bounces>

{% endcodeblock %}

</div>
</div>

* * * * *

{% anchor h2 %} delete {% endanchor %}

Delete an address from the Bounce list. Please note that if no
parameters are specified the ENTIRE list will be deleted.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>start\_date</td>
         <td>No</td>
         <td>Date must be in YYYY-mm-dd format and be before the end\_date parameter</td>
         <td>Optional date to start deleting from.</td>
      </tr>
      <tr>
         <td>end\_date</td>
         <td>No</td>
         <td>Date must be in YYYY-mm-dd format and be after the start\_date parameter</td>
         <td>Optional date to end deleting from.</td>
      </tr>
      <tr>
         <td>type</td>
         <td>No</td>
         <td>hard or soft</td>
         <td>choose the type of bounce to be removed.</td>
      </tr>
      <tr>
         <td>email</td>
         <td>No</td>
         <td>Must be a valid user account email</td>
         <td>Email bounce address to remove</td>
      </tr>
      <tr/>
   </tbody>
</table>

{% xmljsontabs delete %}

<div class="tab-content">
<div class="tab-pane active" id="delete-json">
### Call

{% codeblock %}
https://sendgrid.com/api/bounces.delete.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=emailToDelete@domain.com
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
  "message": "Email does not exist"
}
{% endcodeblock %}

</div>
<div class="tab-pane" id="delete-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/bounces.delete.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=emailToDelete@domain.com
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result> success @nodes </result>

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

{% anchor h2 %} Count {% endanchor %}

<table>
<tbody>
<tr class="odd">
<td align="left">Parameter</td>
<td align="left">Required</td>
<td align="left">Requirements</td>
<td align="left">Description</td>
</tr>
<tr class="even">
<td align="left">start_date</td>
<td align="left">No</td>
<td align="left">Date must be in YYYY-mm-dd format and be before the end_date parameter</td>
<td align="left">Optional date to start counting from.</td>
</tr>
<tr class="odd">
<td align="left">end_date</td>
<td align="left">No</td>
<td align="left">Date must be in YYYY-mm-dd format and be after the start_date parameter</td>
<td align="left">Optional date to end counting from.</td>
</tr>
<tr class="even">
<td align="left">type</td>
<td align="left">No</td>
<td align="left">hard or soft</td>
<td align="left">choose the type of bounce to search for.</td>
</tr>
</tbody>
</table>

{% xmljsontabs count %}

<div class="tab-content">
<div class="tab-pane active" id="count-json">
### Call

{% codeblock %}
https://sendgrid.com/api/bounces.count.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

### Response: Success

{% codeblock lang:javascript %}
{
  "count": "4"
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
<div class="tab-pane" id="count-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/bounces.count.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <count>4</count>
   @nodes
</result>

{% endcodeblock %}

#### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}

</div>
</div>

