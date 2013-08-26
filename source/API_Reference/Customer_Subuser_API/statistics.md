---
layout: page
weight: 0
title: Statistics
navigation:
   show: true
---

Subuser Statistics


{% anchor h2 %} Retrieve Subuser Statistics {% endanchor %}


Note that you can use *either* the days parameter *or* the start\_date and end\_date parameter.

||
|Parameter|Required|Requirements|Description|
|user|Yes|Subuser must be registered under your account|The subuser we are retrieving statistics from|
|days|No|Must be an integer greater than 0|Number of days in the past to include statistics (includes today)|
|start\_date|No|Date must be in YYYY-mm-dd format and be before the end\_date parameter|The start date to look up statistics|
|end\_date|No|Date must be in YYYY-mm-dd format and be after the start\_date parameter|The end date to look up statistics|

{% xmljsontabs stats %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="stats-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.stats.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com
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




</div>
<div markdown="1" class="tab-pane active" id="stats-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.stats.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com
{% endcodeblock %}
    <h3>Response</h3>
    
{% codeblock lang:javascript %}
[
  {
    "date": "2009-06-20",
    "requests": 12342,
    "bounces": 12,
    "clicks": 10223,
    "opens": 9992,
    "spamreports": 5
  },
  {
    "date": "2009-06-21",
    "requests": 32342,
    "bounces": 10,
    "clicks": 14323,
    "opens": 10995,
    "spamreports": 7
  },
  {
    "date": "2009-06-22",
    "requests": 52342,
    "bounces": 11,
    "clicks": 19223,
    "opens": 12992,
    "spamreports": 2
  }
]
{% endcodeblock %}




</div>
</div>

{% anchor h2 %} Retrieve Aggregates {% endanchor %}


Retrieve all-time totals for your subuser

||
|Parameter|Required|Requirements|Description|
|user|Yes|Subuser must be registered under your account|The subuser we are retrieving statistics from|
|aggregate|Yes|Must be set to 1|This is used to let us know that you are interested in all time totals|

{% xmljsontabs agg %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="agg-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.stats.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&aggregate=1
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




</div>
<div markdown="1" class="tab-pane active" id="agg-json">
### Call

#### Command



{% codeblock %}
https://sendgrid.com/apiv2/customer.stats.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&aggregate=1
{% endcodeblock %}
    <h3>Response</h3>
    
{% codeblock lang:javascript %}
{
  "requests": "12342",
  "bounces": "12",
  "clicks": "10223",
  "opens": "9992",
  "spamreports": "5"
}
{% endcodeblock %}




</div>
</div>

{% anchor h2 %} Category List {% endanchor %}


Retrieve a list of all the categories used in your subusers account.

||
|Parameter|Required|Requirements|Description|
|list|Yes|The value must be set to*true*|This will allow you to retrieve a list of all categories used in your subusers account.|
|user|Yes|Subuser must be registered under your account|The subuser we are retrieving category statistics from|

{% xmljsontabs cat %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="cat-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.stats.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&list=true
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




</div>
<div markdown="1" class="tab-pane active" id="cat-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.stats.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&list=true
{% endcodeblock %}
    <h3>Response</h3>
    
{% codeblock lang:javascript %}
[
  {
    "category": "categoryC"
  }
]
{% endcodeblock %}




</div>
</div>

{% anchor h2 %} Category Statistics {% endanchor %}


Retrieve statistics broken down by category. If the category does not exist, there will be an empty result set. Note that you can use  *either* the days parameter *or* the start\_date and end\_date parameter.

||
|Parameter|Required|Requirements|Description|
|category|Yes|Must be an existing category that has statistics. You can pass in an array of categories|The category you will specify to retrieve detailed stats|
|user|Yes|Subuser must be registered under you|The subuser we are retrieving statistics from|
|days|No|Must be an integer greater than 0|Number of days in the past to include statistics (Includes today)|
|start\_date|No|Date must be in YYYY-mm-dd format and be before the end\_date parameter|The start date to look up statistics|
|end\_date|No|Date must be in YYYY-mm-dd format and be after the start\_date parameter|The end date to look up statistics|

{% xmljsontabs catstats %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="catstats-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.stats.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&start_date=2009-06-20&end_date=2009-06-22&category=categoryA
{% endcodeblock %}
    <h4>Call - Using an array of categories</h4>
    {% codeblock %}
https://sendgrid.com/apiv2/customer.stats.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&start_date=2009-06-20&end_date=2009-06-22&category[]=categoryA&category[]=categoryB
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




</div>
<div markdown="1" class="tab-pane active" id="catstats-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.stats.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&start_date=2009-06-20&end_date=2009-06-22&category=categoryA
{% endcodeblock %}
    <h4>Call - Using an array of categories</h4>
    {% codeblock %}
https://sendgrid.com/apiv2/customer.stats.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&start_date=2009-06-20&end_date=2009-06-22&category[]=categoryA&category[]=categoryB
{% endcodeblock %}



### Response




{% codeblock lang:javascript %}
[
  {
    "date": "2009-06-20",
    "category": "categoryA",
    "requests": 12342,
    "bounces": 12,
    "clicks": 10223,
    "opens": 9992,
    "spamreports": 5
  },
  {
    "date": "2009-06-21",
    "category": "categoryB",
    "requests": 32342,
    "bounces": 10,
    "clicks": 14323,
    "opens": 10995,
    "spamreports": 7
  }
]
{% endcodeblock %}




</div>

