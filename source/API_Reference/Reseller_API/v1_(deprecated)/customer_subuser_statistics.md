---
layout: page
weight: 0
title: Customer Subuser Statistics
navigation:
   show: true
---

{% anchor h2 %} Retrieve Customer Subuser Statistics {% endanchor %}
 Note that you can use *either* the days parameter *or* the start\_date and end\_date parameter.

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
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Customer subuser must be registered under your account

</td>
<td markdown="1">
The customer subuser we are retrieving statistics from

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
Must be an integer greater than 0

</td>
<td markdown="1">
Number of days in the past to include statistics (includes today)

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
Date must be in YYYY-mm-dd format and be before the end\_date parameter

</td>
<td markdown="1">
The start date to look up statistics

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
Date must be in YYYY-mm-dd format and be after the start\_date parameter

</td>
<td markdown="1">
The end date to look up statistics

</td>
</tr>
</tbody>
</table>
### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=stats&user=example@example.com
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<stats>
   <day>
      <date>2009-06-20</date>
      <requests>12342</requests>
      <bounces>12</bounces>
      <clicks>10223</clicks>
      <opens>9992</opens>
      <spamreports>5</spamreports>
   </day>
   <day>
      <date>2009-06-21</date>
      <requests>32342</requests>
      <bounces>10</bounces>
      <clicks>14323</clicks>
      <opens>10995</opens>
      <spamreports>7</spamreports>
   </day>
   <day>
      <date>2009-06-22</date>
      <requests>52342</requests>
      <bounces>11</bounces>
      <clicks>19223</clicks>
      <opens>12992</opens>
      <spamreports>2</spamreports>
   </day>
</stats>

{% endcodeblock %}




### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=stats&user=example@example.com
{% endcodeblock %}
<h3>Response</h3>




* * * * *


{% anchor h2 %} Retrieve Aggregates {% endanchor %}
 Retrieve all-time totals for your customer subuser

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
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Customer subuser must be registered under your account

</td>
<td markdown="1">
The subuser we are retrieving statistics from

</td>
</tr>
<tr markdown="1">
<td markdown="1">
aggregate

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to 1

</td>
<td markdown="1">
This is used to let us know that you are interested in all time totals

</td>
</tr>
</tbody>
</table>
### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=stats&;user=example@example.com&aggregate=
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<stats>
   <requests>12342</requests>
   <bounces>12</bounces>
   <clicks>10223</clicks>
   <opens>9992</opens>
   <spamreports>5</spamreports>
</stats>

{% endcodeblock %}




### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=stats&user=example@example.com&aggregate=
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "requests": 12342,
  "bounces": 12,
  "clicks": 10223,
  "opens": 9992,
  "spamreports": 5
}
{% endcodeblock %}




* * * * *


{% anchor h2 %} Category List {% endanchor %}
 Retrieve a list of all the categories used in your customer subusers account.

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
list

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
The value must be set to *true*

</td>
<td markdown="1">
This will allow you to retrieve a list of all categories used in your customer subusers account.

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
The subuser we are retrieving category statistics from

</td>
</tr>
</tbody>
</table>
### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=stats&user=example@example.com&list=tru
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<categories>
   <category>categoryA</category>
   <category>categoryB</category>
   <category>categoryC</category>
</categories>

{% endcodeblock %}




### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=stats&user=example@example.com&list=tru
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "category": "categoryC"
}
{% endcodeblock %}




* * * * *


{% anchor h2 %} Category Statistics {% endanchor %}
 Retrieve statistics broken down by category. If the category does not exist, there will be an empty result set. Note that you can use *either* the days parameter *or* the start\_date and end\_date parameter.

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
category

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be an existing category that has statistics. You can pass in an array of categories

</td>
<td markdown="1">
The category you will specify to retrieve detailed stats

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
Customer subuser must be registered under you

</td>
<td markdown="1">
The customer subuser we are retrieving statistics from

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
Must be an integer greater than 0

</td>
<td markdown="1">
Number of days in the past to include statistics (Includes today)

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
Date must be in YYYY-mm-dd format and be before the end\_date parameter

</td>
<td markdown="1">
The start date to look up statistics

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
Date must be in YYYY-mm-dd format and be after the start\_date parameter

</td>
<td markdown="1">
The end date to look up statistics

</td>
</tr>
</tbody>
</table>
### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=stats&user=example@example.com&start_date=2009-06-20&end_date=2009-06-22&category=category
{% endcodeblock %}
<h4>Command - Using an array of categories</h4>
{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=stats&user=example@example.com&start_date=2009-06-20&end_date=2009-06-22&category[]=categoryA&category[]=category
{% endcodeblock %}



### Response




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<stats>
   <day>
      <date>2009-06-20</date>
      <category>categoryA</category>
      <requests>12342</requests>
      <bounces>12</bounces>
      <clicks>10223</clicks>
      <opens>9992</opens>
      <spamreports>5</spamreports>
   </day>
   <day>
      <date>2009-06-21</date>
      <category>categoryB</category>
      <requests>32342</requests>
      <bounces>10</bounces>
      <clicks>14323</clicks>
      <opens>10995</opens>
      <spamreports>7</spamreports>
   </day>
</stats>

{% endcodeblock %}




### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=stats&user=example@example.com&start_date=2009-06-20&end_date=2009-06-22&category=category
{% endcodeblock %}
<h4>Command - Using an array of categories</h4>
{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=stats&user=example@example.com&start_date=2009-06-20&end_date=2009-06-22&category[]=categoryA&category[]=category
{% endcodeblock %}



### Response




{% codeblock lang:xml %}

{% endcodeblock %}



