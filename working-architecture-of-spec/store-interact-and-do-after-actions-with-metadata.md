---
description: Step Five - Store, Interact and Do After Actions
---

# 📀 Store, Interact and Do After Actions

Once the user confirms their payment and the transaction gets successful, wallets can play with the received metadata, and lightning-driven web apps can do some after actions after receiving the payments.

### Processing of Metadata By WebLN Powered Bitcoin Lightning Wallets and Browser Extensions

Wallets can store the metadata in their transaction database and render it so that users to interact with the metadata.

Metadata can be rendered in transaction lists, providing more insights into each transaction to the user, and making it more interactive. Wallets can interact with metadata in different ways to create visual spending breakdowns from the metadata, letting the user spend a digital coupon provided as metadata and many more.

### After Actions Performed by Bitcoin Lightning Driven Web Apps

Once the payment is successful, we can allow the user to access the purchased content; after the successful payment, the client application can permit the user to download a song.

After actions can be performed in the **SendPayment** callback function as follows:

```
webln.sendPayment(invoice, metadata)
  .then(function (r) {
    // Required constraint to protect metadata as a rule while paying empty invoices
    if (r != undefined) {
      // Provide metadata after successful payment
      // Eg. Allow users to download a song after payment is successful
    }
  })
  .catch(function (e) {
    alert("Failed: " + e.message);
    console.log('err pay:', e);
   });
```
