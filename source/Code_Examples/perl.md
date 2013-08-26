Some html [SG](http://sendgrid.com)

' ); \#disable click tracking filter for this request \$sg-\>disableClickTracking(); \#turn on the unsubscribe filter here with custom values \$sg-\>enableUnsubscribe( text =\> "Unsubscribe here: \<% %\>", html =\> "Unsubscribe \<% here %\>" ); \#set a category \$sg-\>header-\>setCategory('first contact'); \#add unique arguments \$sg-\>header-\>addUniqueIdentifier( customer =\> '12345', location =\> 'somewhere' ); my \$trans = Mail::SendGrid::Transport::SMTP-\>new( username =\> 'sendgrid\_username', password =\> 'sendgrid\_password' ); my \$error = \$trans-\>deliver(\$sg); die \$error if ( \$error ); {% endcodeblock %} 
{% anchor h2 %} Without sendgrid-perl {% endanchor %}
 The following code builds a MIME mail message demonstrating all the portions of the SMTP API protocol. To use this example, you will need to have the following perl modules installed:

-   [MIME::Entity](http://search.cpan.org/perldoc?MIME::Entity)
-   [Authen::SASL](http://search.cpan.org/perldoc?Authen::SASL)



{% codeblock lang:perl %}
use warnings;
use strict;

use Mail::SendGrid;
use Mail::SendGrid::Transport::SMTP;

my $sg = Mail::SendGrid->new( from => 'from@example.com',
                              to => 'to@example.com',
                              subject => 'Testing',
                              text => "Some text http://sendgrid.com/\n",
                              html => '<html><body>Some html
                                                  <a href="http://sendgrid.com">SG</a>
                                       </body></html>' );

#disable click tracking filter for this request
$sg->disableClickTracking();

#turn on the unsubscribe filter here with custom values
$sg->enableUnsubscribe( text => "Unsubscribe here: <% %>", html => "Unsubscribe <% here %>" );

#set a category
$sg->header->setCategory('first contact');

#add unique arguments
$sg->header->addUniqueIdentifier( customer => '12345', location => 'somewhere' );

my $trans = Mail::SendGrid::Transport::SMTP->new( username => 'sendgrid_username', password => 'sendgrid_password' );

my $error = $trans->deliver($sg);
die $error if ( $error );
{% endcodeblock %}


