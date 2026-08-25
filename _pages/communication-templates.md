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
2. Navigate to the Admin module, and select `Communication` -> `Communication Templates`
3. Click the `+` symbol to create a new template
4. Enter `Responsive Template` into Name
5. Optionally provide your template with a description. This can be used to identify what they are used for if you have multiple templates in your system.
6. Paste the source code for your template into the Template field. An example template is [included below](#example-template). In the default (responsive) interface the Template field is a plain text field you paste HTML into directly. In desktop mode, an `Edit` button opens a rich editor instead - click `Source` to switch it to source code mode, paste your HTML, and click `Apply`.
7. Within your template, you must tell Skyve where the body of the email will be inserted. For example, if your template contains a header and a footer, the email body will sit in-between. To tell Skyve where this should be inserted, the expression `{body}` must appear somewhere within the email template. The Template field is pre-filled with `<p>{body}</p>` when you create a new template, so edit around it rather than adding it from scratch - a template cannot be saved without `{body}`.
8. Click `OK`
9. Now we can use our template in a Communication. Open an existing Communication, or create a new one following the guide [here]({{ site.url }}{{ site.baseurl }}/communication).
10. With our communication open, we can then select the template we just created from the `Communication Template` drop-down at the bottom of the `Contents` tab.

    ![Select template]({{ site.url }}{{ site.baseurl }}/assets/images/communication-template/comm-template-2.png)

11. You can now send the email to tagged recipients, or use the `Test Send to yourself` button on the `Manage` tab to send a test email (this requires at least one tagged record).

#### Example Template
An example of a basic HTML template which can be used as a communication template is included here. This is a modified version of the inline template from the [responsive-html-email-template](https://github.com/leemunroe/responsive-html-email-template) project on GitHub.

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