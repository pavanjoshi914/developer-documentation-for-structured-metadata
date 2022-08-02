# 📀 Store, Interact and Do After Actions

Once the user confirms his/her payment and the transaction gets successful wallets can play with metadata and lightning-driven web apps can do some after actions after receiving the payments -

### Processing of Metadata By WebLN Powered Bitcoin Lightning Wallets and Browser Extensions

We can store and render the metadata in the transaction database of the wallet allowing users to interact with the metadata.

Metadata can be rendered in transaction lists, providing more insights into each transaction to the user, and making it more interactive. Wallets can interact in any way, they can create a category-wise money spending wheel using the metadata, or allow the user to spend a digital coupon given in form of metadata and many more.

### After Actions Performed by Bitcoin Lightning Driven Web Apps

Once the payment is successful, we can allow the user to access his purchased content such as allowing user to download a song, once the payment is successful.

This can be done in SendPayment callback function as follows -

```
 webln.sendPayment(Bolt 11 invoice, Metadata)
          .then(function(r) {
            // Required constraint to protect Metadata, as a rule when empty 
            invoices are paid
            if(r != undefined){
              // Provide Metadata after successful Payment
              // eg. Allow user to download a song after payment is successful
            }
          })
          .catch(function(e) {
            alert("Failed: " + e.message);
            console.log('err pay:', e);
          });    
```
