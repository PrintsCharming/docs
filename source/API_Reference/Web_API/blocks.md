---
layout: page
weight: 0
title: Blocks
navigation:
  show: true
---

This endpoint allows you to retrieve and delete entries in the Blocks list.


{% anchor h2 %} get {% endanchor %}
Retrieve a list of Blocks with addresses and response codes, optionally with dates.

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
         <td>Retrieve the timestamp of the Block records. It will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS</td>
      </tr>
      <tr>
         <td>days</td>
         <td>No</td>
         <td>If specified, must be an integer greater than 0</td>
         <td>Number of days in the past for which to retrieve blocks (includes today)</td>
      </tr>
      <tr>
         <td>start_date</td>
         <td>No</td>
         <td>Date must be in YYYY-MM-DD format and be earlier than the end_date parameter.</td>
         <td>The start of the date range for which to retrieve blocks.</td>
      </tr>
      <tr>
         <td>end_date</td>
         <td>No</td>
         <td>Date must be in YYYY-MM-DD format and be later than the start_date parameter.</td>
         <td>The end of the date range for which to retrieve blocks.</td>
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
   </tbody>
</table>

{% xmljsontabs get %}

<div class="tab-content">
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %} https://sendgrid.com/api/blocks.get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&date=1 {% endcodeblock %}

### Response


{% codeblock lang:javascript %}
[
  {
    "status": "4.0.0",
    "created": "2012-09-02 00:12:12",
    "reason": "550 Access denied...04d52d35b93501d500a9bca895ddad5cddd1a9f8486c89ace8c5e959398198cd49cd58288c9d11313975284d852811... (throttled)",
    "email": "example@juno.com"
  },
  {
    "status": "4.0.0",
    "created": "2012-09-02 00:21:29",
    "reason": "Connection timed out",
    "email": "example2@band.la"
  },
  {
    "status": "4.0.0",
    "created": "2012-09-02 00:25:33",
    "reason": "Unable to resolve MX record for exampledomain.com: nxdomain",
    "email": "example3@exampledomain.com"
  }
]
{% endcodeblock %}


</div>
<div class="tab-pane" id="get-xml">
### Call

{% codeblock %} https://sendgrid.com/api/blocks.get.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&date=1 {% endcodeblock %}

### Response


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<blocks>
   <block>
      <email>email1@domain.com</email>
      <status>5.1.1</status>
      <reason>host [127.0.0.1] said: 550 5.1.1 unknown or illegal user: email1@domain.com</reason>
      <created>2009-06-10 12:40:30</created>
   </block>
   <block>
      <email>email2@domain2.com</email>
      <status>5.1.1</status>
      <reason>host [127.0.0.1] said: 550 5.1.1 unknown or illegal user: email2@domain2.com</reason>
      <created>2009-08-01 10:16:30</created>
   </block>
</blocks>

{% endcodeblock %}


</div>
</div>

* * * * *


{% anchor h2 %} delete {% endanchor %}
Delete an address from the Block list.

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
         <td>Email block address to remove</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs delete %}

<div class="tab-content">
<div class="tab-pane active" id="delete-json">
### Call

{% codeblock %} https://sendgrid.com/api/blocks.delete.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=emailToDelete@domain.com {% endcodeblock %}

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

{% codeblock %} https://sendgrid.com/api/blocks.delete.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=emailToDelete@domain.com {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <count>4</count>
   @nodes
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

