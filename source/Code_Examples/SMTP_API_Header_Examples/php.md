---
layout: page
weight: 0
title: PHP
navigation:
  show: true
---

The following is a sample of a header that calls the SMTP API. Further down on this page you can find a complete example.

{% codeblock lang:php %} <?php # version 1.0 # last updated 6 22 2009 class smtpapiheader { var $data; function addto($tos) { if (!isset($this- ?>data['to'])) { \$this-\>data['to'] = array(); } \$this-\>data['to'] = array\_merge(\$this-\>data['to'], (array) \$tos); } function addSubVal(\$var, \$val) { if (!isset(\$this-\>data['sub'])) { \$this-\>data['sub'] = array(); } if (!isset(\$this-\>data['sub'][\$var])) { \$this-\>data['sub'][\$var] = array(); } \$this-\>data['sub'][\$var] = array\_merge(\$this-\>data['sub'][\$var], (array) \$val); } function setUniqueArgs(\$val) { if (!is\_array(\$val)) return; // checking for associative array \$diff = array\_diff\_assoc(\$val, array\_values(\$val)); if (((empty(\$diff)) ? false : true)) { \$this-\>data['unique\_args'] = \$val; } } function setCategory(\$cat) { \$this-\>data['category'] = \$cat; } function addFilterSetting(\$filter, \$setting, \$value) { if (!isset(\$this-\>data['filters'])) { \$this-\>data['filters'] = array(); } if (!isset(\$this-\>data['filters'][\$filter])) { \$this-\>data['filters'][\$filter] = array(); } if (!isset(\$this-\>data['filters'][\$filter]['settings'])) { \$this-\>data['filters'][\$filter]['settings'] = array(); } \$this-\>data['filters'][\$filter]['settings'][\$setting] = \$value; } function asJSON() { \$json = json\_encode(\$this-\>data); // Add spaces so that the field can be folded \$json = preg\_replace('/(["\\]}])([,:])(["\\[{])/', '\$1\$2 \$3', \$json); return \$json; } function as\_string() { \$json = \$this-\>asJSON(); \$str = "X-SMTPAPI: " . wordwrap(\$json, 76, "\\n "); return \$str; } } ?\> {% endcodeblock %} 
{% anchor h2 %} Example PHP Usage {% endanchor %}
 {% codeblock lang:php %} <?php include "SmtpApiHeader.php" ; $hdr="new" smtpapiheader(); $receiver="array(" "kyle@somewhere.com" , "bob@someplace.net" , "someguy@googlemailz.coms" ); $times="array(" "1pm" , "2pm" , "3pm" ); $names="array(" "kyle" , "bob" , "someguy" ); $hdr- ?>addFilterSetting('subscriptiontrack', 'enable', 1); \$hdr-\>addFilterSetting('twitter', 'enable', 1); \#please check the apps available for your current package at www.sendgrid.com/pricing.html ? \$hdr-\>addTo(\$receiver); \$hdr-\>addSubVal('-time-', \$times); \$hdr-\>addSubVal('-name-', \$names); \$hdr-\>setUniqueArgs(array( 'test' =\> 1, 'foo' =\> 2 )); echo \$hdr-\>as\_string(); echo "\\n"; ?\> {% endcodeblock %}
