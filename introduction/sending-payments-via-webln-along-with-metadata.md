# 📑 Extending SendPayment Method

WebLN _**SendPayment**_ which takes _**paymentRequest**_ parameter holding[ Bolt11 invoice](https://github.com/lightning/bolts/blob/master/11-payment-encoding.md), we can extend this function to add an extra “optional” parameter named _**metadata**_ which will hold metadata as a string which can be passed to the Wallets.

_**Function Signature:**_

```
sendPayment(paymentRequest: string, metadata?: string): Promise<SendPaymentResponse>;
```

**WebLN Provider attached by wallets before**

![WebLN provider attachted by wallets before](<../.gitbook/assets/image (2).png>)

**WebLN Provider attached by wallets after implementation of this spec**

![WebLN provider attached by wallets after ](<../.gitbook/assets/image (1).png>)

### Passing Metadata Via SendPayment Method

As an extended version of the `SendPayment` method is implemented by the wallet and is sent to the WebLN-enabled client. Clients can now pass metadata along with Invoice using such function.

\
_Example:_

```
webln.sendPayment(invoice, metadata)
  .then(function (r) {
    // Required constraint to protect Metadata, as a rule when empty invoices are paid
    if (r != undefined) {
      // Provide Metadata after successful Payment
      // eg. Allow user to download a song after payment is successful
    }
  })
```
