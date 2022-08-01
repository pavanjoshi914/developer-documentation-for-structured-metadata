# 📑 Extending SendPayment Method

WebLN _**SendPayment**_ which takes _**paymentRequest**_ parameter holding Bolt11 invoice, we can extend this function to add an extra “optional” parameter named _**metadata**_ which will hold metadata as a string which can be passed to the Wallets.

_**Function Signature::**_

```
sendPayment(paymentRequest: string, metadata?: string): Promise<SendPaymentResponse>;
```

**WebLN Provider attached by wallets currently**

![](https://cdn-images-1.medium.com/max/2478/0\*xH3Ip4lBH\_1Xzj0S.png)

**WebLN Provider attached by wallets after implementation of spec**

![](https://cdn-images-1.medium.com/max/2000/0\*ck3K-T5O2haHBVqy.png)

### Passing Metadata Via SendPayment Method

As an extended version of the `SendPayment` method is implemented by the wallet and is sent to the WebLN-enabled client. Clients can now pass metadata along with Invoice using such function.

\
_Example:_

```
webln.sendPayment(Invoice, Metadata)
          .then(function(r) {
            // Required constraint to protect Metadata, as a rule when empty 
            invoices are paid
            if(r != undefined){
              // Provide Metadata after successful Payment
              // eg. Allow user to download a song after payment is successful
            }
          })
```
