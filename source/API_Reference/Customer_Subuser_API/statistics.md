--- layout: page weight: 0 title: Statistics navigation: show: true ---

Subuser Statistics

{% anchor h2 %} Retrieve Subuser Statistics {% endanchor %}

Note that you can use *either* the days parameter *or* the start\_date
and end\_date parameter.

<table>
<tbody>
<tr class="odd">
<td align="left">Parameter</td>
<td align="left">Required</td>
<td align="left">Requirements</td>
<td align="left">Description</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Subuser must be registered under your account</td>
<td align="left">The subuser we are retrieving statistics from</td>
</tr>
<tr class="odd">
<td align="left">days</td>
<td align="left">No</td>
<td align="left">Must be an integer greater than 0</td>
<td align="left">Number of days in the past to include statistics (includes today)</td>
</tr>
<tr class="even">
<td align="left">start_date</td>
<td align="left">No</td>
<td align="left">Date must be in YYYY-mm-dd format and be before the end_date parameter</td>
<td align="left">The start date to look up statistics</td>
</tr>
<tr class="odd">
<td align="left">end_date</td>
<td align="left">No</td>
<td align="left">Date must be in YYYY-mm-dd format and be after the start_date parameter</td>
<td align="left">The end date to look up statistics</td>
</tr>
</tbody>
</table>

{% xmljsontabs stats %}

<div class="tab-content">
<div class="tab-pane" id="stats-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.stats.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com
{% endcodeblock %}

### Response

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
<div class="tab-pane active" id="stats-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.stats.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com
{% endcodeblock %}

### Response

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

<table>
<tbody>
<tr class="odd">
<td align="left">Parameter</td>
<td align="left">Required</td>
<td align="left">Requirements</td>
<td align="left">Description</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Subuser must be registered under your account</td>
<td align="left">The subuser we are retrieving statistics from</td>
</tr>
<tr class="odd">
<td align="left">aggregate</td>
<td align="left">Yes</td>
<td align="left">Must be set to 1</td>
<td align="left">This is used to let us know that you are interested in all time totals</td>
</tr>
</tbody>
</table>

{% xmljsontabs agg %}

<div class="tab-content">
<div class="tab-pane" id="agg-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.stats.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&aggregate=1
{% endcodeblock %}

### Response

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
<div class="tab-pane active" id="agg-json">
### Call

#### Command

{% codeblock %}
https://sendgrid.com/apiv2/customer.stats.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&aggregate=1
{% endcodeblock %}

### Response

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

<table>
<tbody>
<tr class="odd">
<td align="left">Parameter</td>
<td align="left">Required</td>
<td align="left">Requirements</td>
<td align="left">Description</td>
</tr>
<tr class="even">
<td align="left">list</td>
<td align="left">Yes</td>
<td align="left">The value must be set to<em>true</em></td>
<td align="left">This will allow you to retrieve a list of all categories used in your subusers account.</td>
</tr>
<tr class="odd">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Subuser must be registered under your account</td>
<td align="left">The subuser we are retrieving category statistics from</td>
</tr>
</tbody>
</table>

{% xmljsontabs cat %}

<div class="tab-content">
<div class="tab-pane" id="cat-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.stats.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&list=true
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<categories>
   <category>categoryA</category>
   <category>categoryB</category>
   <category>categoryC</category>
</categories>

{% endcodeblock %}

</div>
<div class="tab-pane active" id="cat-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.stats.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&list=true
{% endcodeblock %}

### Response

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

Retrieve statistics broken down by category. If the category does not
exist, there will be an empty result set. Note that you can use 
*either* the days parameter *or* the start\_date and end\_date
parameter.

<table>
<tbody>
<tr class="odd">
<td align="left">Parameter</td>
<td align="left">Required</td>
<td align="left">Requirements</td>
<td align="left">Description</td>
</tr>
<tr class="even">
<td align="left">category</td>
<td align="left">Yes</td>
<td align="left">Must be an existing category that has statistics. You can pass in an array of categories</td>
<td align="left">The category you will specify to retrieve detailed stats</td>
</tr>
<tr class="odd">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Subuser must be registered under you</td>
<td align="left">The subuser we are retrieving statistics from</td>
</tr>
<tr class="even">
<td align="left">days</td>
<td align="left">No</td>
<td align="left">Must be an integer greater than 0</td>
<td align="left">Number of days in the past to include statistics (Includes today)</td>
</tr>
<tr class="odd">
<td align="left">start_date</td>
<td align="left">No</td>
<td align="left">Date must be in YYYY-mm-dd format and be before the end_date parameter</td>
<td align="left">The start date to look up statistics</td>
</tr>
<tr class="even">
<td align="left">end_date</td>
<td align="left">No</td>
<td align="left">Date must be in YYYY-mm-dd format and be after the start_date parameter</td>
<td align="left">The end date to look up statistics</td>
</tr>
</tbody>
</table>

{% xmljsontabs catstats %}

<div class="tab-content">
<div class="tab-pane" id="catstats-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.stats.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&start_date=2009-06-20&end_date=2009-06-22&category=categoryA
{% endcodeblock %}

#### Call - Using an array of categories

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
<div class="tab-pane active" id="catstats-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.stats.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&start_date=2009-06-20&end_date=2009-06-22&category=categoryA
{% endcodeblock %}

#### Call - Using an array of categories

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

