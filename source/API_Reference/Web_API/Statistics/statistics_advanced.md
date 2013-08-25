---
layout: page
weight: 0
title: Advanced Statistics
navigation:
  show: true
---

{% anchor h2 %} Get Statistics for: Browsers, Clients, Devices, Geo, Global, Isp {% endanchor %}


<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>data\_type</td>
         <td>Yes</td>
         <td>One of the following:-   *browsers*: Browser data obtained from click events-   *clients*: Email client data obtained from open events-   *devices*: Device data obtained from open events-   *geo*: Geographical data obtained from multiple events-   *global*: Global account data obtained from multiple events-   *isps*: ISP data obtained from multiple events</td>
      </tr>
      <tr>
         <td>start\_date</td>
         <td>Yes</td>
         <td>Date format is based on aggregated\_by value (default is yyyy-mm-dd):-   *yyyy-mm-dd* (i.e 2012-12-13) if aggregated\_by=day (default)-   *yyyy-ww* (i.e 2012-43) if aggregated\_by=week-   *yyyy-mm* (i.e 2012-11) if aggregated\_by=month</td>
      </tr>
      <tr>
         <td>end\_date</td>
         <td>No</td>
         <td>Date format is based on aggregated\_by value (default is yyyy-mm-dd):-   *yyyy-mm-dd* (i.e 2012-12-13) if aggregated\_by=day (default)-   *yyyy-ww* (i.e 2012-43) if aggregated\_by=week-   *yyyy-mm* (i.e 2012-11) if aggregated\_by=month</td>
      </tr>
      <tr>
         <td>metric</td>
         <td>No</td>
         <td>One of the following (default is *all*):-   *open*: Opens-   *click*: Clicks-   *unique\_open*: Unique opens-   *unique\_click*: Unique clicks-   *processed*: Processed emails-   *delivered*: Delivered emails-   *drop*: Dropped emails-   *bounce*: Bounced emails-   *deferred*: Deferred email tries-   *spamreport*: Emails marked as spam-   *blocked*: Emails that have been blocked-   *all*: All metrics are returned</td>
      </tr>
      <tr>
         <td>category</td>
         <td>No</td>
         <td>Return stats for the given category</td>
      </tr>
      <tr>
         <td>aggregated\_by</td>
         <td>No</td>
         <td>Aggregate the data by the given period (default is *day*):-   *day*: Keys are returned in the format yyyy-mm-dd (i.e 2012-12-13)-   *week*: Keys are return in the format yyyy-ww (i.e 2012-43)-   *month*: Keys are return in the format yyyy-mm (i.e 2012-11)</td>
      </tr>
      <tr>
         <td>country</td>
         <td>No</td>
         <td>
            Get stats for each region/state for the given country. Only *US* (United States) and *CA* (Canada) is supported at this time. Country code is two letter characters based on [ISO 3166-1 alpha-2](http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)
            <p>This parameter is only used for when *data\_type=geo*</p>
         </td>
      </tr>
   </tbody>
</table>

{% xmljsontabs activate %}

<div class="tab-content">
<div class="tab-pane active" id="activate-json">
### Call

{% codeblock %}
https://sendgrid.com/api/stats.getAdvanced.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&start_date=2013-01-01&end_date=2013-01-02&data_type=global
{% endcodeblock %}

### Response

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
<div class="tab-pane" id="activate-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/stats.getAdvanced.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&start_date=2013-01-01&end_date=2013-01-02&data_type=global
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="UTF-8" ?>
<stats>
   <day>
      <delivered>41</delivered>
      <request>41</request>
      <unique_open>1</unique_open>
      <unique_click>1</unique_click>
      processed&gt;41
   </day>
   <date>2013-01-01</date>
   <open>2</open>
   <click>1</click>
</stats>

{% endcodeblock %}

</div>
</div>

