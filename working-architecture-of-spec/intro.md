---
description: Describes architecture of the spec
---

# ⚙ Introduction

This page describes the basic workflow of the current spec broken down into 5 basic steps for different wallets trying to implement this spec

![Spec Architecture](https://cdn-images-1.medium.com/max/3694/1\*Lz4JHjDty-jrWAV9eqcDPA.png)

### Workflow

* Trigger `SendPayment` method\
  \
  The Client's website requests for WebLN provider by triggering `SendPayment` method.\
  \
  Provider passed by the wallet to the client shall contain an extended definition  of `SendPayment` method

```
sendPayment(paymentRequest: string, metadata?: string): Promise<SendPaymentResponse>;
```

* Structure and Pass Metadata\
  \
  The Client passes the Invoice along with metadata via `SendPayment` method, which is delivered to the wallet through the Provider\
  \
  Before passing metadata, metadata needs to be structured following the data models provided in a comprehensive guide

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

* Validate Metadata\
  \
  Passed metadata is validated against predefined data models/schemas by wallets\

* Render Metadata in Confirmation Dialogue\
  \
  ✅ If metadata is passed and is valid, it is rendered in confirmation dialogue along with payment details.\
  \
  &#x20;❌ If metadata is passed and is not valid, even if the invoice is valid, it might be a case of fraud, we don't allow it to proceed further.\

* Store, Interact and Do After Actions\
  \
  If metadata is passed and is valid and the invoice is paid - store, interact and do after actions with metadata

### Know More About Each Step

Follow our comprehensive guide to know more about each step and their implementation details

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
