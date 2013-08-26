---
layout: page
weight: 0
title: Advanced Statistics
navigation:
  show: true
---

{% anchor h2 %} Get Statistics for: Browsers, Clients, Devices, Geo, Global, Isp {% endanchor %}



{% xmljsontabs activate %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="activate-json">
### Call



{% codeblock %}
https://sendgrid.com/api/stats.getAdvanced.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&start_date=2013-01-01&end_date=2013-01-02&data_type=global
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
[
  {
    "delivered": 41,
    "request": 41,
    "unique_open": 1,
    "unique_click": 1,
    "processed": 41,
    "date": "2013-01-01",
    "open": 2,
    "click": 1
  },
  {
    "delivered": 224,
    "unique_open": 1,
    "request": 224,
    "processed": 224,
    "date": "2013-01-02",
    "open": 3
  }
]
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="activate-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/stats.getAdvanced.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&start_date=2013-01-01&end_date=2013-01-02&data_type=global
{% endcodeblock %}
<h3>Response</h3>
	
{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version='1.0' encoding='UTF-8'?>
<stats>
   <day>
      <delivered>41</delivered>
      <request>41</request>
      <unique_open>1</unique_open>
      <unique_click>1</unique_click>
      <processed>41</processed>
      <date>2013-01-01</date>
      <open>2</open>
      <click>1</click>
   </day>
   <day>
      <delivered>224</delivered>
      <unique_open>1</unique_open>
      <request>224</request>
      <processed>224</processed>
      <date>2013-01-02</date>
      <open>3</open>
   </day>
</stats>

{% endcodeblock %}




</div>
</div>

