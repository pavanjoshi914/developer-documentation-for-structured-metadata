# 💽Store, Interact and Do After Actions



Once the user confirms his/her payment and the transaction gets successful -

* In Bitcoin Lightning Wallet

We can store and render the metadata in the transaction database of the wallet allowing users to interact with the metadata.

* In Lightning Application

Once the payment is successful , we can allow the user to access his purchased content such as allowing user to download a song, once the payment is successful.

```
 webln.sendPayment(Bolt 11 invoice, Metadata)
          .then(function(r) {
            if(r != undefined){  
            // do after payment actions with the metadata. eg. allowing user to download song after payment is done 
          }
          })
          .catch(function(e) {
            alert("Failed: " + e.message);
            console.log('err pay:', e);
          });
    })
    .catch(function(e) {
      alert("Webln error, check console");
      console.log('err, provider', e);
    });
}
```
