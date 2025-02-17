---
type: rule
title: Quality - Do you know how to request a "test please"?
uri: request-a-test-please
authors:
  - title: Adam Cogan
    url: https://ssw.com.au/people/adam-cogan
  - title: Tiago Araujo
    url: https://ssw.com.au/people/tiago-araujo
related:
  - do-you-send-as-per-our-conversation-emails
  - do-you-know-when-to-do-use-checked-by-xxx
  - conduct-a-test-please-internally-and-then-with-the-client
redirects:
  - quality-do-you-know-how-to-request-a-test-please
created: 2015-08-26T19:03:34.000Z
archivedreason: null
guid: dda8e03b-f5a1-4dea-967e-cfda36fbda95

---

These are the steps you should take when request a "test please":

<!--endintro-->

1. Find 2 free testers to send the email below
2. Stop working on the project until you receive either a "pass" or "fail" email
3. Create your "test please" following this template:

::: email-template  
|          |     |
| -------- | --- |
| To:      | John |
| Subject: | Test Please - Product Name v1.11 |  
::: email-content  

### Hi John,  
I am looking for bugs or approval to release this version.

1. Please test the following modifications:

* {{ FEATURE TO BE TESTED }}
* {{ FEATURE TO BE TESTED }}

I have done what I could for my code's health. E.g.

* Run SSW Code Auditor - it has {{ X }} errors (if not 0, give reason)
* Run SSW Link Auditor - it has {{ X }} errors (if not 0, give reason)
* Kept my eye on Application Insights

Specific issues to look out for are:

* {{ ISSUE }}
* {{ ISSUE }}

The latest version (Product Name v1.11) is at {{ URL }}

Keep in mind that a "test please" is an urgent task and that it should start within the hour.

**Note:**
* Know the [definition of a bug](/definition-of-a-bug)
* Understand the importance of testing. Read the rule on [Do you conduct a "test please" internally and then with the client?](/conduct-a-test-please-internally-and-then-with-the-client)
* Send suggestions/bugs one email at a time (with a unique email subject) because it makes it easier to fix and reply "done"
  * Please CC the project manager and the client
  * [Use good subjects on your emails](/good-email-subject)
* Do not reply to this message until you can say "**Test Please Succeeded** (as no Critical bugs). You are ready to deploy." or "**Test Please Failed** (as per Critical bugs reported)"

Regards,

:::
:::

::: info
**Note:** For clients on fixed-price contracts, the test please reply marks the start of the 30-day warranty period.
:::

### DO NOT send a 'Test Please' via Teams (with the content)

You should use Teams to point the tester to the 'Test Please' email:

::: greybox
"Ping!   
I need you to see my 'Test Please' email   
See subject: **Test Please - Product Name v1.11**"
:::

::: info
**Note to developers:**
If current version is better than the last version you can release (even with a test fail) as long:
- The bugs reported in the test fail existed in the old version
- Two people have tested it
- The changes in this version are fairly important to get out
- You get to work on the failures ASAP
:::

### What if you're doing a Windows Forms test?

Then you should also include this to the email:
- The latest version of {{Product Name}} has been uploaded to **\\frog\SSW\Download\[Application\_verX-XX\_beta.exe**
- Test on a fresh VPC image of Windows
- Install into a non-default directory
- Check the installation folder for misplaced items
- Test Unit Tests via "Help - Run Unit Tests"
- (If Applicable)Test the "Create" and "Reconcile" buttons. Read [Rules to Better .NET Projects](/rules-to-better-net-projects)
- Test open and closing forms and saving values
- Test most buttons and menus and links
- Disable your network connection and test again (check for unhandled errors)
- If your test fails, please rename the executable to **Application\_verX-XX\_failed.exe**

### What if you are doing an email test?

In most cases, you can follow [Do you use 'Checked by xxx'?](/checked-by-xxx)

For really important stuff you may need to actually send a 'Test Please' email to test your email. In these cases:

- DO NOT add 'Test Please' to the subject. (it is too easy to forget later!)
- Instead, add 'Test please' highlighted in yellow to the top of the email body

### What if you need to get input from a few people?

If you have received a task that requires input from a few people that were not originally cc'd on the email or on the ['To Myself'](/send-to-myself-emails), like getting feedback on a design, it's nice to give everyone the entire task context.

You have 2 options:

1. Keep the "test" in the same thread (recommended)  
   In this case, just add the people you need to the thread, asking them specifically for a 'test please' on what you need

2. Create a new thread for the 'test please'. This is for when you have a good reason not to (e.g. avoiding too long email threads; too many people cc'ed, etc).
   In this case, make sure you include the original thread subject in your email, so people know the main task is happening there

This way everyone will have the entire history of the task and its progress.
