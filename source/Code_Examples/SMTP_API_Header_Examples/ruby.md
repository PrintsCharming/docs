--- layout: page weight: 0 title: Ruby navigation: show: true ---

These examples require the [JSON Ruby Gem](http://json.rubyforge.org/).

{% anchor h2 %} SmtpApiHeader.rb {% endanchor %}

This header is required for each example.

{% codeblock lang:ruby %} \#!/usr/bin/ruby \# Version 1.0 \# Last
Updated 6/22/2009 require 'json' class SmtpApiHeader def initialize()
@data = {} end def addTo(to) @data['to'] ||= [] @data['to'] +=
to.kind\_of?(Array) ? to : [to] end def addSubVal(var, val) if not
@data['sub'] @data['sub'] = {} end if val.instance\_of?(Array)
@data['sub'][var] = val else @data['sub'][var] = [val] end end def
setUniqueArgs(val) if val.instance\_of?(Hash) @data['unique\_args'] =
val end end def setCategory(cat) @data['category'] = cat end def
addFilterSetting(fltr, setting, val) if not @data['filters']
@data['filters'] = {} end if not @data['filters'][fltr]
@data['filters'][fltr] = {} end if not
@data['filters'][fltr]['settings'] @data['filters'][fltr]['settings'] =
{} end @data['filters'][fltr]['settings'][setting] = val end def
asJSON() json = JSON.generate @data return
json.gsub(/(["\\]}])([,:])(["\\[{])/, '\\\\1\\\\2 \\\\3') end def
as\_string() json = asJSON() str = 'X-SMTPAPI: %s' %
json.gsub(/(.{1,72})( +|\$\\n?)|(.{1,72})/,"\\\\1\\\\3\\n") return str
end end {% endcodeblock %} {% anchor h2 %} Example Ruby Usage {%
endanchor %} {% codeblock lang:ruby %} \#!/usr/bin/ruby require
'SmtpApiHeader.rb' hdr = SmtpApiHeader.new receiver =
['kyle','bob','someguy'] time = '1pm' name = 'kyle' hdr.addTo(receiver)
hdr.addTo('kyle2') hdr.addSubVal('-time-', time) hdr.addSubVal('-name-',
name) hdr.addFilterSetting('subscriptiontrack', 'enable', 1)
hdr.addFilterSetting('twitter', 'enable', 1) \#please check the apps
available for your current package at www.sendgrid.com/pricing.html
hdr.setUniqueArgs({'test' =\> 1, 'foo' =\>2}) a = hdr.asJSON() a =
hdr.as\_string() print a print "\\n" {% endcodeblock %}
