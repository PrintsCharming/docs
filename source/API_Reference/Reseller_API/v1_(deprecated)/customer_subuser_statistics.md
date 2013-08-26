---
layout: page
weight: 0
title: Customer Subuser Statistics
navigation:
   show: true
---

{% anchor h2 %} Retrieve Customer Subuser Statistics {% endanchor %}
 Note that you can use *either* the days parameter *or* the start\_date and end\_date parameter.


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



