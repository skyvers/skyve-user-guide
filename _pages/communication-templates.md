---
title: "Communication Templates"
permalink: /communication-templates/
excerpt: "Configuring and using Communication Templates within a Skyve application."
toc: true
sidebar:
  title: "Index"
  nav: docs
---
Communication templates are designed to be used as a rich email template, to support common headers and footers for your application. The template is wrapped around the HTML of a [Communication]({{ site.url }}{{ site.baseurl }}/communication).

### Create a new Communication Template

1. Login with a user which has the `ContactManager` or `SecurityAdministrator` role
2. From the top right hand corner, switch to power user mode if not already in there

    ![Switch mode]({{ site.url }}{{ site.baseurl }}/assets/images/switch.png)
    
3. Navigate to the Admin module, and select `Communication Templates`
4. Click the `+` symbol to create a new template
5. Enter `Responsive Template` into Name
6. Optionally provide your template with a description. This can be used to identify what they are used for if you have multiple templates in your system.
7. To the right of the Template field, click `Edit`
8. As we are creating a HTML email template, we need to edit the source code. This is not a requirement, and basic layout can be created using the editor, but HTML is required to completely style an email. Click the `Source` button to switch the editor to source code mode.

    ![Source button]({{ site.url }}{{ site.baseurl }}/assets/images/communication-template/comm-template-1.png)

9. Paste the source code for your template into the editor. An example template is [included below](#example-template).
10. Within your template, you must tell Skyve where the body of the email will be inserted. For example, if your template contains a header and a footer, the email body will sit in-between. To tell Skyve where this should be inserted, we add the expression `{body}` somewhere within our email template.
11. Click `Apply` once the template source and `{body}` have been added
12. Click `OK`
13. Now we can use our template in a Communication. Open an existing Communication, or create a new one following the guide [here]({{ site.url }}{{ site.baseurl }}/communication).
14. With our communication open, we can then selcet the template we just created from the `Contents` tab.

    ![Select template]({{ site.url }}{{ site.baseurl }}/assets/images/communication-template/comm-template-2.png)

15. You can now send the email to tagged recipients, or use the Test Send to yourself button to send a test email.

#### Example Template
An example of a basic HTML template which can be used as a communcation template is included here. This is a modified version of the inline template from the [responsive-html-email-template](https://github.com/leemunroe/responsive-html-email-template) project on GitHub.

```html
<!doctype html>
<html>
    <head>
        <meta name="viewport" content="width=device-width">
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    </head>
    <body style="background-color: #f6f6f6; font-family: sans-serif; -webkit-font-smoothing: antialiased; font-size: 14px; line-height: 1.4; margin: 0; padding: 0; -ms-text-size-adjust: 100%; -webkit-text-size-adjust: 100%;">
        <table border="0" cellpadding="0" cellspacing="0" class="body" style="background-color:#f6f6f6; border-collapse:separate; mso-table-lspace:0pt; mso-table-rspace:0pt; width:100%">
            <tbody>
                <tr>
                    <td style="vertical-align:top">&nbsp;</td>
                    <td style="vertical-align:top; width:580px">
                    <div class="content" style="box-sizing: border-box; display: block; Margin: 0 auto; max-width: 580px; padding: 10px;">
                    <table class="main" style="background:#ffffff; border-collapse:separate; border-radius:3px; mso-table-lspace:0pt; mso-table-rspace:0pt; width:100%">
                    <!-- START MAIN CONTENT AREA -->
                        <tbody>
                            <tr>
                                <td style="vertical-align:top">{body}</td>
                            </tr>
                        </tbody>
                    </table>
                    <!-- END CENTERED WHITE CONTAINER -->
                    <!-- START FOOTER -->
                    <div class="footer" style="clear: both; Margin-top: 10px; text-align: center; width: 100%;">
                    <table border="0" cellpadding="0" cellspacing="0" style="border-collapse:separate; mso-table-lspace:0pt; mso-table-rspace:0pt; width:100%">
                        <tbody>
                            <tr>
                                <td style="text-align:center; vertical-align:top"><span style="color:#999999; font-size:12px">Company Inc, 123 Fake Street, Springfield OH 45505</span></td>
                            </tr>
                            <tr>
                                <td style="text-align:center; vertical-align:top">Powered by <a href="https://skyve.org" style="color: #999999; font-size: 12px; text-align: center; text-decoration: none;">Skyve</a>.</td>
                            </tr>
                        </tbody>
                    </table>
                    </div>
                    <!-- END FOOTER --></div>
                    </td>
                    <td style="vertical-align:top">&nbsp;</td>
                </tr>
            </tbody>
        </table>
    </body>
</html>
```