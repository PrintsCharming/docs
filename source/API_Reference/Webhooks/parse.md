<div class="WordSection1">
<o:p> </o:p>

</div>
[from] =\> \\"SendGrid Test 2\\" <send.grid.test@gmail.com> [text] =\> [envelope] =\> {\\"to\\":[\\"test@sendgrid.biz\\"],\\"from\\":\\"send.grid.test@gmail.com\\"} [charsets] =\> {\\"to\\":\\"UTF-8\\",\\"html\\":\\"us-ascii\\",\\"subject\\":\\"UTF-8\\",\\"from\\":\\"UTF-8\\",\\"text\\":\\"us-ascii\\"} [SPF] =\> pass ) {% endcodeblock %} If you have an attachment, there will be a 2nd array, as follows: {% codeblock %} Array ( [attachment1] =\> Array ( [name] =\> Upload.csv [type] =\> text/csv [tmp_name] =\> /tmp/phpo34iHI [error] =\> 0 [size] =\> 76 ) ) {% endcodeblock %}
