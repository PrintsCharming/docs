---
layout: page
weight: 0
title: Mail
navigation:
  show: true
---

This endpoint allows you to send email.


{% anchor h2 %} send {% endanchor %}


Send email.

<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter

</th>
<th markdown="1">
Required

</th>
<th markdown="1">
Requirements

</th>
<th markdown="1">
Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
to

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be a valid email address

</td>
<td markdown="1">
This can also be passed in as an array, to send to multiple locations. Note that recipients passed in this parameter will be visible as part of the message. If you wish to hide the recipients, use the TO parameter in the [x-smtpapi]({{root_url}}/API_Reference/SMTP_API/index.html) header.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
toname

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Must be a string. If *to* parameter is an array, *toname* must be an array with the exact number of array elements as the *to* field

</td>
<td markdown="1">
Give a name to the recipient

</td>
</tr>
<tr markdown="1">
<td markdown="1">
x-smtpapi

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Must be in valid JSON format

</td>
<td markdown="1">
Please review the [SMTP API]({{root_url}}/API_Reference/SMTP_API/index.html) to view documentation on what you can do with the JSON headers

</td>
</tr>
<tr markdown="1">
<td markdown="1">
subject

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be a valid string

</td>
<td markdown="1">
The subject of your email

</td>
</tr>
<tr markdown="1">
<td markdown="1">
text and/or html

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must include one or both parameters

</td>
<td markdown="1">
The actual content of your email message. It can be sent as either plain text or HTML for the user to display

</td>
</tr>
<tr markdown="1">
<td markdown="1">
from

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be a valid email address from your domain

</td>
<td markdown="1">
This is where the email will appear to originate from for your recipient

</td>
</tr>
<tr markdown="1">
<td markdown="1">
bcc

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Must be a valid email address

</td>
<td markdown="1">
This can also be passed in as an array of email addresses for multiple recipients

</td>
</tr>
<tr markdown="1">
<td markdown="1">
fromname

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Must a valid string

</td>
<td markdown="1">
This is name appended to the from email field. IE - Your name or company name

</td>
</tr>
<tr markdown="1">
<td markdown="1">
replyto

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Must be a valid email address

</td>
<td markdown="1">
Append a reply-to field to your email message

