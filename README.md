# Sending-Emails-with-Python
a)A simple Python method to send email. You can use this Python method to:

1.Notify you whenever a long process is done.
2.Send email to anyone.


b)Installation

1.Create a new GMail account just for this purpose (You may use your current GMail but not it's not recommended because you will need to turn off 2 Factor Authentication, which makes your account less secure).
2.Login to your new GMail account and go to, https://www.google.com/settings/security/lesssecureapps.
3.Toggle "Allow less secure apps" to be "ON": img

4.Copy the Python method in send_email.py and paste it in your code.(Or you may just copy the code from below):
def send_email(sendto, subject, text):
    username = "YOUR_NEW_EMAIL" # Change this!
    password = "YOUR_NEW_EMAIL_PASSWORD" # Change this!
    for i in range(3):
        try:
            print("Sending Email to {} (trial {})...".format(sendto, i+1))
            import smtplib
            server = smtplib.SMTP('smtp.gmail.com', 587)
            server.starttls()
            server.login(username, password)
            msg = 'Subject: {}\n\n{}'.format(subject, text)
            server.sendmail(username, sendto, msg)
            server.quit()
            print("Email sent!")
            break
        except Exception as e:
            print("Failed to send email due to Exception:")
            print(e)
5.Remember to change YOUR_NEW_EMAIL and YOUR_NEW_EMAIL_PASSWORD to your newly registered email credentials.
6.Call the method like so:

send_email("ReceiverEmail", "EmailTitle", "EmailBody")

c)Troubleshoot
If you run the code from an unfamiliar device or from an IP of a different country, Google might block you immediately from logging in. To resolve that, follow the following steps:

Sign in to your new GMail account from your browser.
Head on to https://accounts.google.com/DisplayUnlockCaptcha.
Click the "Continue" button to allow access.
Finally, try logging in using the code again.
