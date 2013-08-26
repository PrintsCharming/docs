---
layout: page
weight: 0
title: DKIM
navigation:
  show: true
---

Many ISPs authenticate e-mail using DKIM certification. DKIM works by having a company sign an e-mail with their private key, and then publish a public key in their DNS, which is then used to verify the e-mail signature. The domain that is checked for the public key is based on a field in the DKIM signature header in your email. This field is the "d=" parameter of the signature.

![]({{root_url}}/images/dkim.png "DKIM")

By default, SendGrid signs all e-mail with DKIM to improve its deliverability. For shared accounts such as Free or Bronze plans, this signature uses the sendgrid.me domain. For higher tier packages with whitelabeling setup a custom domain is used. In order for this custom domain to be correctly certified the appropriate public key MUST be present in the domain's DNS records. For more info on how this record is added go [here]({{root_url}}/User_Guide/whitelabel_wizard.html).


{% anchor h2 %} Settings {% endanchor %}


|Name|Required|Description|
|:---
layout: page
weight: 0
title: DKIM
navigation:
  show: true
---
---
layout: page
weight: 0
title: DKIM
navigation:
  show: true
---
---
layout: page
weight: 0
title: DKIM
navigation:
  show: true
---
-|
|Domain|No|Sets the sender domain.|
|Use From domain|No|Sets the DKIM domain to the sender domain|