</td>
</tr>
<tr markdown="1">
<td markdown="1">
date

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Must be a valid [RFC 2822 formatted date](http://www.faqs.org/rfcs/rfc2822)

</td>
<td markdown="1">
Specify the date header of your email. One example: "Thu, 21 Dec 2000 16:01:07 +0200". PHP developers can use: *date('r');*

</td>
</tr>
<tr markdown="1">
<td markdown="1">
files

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Must be less than 7MB

</td>
<td markdown="1">
Files to be attached. The file contents must be part of the multipart HTTP POST. Ex: files[file1.jpg]=<file contents>&files[file2.pdf]=<file contents>  
 [Example Code (PHP)]({{root_url}}/Code_Examples/php.html#-Using-Attachments)

</td>
</tr>
<tr markdown="1">
<td markdown="1">
content

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Required for sending inline images

</td>
<td markdown="1">
Content IDs of the files to be used as inline images. Content IDs should match the cid's used in the HTML markup. Ex: content[file1.jpg]=ii\_139db99fdb5c3704 would correspond with the HTML `<img src="cid:ii_139db99fdb5c3704">`

</tr>
<tr markdown="1">
<td markdown="1">
headers

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Must be in valid JSON format without integers

</td>
<td markdown="1">
A collection of key/value pairs in JSON format. Each key represents a header name and the value the header value. Ex: {"X-Accept-Language": "en", "X-Mailer": "MyApp"}

</td>
</tr>
</tbody>
</table>
{% xmljsontabs mail %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="mail-json">
### Call: Send to One Recipient



{% codeblock %}
https://sendgrid.com/api/mail.send.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&to=destination@example.com&toname=Destination&subject=Example_Subject&text=testingtextbody&from=info@domain.com
{% endcodeblock %}
<h3>Call: Send to Multiple Recipients
{% codeblock lang:bash %}
https://sendgrid.com/api/mail.send.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&to[]=destination@example.com&toname[]=Destination&to[]=destination2@example.com&toname[]=Destination2&subject=Example_Subject&text=testingtextbody&from=info@domain.com
{% endcodeblock %}



### Response: Success




{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




### Response: Error




{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="mail-xml">
### Call: Send to One Recipient



{% codeblock %}
https://sendgrid.com/api/mail.send.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&to=destination@example.com&toname=Destination&subject=Example_Subject&text=testingtextbody&from=info@domain.com
{% endcodeblock %}
<h3>Call: Send to Multiple Recipients
{% codeblock lang:bash %}
https://sendgrid.com/api/mail.send.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&to[]=destination@example.com&toname[]=Destination&to[]=destination2@example.com&toname[]=Destination2&subject=Example_Subject&text=testingtextbody&from=info@domain.com
{% endcodeblock %}



### Response: Success




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   success
   <result>
</result>
</result>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      <error>...</error>
      ...
   </errors>
   @nodes
</result>

{% endcodeblock %}




</div>
</div>

* * * * *

### cURL Examples

Send to one email recipient



{% codeblock lang:bash %}
$ curl -d 'to=destination@example.com&toname=Destination&subject=Example Subject&text=testingtextbody&from=info@domain.com&api_user=your_sendgrid_username&api_key=your_sendgrid_password' https://sendgrid.com/api/mail.send.json
{% endcodeblock %}



Send to multiple email recipients



{% codeblock lang:bash %}
$ curl -d 'to[]=destination@example.com&toname[]=Destination&to[]=destination2@example.com&toname[]=Destination2&subject=Example Subject&text=testingtextbody&from=info@domain.com&api_user=your_sendgrid_username&api_key=your_sendgrid_password' https://sendgrid.com/api/mail.send.json
{% endcodeblock %}



Send a test with attachment



{% codeblock lang:bash %}
$ curl https://sendgrid.com/api/mail.send.json \
-F to=recipient@domain.com -F toname=test -F subject="Example Subject" \
-F text="testing text body" --form-string html="<strong>testing html body</strong>" \
-F from=test@yourdomain.com -F api_user=your_sendgrid_username -F api_key=your_sendgrid_password \
-F files[attachment.gz]=@f.php.gz https://sendgrid.com/api/mail.send.json
{% endcodeblock %}



<span class="label label-info">Note</span> To ensure that it uploads from a local file, use \<@filename\>.

Send a test specifying the file content type by appending ';type=<mime type>' to the file name



{% codeblock lang:bash %}
$ curl https://sendgrid.com/api/mail.send.json \
-F to=recipient@domain.com -F toname=test -F subject="Example Subject" \
-F text="testing text body" --form-string html="<strong>testing html body</strong>" \
-F from=test@yourdomain.com -F api_user=your_sendgrid_username -F api_key=your_sendgrid_password \
-F files[attachment.pdf]=@attachment.pdf;type=application/pdf
{% endcodeblock %}



### Raw HTTP Dump

The following is a dump of the HTTP data sent to our server to generate an email via our web API.



{% codeblock %}
POST /api/mail.send.json HTTP/1.1
{% endcodeblock %}

{% codeblock %}
Host: sendgrid.com

Accept: */*

Content-Length: 999

Expect: 100-continue

Content-Type: multipart/form-data; boundary=----------------------------400f182a9360

HTTP/1.1 100 Continue

------------------------------400f182a9360

Content-Disposition: form-data; name="api_user"

YOURUSERNAME

------------------------------400f182a9360

Content-Disposition: form-data; name="api_key"

YOURKEY

------------------------------400f182a9360

Content-Disposition: form-data; name="to"

someone@somewhere.com

------------------------------400f182a9360

Content-Disposition: form-data; name="subject"

test of file sends

------------------------------400f182a9360

Content-Disposition: form-data; name="html"

the HTML

------------------------------400f182a9360

Content-Disposition: form-data; name="text"

the plain text

------------------------------400f182a9360

Content-Disposition: form-data; name="from"

example@sendgrid.com

------------------------------400f182a9360

Content-Disposition: form-data; name="files[myfile]"; filename="myfile"

Content-Type: application/octet-stream

file with stuff in it

------------------------------400f182a9360--

HTTP/1.1 200 OK

Server: nginx/0.7.65

Date: Fri, 03 Jun 2011 22:30:58 GMT

Content-Type: application/json

Transfer-Encoding: chunked

Connection: keep-alive

{% endcodeblock %}

 {% codeblock %} {"message":"success"} {% endcodeblock %}
