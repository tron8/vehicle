# Introduction #

Add your content here.


---


# Links #
Someone once said:
> This sentence will be quoted in the future as the canonical example of a quote that is so important that it should be visually separate from the rest of the text in which it appears.

file1.cs
```
    protected void btnSend_Click(object sender, EventArgs e)
    {
        string name = txtName.Text;
        string email = txtEmail.Text;
        string order = txtOrder.Text;
        string subject = txtSubject.Text;
        string message = txtMessage.Text;

        MailMessage msg = new MailMessage();

        msg.IsBodyHtml = false;
        msg.From = new MailAddress(email);
        msg.To.Add(ConfigurationManager.AppSettings["PapersMail"]);
        msg.Subject = "ContactUs: "+subject;
        msg.Body = string.Format("From: {0}, E-Mail: {1}\n{2}", name, email, message);

        SmtpClient client = new SmtpClient(ConfigurationManager.AppSettings["SMTP"], 25);
        client.Credentials = CredentialCache.DefaultNetworkCredentials;
        client.DeliveryMethod = SmtpDeliveryMethod.Network;
        client.Send(msg);

        Navigation.ContactUsConfirm();
    }

```