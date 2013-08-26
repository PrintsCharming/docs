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


<table>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Required</th>
<th align="left">Description</th>
<th align="left">Default Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Campaign Source</td>
<td align="left">No</td>
<td align="left">Name of the referrer source. (e.g. Google, SomeDomain.com, Marketing EmailA)</td>
<td align="left">sendgrid.com</td>
</tr>
<tr class="even">
<td align="left">Campaign Medium</td>
<td align="left">No</td>
<td align="left">Name of the marketing medium. (e.g. Email)</td>
<td align="left">email</td>
</tr>
<tr class="odd">
<td align="left">Campaign Term</td>
<td align="left">No</td>
<td align="left">Identify paid keywords..</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">Campaign Content</td>
<td align="left">No</td>
<td align="left">Use to differentiate ads.</td>
<td align="left"></td>
</tr>
<tr class="odd">
<td align="left">Campaign Name</td>
<td align="left">No</td>
<td align="left">Name of the campaign.</td>
<td align="left">website</td>
</tr>
</tbody>
</table>


{% anchor h2 %} Example {% endanchor %}
 {% codeblock %} http://sendgrid.com/?utm_source=sendgrid&utm_medium=email&utm_term=variationC&utm_content=newsletter4&utm_campaign=flagshipproduct {% endcodeblock %}
