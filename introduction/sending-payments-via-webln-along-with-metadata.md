# Sending Payments Via WebLN Along With Metadata🧾



###

WebLN _**SendPayment**_ which takes _**paymentRequest**_ parameter holding Bolt11 invoice, we can extend this function to add an extra “optional” parameter named _**metadata**_ which will hold metadata as a string which can be passed to the Wallets.

_**Function Signature::**_

```
sendPayment(paymentRequest: string, metadata?: string): Promise<SendPaymentResponse>;
```

**WebLN Provider attached by wallets currently**

![](https://cdn-images-1.medium.com/max/2478/0\*xH3Ip4lBH\_1Xzj0S.png)

**WebLN Provider attached by wallets after implementation of spec**

![](https://cdn-images-1.medium.com/max/2000/0\*ck3K-T5O2haHBVqy.png)
