# stripe-payout-failed-webhook-aws
Send an email if a Stripe connect payout failed 

## Setup
1. Verify the email addresses you're sending from and to in [Simple Email Service](https://console.aws.amazon.com/ses/home?region=us-east-1#verified-senders-email:).
This statically uses us-east-1. You may also want to follow the '[move out of sandbox](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/request-production-access.html)' instructions
2. Upload the cloudformation-stack's yaml file on [CloudFormation](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/template). You'll be prompted to enter a name as well as the email addresses you want to send from and to (which you verified in 1)
3. Copy the apiGatewayInvokeURL value from the output of the Cloudformation Stack
4. Add a new webhook in [Stripe](https://dashboard.stripe.com/webhooks), setting the Endpoint URL to the value you copied in 3, and selecting the payout.failed event
