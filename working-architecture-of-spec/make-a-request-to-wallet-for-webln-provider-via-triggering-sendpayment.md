---
description: First Step - Triggering extended sendPayment method
---

# ☎ Trigger SendPayment Method

Bitcoin Lightning-driven web application using the WebLN standard can request for WebLN provider by triggering `SendPayment` method.

\
Provider passed by the wallet to the client shall contain an extended definition of the `SendPayment` method.

```
sendPayment(paymentRequest: string, metadata?: string): Promise<SendPaymentResponse>;
```

### WebLN Provider by Alby&#x20;

Alby uses an extended version of the WebLN provider when triggered, provides `SendPayment` method containing optional parameter `metadata`.

![WebLN provider attached by wallets after the implementation of this spec](<../.gitbook/assets/image (3).png>)
