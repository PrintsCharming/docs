---
layout: page
weight: 0
title: Google Analytics
navigation:
  show: true
---

This app appends links to integrate with Google Analytics.

![Google Analytics App Image]({{root_url}}/images/google_analytics.png "Google Analytics")

For more information about using this app, please refer to [Google's URL Builder](http://support.google.com/googleanalytics/bin/answer.py?hl=en&answer=55578) and their [presentation on Campaign Tracking](http://www.google.com/analytics/iq.html).

We default the settings to Google's recommendations. Anything you enter into those fields in the App Settings or via API will take precedence.


{% anchor h2 %} Settings {% endanchor %}


|Name|Required|Description|Default Value|
|:---|:-------|:----------|:------------|
|Campaign Source|No|Name of the referrer source. (e.g. Google, SomeDomain.com, Marketing EmailA)|sendgrid.com|
|Campaign Medium|No|Name of the marketing medium. (e.g. Email)|email|
|Campaign Term|No|Identify paid keywords..||
|Campaign Content|No|Use to differentiate ads.||
|Campaign Name|No|Name of the campaign.|website|


{% anchor h2 %} Example {% endanchor %}
 {% codeblock %} http://sendgrid.com/?utm_source=sendgrid&utm_medium=email&utm_term=variationC&utm_content=newsletter4&utm_campaign=flagshipproduct {% endcodeblock %}
