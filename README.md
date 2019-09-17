# myraveapp
Implementation of inline payment for rave in ionic 4/5

# Prerequisites

TypeScript,
JavaScript,
CSS and Sass,
HTML.

# Installing Ionic CLI 5 and Cordova
npm install -g ionic cordova

ionic start


# Instance Members
# Rave
init(PRODUCTION_FLAG, PUBLIC_KEY)

You must call the init method with the PRODUCTION_FLAG set to true or false and your PUBLIC KEY. If your production flag is set to true, you will need to pass in your live public key otherwise, you pass in your sandbox public key

Returns: Promise
preRender(validatedPaymentObject) You must preconnect to Rave to obtain a secure link that will enable you to load the payment UI. Prior to calling this method you must have called RavePayment.create() to validate your payment object.

Returns: Promise
render(paymentLink) Start the Rave UI to collect payment from user.

Returns: InAppBrowserObject
Use the InAppBrowserObject returned to close the modal once the transaction completes by binding to the loadend event and checking for your redirect url as was shown above.

paymentStatus(url) Get's the status of the transaction and returns it as a string. The status could either be success or ````failed```.

Parameter(s)

url: this is the url gotten from the inappbroswer event event.url

Returns: String

You should use the returned status to determine whether or not you shoud show a success or error message to your users.

NOTE: IOS users may still need to rely on the Done button at the bottom left of the opened.

Rave Payment
create(paymentObject) You must validate the paymentObject you want to use to load the Rave payment UI. See https://developer.flutterwave.com/docs/rave-inline-1 for more documentation of the parameters.

Returns: Object (either an error or your validated payment object)
amount() The amount of the payment

email() The customer's email

txref() The transaction reference of the payment

currency() The currency of the payment
