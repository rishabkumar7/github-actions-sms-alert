# github-actions-sms-alert
SMS alerts when GitHub action fails using Twilio

### Prerequisites
What you’ll need for this:
- A Twilio Account. [Sign up for free](twilio.com/try-twilio)
- A Twilio phone number
- A [Twilio API Key and Secret](https://www.twilio.com/docs/iam/keys/api-key)
- GitHub Actions

We will be using the [Twilio SMS Action](https://github.com/marketplace/actions/twilio-sms) from the Actions marketplace.
- Set up your credentials as secrets in your repository settings using `TWILIO_ACCOUNT_SID`, `TWILIO_API_KEY`, `TWILIO_API_SECRET`

- Add the following to your workflow
``` yaml
- name: 'Sending SMS Notification'
  uses: twilio-labs/actions-sms@v1
  with:
    fromPhoneNumber: '+1(234)5678901'
    toPhoneNumber: '+1(234)3334444'
    message: 'Hello from Twilio'
  env:
    TWILIO_ACCOUNT_SID: ${{ secrets.TWILIO_ACCOUNT_SID }}
    TWILIO_API_KEY: ${{ secrets.TWILIO_API_KEY }}
    TWILIO_API_SECRET: ${{ secrets.TWILIO_API_SECRET }}
```
