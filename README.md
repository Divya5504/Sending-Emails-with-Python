# Sending-Emails-with-Python
A simple Python method to send email. You can use this Python method to:

Notify you whenever a long process is done.
Send email to anyone.
Installation
Create a new GMail account just for this purpose (You may use your current GMail but not it's not recommended because you will need to turn off 2 Factor Authentication, which makes your account less secure).
Login to your new GMail account and go to, https://www.google.com/settings/security/lesssecureapps.
Toggle "Allow less secure apps" to be "ON": img
Copy the Python method in send_email.py and paste it in your code.(Or you may just copy the code from below):
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
Remember to change YOUR_NEW_EMAIL and YOUR_NEW_EMAIL_PASSWORD to your newly registered email credentials.
Call the method like so:
send_email("ReceiverEmail", "EmailTitle", "EmailBody")
Troubleshoot
If you run the code from an unfamiliar device or from an IP of a different country, Google might block you immediately from logging in. To resolve that, follow the following steps:

Sign in to your new GMail account from your browser.
Head on to https://accounts.google.com/DisplayUnlockCaptcha.
Click the "Continue" button to allow access.
Finally, try logging in using the code again.
