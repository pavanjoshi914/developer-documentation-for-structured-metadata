---
description: Describes architecture of the spec
---

# ⚙ Introduction

This page describes the basic workflow of the current spec broken down into the five steps for different wallets trying to implement this spec.

![Spec Architecture](https://cdn-images-1.medium.com/max/3694/1\*Lz4JHjDty-jrWAV9eqcDPA.png)

### Workflow

* Trigger `SendPayment` method\
  \
  The lightning web application requests for WebLN provider by triggering `SendPayment` method.\
  \
  Provider passed by the wallet to the lightning web application shall contain an extended definition  of `SendPayment` method

```
sendPayment(paymentRequest: string, metadata?: string): Promise<SendPaymentResponse>;
```

* Structure and Pass Metadata\
  \
  Using `SendPayment` method, the lightning web application passes an invoice along with additional metadata. WebLN provider delivers such data to the wallets.\
  \
  Before passing metadata to the wallet using the `SendPayment` method, metadata shall present in a structured form using the data models provided in a comprehensive guide.

```
webln.sendPayment(invoice, metadata)
  .then(function (r) {
    // Required constraint to protect metadata as a rule while paying empty invoices
    if (r != undefined) {
      // Provide metadata after successful payment
      // Eg. Allow users to download a song after payment is successful
    }
  })
```

* Validate Metadata\
  \
  Wallets validate received metadata against predefined data models/schemas.\

* Render Metadata in Confirmation Dialogue\
  \
  ✅ If metadata is passed and is valid, it is rendered in confirmation dialogue along with payment details.\
  \
  &#x20;❌ If metadata is passed and is not valid, even if the invoice is valid, there might be a possibility of fraud, and wallets don't allow it to proceed further.\

* Store, Interact and Do After Actions\
  \
  If metadata passed to the wallet is valid, also an invoice is paid - store, interact and do after actions with metadata.

### Know More About Each Step

Follow our comprehensive guide to know more about each step and its implementation details.

{% content-ref url="make-a-request-to-wallet-for-webln-provider-via-triggering-sendpayment.md" %}
[make-a-request-to-wallet-for-webln-provider-via-triggering-sendpayment.md](make-a-request-to-wallet-for-webln-provider-via-triggering-sendpayment.md)
{% endcontent-ref %}

{% content-ref url="structure-metadata-and-pass-it-to-the-wallet-in-callback.md" %}
[structure-metadata-and-pass-it-to-the-wallet-in-callback.md](structure-metadata-and-pass-it-to-the-wallet-in-callback.md)
{% endcontent-ref %}

{% content-ref url="validate-metadata-wallets.md" %}
[validate-metadata-wallets.md](validate-metadata-wallets.md)
{% endcontent-ref %}

{% content-ref url="render-metadata-in-confirmation-dialogue-if-valid.md" %}
[render-metadata-in-confirmation-dialogue-if-valid.md](render-metadata-in-confirmation-dialogue-if-valid.md)
{% endcontent-ref %}

{% content-ref url="store-interact-and-do-after-actions-with-metadata.md" %}
[store-interact-and-do-after-actions-with-metadata.md](store-interact-and-do-after-actions-with-metadata.md)
{% endcontent-ref %}
