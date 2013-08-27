---
layout: page
weight: 0
title: Sending Practices and Limitations
navigation:
  show: true
---

As you begin to use your SendGrid account there are some important things to remember. For example, Lite and Free packages have limitations in the amount of email that can be sent each day. Free accounts are simply limited to 200 emails per day, but the [equation]({{root_url}}/User_Guide/sending_practices.html) for Lite packages is bit more complex.

Additionally, there are limitations to delivery rates imposed by recipient mail servers. Exceeding these limitations results in a practice referred to as throttling. Throttling in terms of email means that a recipient mail server has accepted all the mail it is willing to accept from your IP for a certain period of time.

If you have a Silver or higher package, you may want to read how to warm up your IP address to avoid having your outbound messaging throttled. [We've got a great page on warming up your IP just for that]({{root_url}}/User_Guide/warming_up.html)!


{% anchor h2 %} Lite Plan Volume Restrictions {% endanchor %}


Our Lite package has a bandwidth restriction to keep spammers from abusing our system. For the first 7 days you will be limited to 1,000 emails per day. After the 7th day we look into how many emails you have sent, how many days your account has been active, and check your reputation status. As the value of each of these parameters increases, your volume limitations will decrease.

As you achieve each guideline after the 7-day period, your account limit will be raised incrementally. You must achieve all guidelines in one row before you can achieve any guideline on the next row. The below table lists the limitation factors, and how they affect your total.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Account Age</th>
         <th>Email Requests</th>
         <th>Send Reputation</th>
         <th>Daily Send Limit</th>
      </tr>
      <tr>
         <td>0 days</td>
         <td>--</td>
         <td>--</td>
         <td>1,000</td>
      </tr>
      <tr>
         <td>7 days *Adds 3,000*</td>
         <td>50,000 *Adds 3,000*</td>
         <td>80% *Adds 3,000*</td>
         <td>10,000</td>
      </tr>
      <tr>
         <td>14 days *Adds 30,000*</td>
         <td>500,000 *Adds 30,000*</td>
         <td>90% *Adds 30,000*</td>
         <td>100,000</td>
      </tr>
      <tr>
         <td>28 days *Adds 300,000*</td>
         <td>5,000,000 *Adds 300,000*</td>
         <td>95% *Adds 300,000*</td>
         <td>1,000,000</td>
      </tr>
   </tbody>
</table>

For example:

-   If you have a 10 day old account (+3,000), have sent 10,000 messages (+0), and have a reputation of 91% (+3,000), you would have a Daily Send Limit of 7,000.
-   If you have a 15 day old account, have sent 49,000 messages, and have a reputation of 99%, you would have a Daily Send Limit of 7,000, because you can't achieve the 14-day guideline until you achieve the 50,000-messages guideline.

Please note that if your reputation declines, your limit will decrease accordingly. All these values are checked overnight, so they won't update the moment you reach the next increment of any given parameter.


{% anchor h2 %} Peer Initiated Invitation Requirements {% endanchor %}


A peer-initiated invitation system can help your subscribers spread the word about your service and grow your user base—if done well. An aggressive invitation system can backfire, and your invitations will be filtered or blocked. SendGrid customers who implement a peer-initiated invitation system must abide by the following requirements:

-   **Never allow your subscribers to send invitations to their entire address book.**Address books contain old, stale addresses that ISPs use as spam traps. A spam trap is an address that doesn't send mail, and marks the mail it does receive as spam. If your invitations hit spam traps, your subsequent messages will be filtered by ISPs. To prevent this, design your invitation system so that your inviter must deliberately select each individual invitee.
-   **Limit the number of invitations each customer can send to encourage selective, quality invitations.**When your customers are careful to invite only those who they think will appreciate your service, you reduce the risk of invitees reporting the invitations as spam. If enough people report your invitations as spam, your invitations will be blocked or filtered—not what you intended.
-   **Clearly display the inviter's name or email address**, so the invitee knows who sent the invitation. (Peer-initiated invitations are most effective when the invitee knows and trusts the inviter.)
-   **The invitation messages' From address must reflect your brand.** Don't use the inviter's email address for the invitation's From address.
-   **Clearly express the purpose of the invitation.**Recipients must understand what they are being invited to.
-   **After the initial invitation, don't send more than one follow-up** (reminder) email to invitees that didn't respond to the first invitation.


{% info %} You increase the odds of your invitations reaching the recipient when you structure your systems and processes to send the right message, to the right person, at the right time, with the right frequency. If you don't, your messages will be marked as spam and your marketing results will suffer. {% endinfo %}
 SendGrid also strongly recommends:  

-   Ensure your invitation is relevant and valued by the recipient.
-   Let your inviters add a personal text-only message to their invitation. (No URLs, as they may be used to exploit or infect the invitee.)
-   Include a conspicuous, functioning opt-out link—it's better for the recipient to remove themselves from future mailings than to report your message as spam.
-   Beware of offering invitation incentives to your subscribers. Incentives may encourage them to invite people who aren't likely to want your service, and this could lead to backlash.
-   Monitor your spam complaints. Some inviters will trigger spam complaints by sending invitations to people who don't want them. If your system correlates spam complaints with the troublesome inviter, you can limit their invitation quota to minimize the adverse effect on your email sending reputation.
-   Typos happen. Pre-screen the email addresses you collect before you send the invitation. Ensure addresses are syntactically correct, and that the domain part of the address has a DNS MX record (which indicates that the domain accepts mail).

