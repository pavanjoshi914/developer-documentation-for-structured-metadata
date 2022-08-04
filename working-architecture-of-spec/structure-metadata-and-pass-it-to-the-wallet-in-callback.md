---
description: Second Step - Structure and pass metadata
---

# 🧱 󠁻󠁻Structure and Pass Metadata

### Structure Metadata

This specification uses data models derived from standards such as [schema.org](https://schema.org) to deliver structure to metadata and define some standard properties, which we use to describe metadata.

[**Schema.org**](http://schema.org) allows the structuring of data using **JSON-LD** format. **JSON-LD** is a **JSON** having an additional _`@context`_ field. We use the same schema to structure metadata without the presence of this field.

Each data model possesses a type with the various supported attributes which a lightning web application can utilise to structure metadata. Data model types such as _**AudioObject, ImageObject, VideoObject**_ and many more are present to structure metadata_**.**_

Use our data models of the suitable type to structure metadata in **JSON** format**:**

{% content-ref url="../data-models/data-model-overview.md" %}
[data-model-overview.md](../data-models/data-model-overview.md)
{% endcontent-ref %}

Eg.

```
let metadata: {};
metadata = {
 "type": "AudioObject",
 "name": "title",
 "creator": "artist",
 "image": "image" 
 }
```

To learn more about how to structure metadata for Bitcoin transactions :

{% content-ref url="../data-models/structure-metadata-using-data-models.md" %}
[structure-metadata-using-data-models.md](../data-models/structure-metadata-using-data-models.md)
{% endcontent-ref %}

### Pass Metadata

Using `SendPayment` method, the lightning web application passes an invoice along with additional metadata. WebLN provider delivers such data to the wallets.\
\
Before passing metadata to the wallet using the `SendPayment` method, metadata shall present in a structured form using the data models provided in a comprehensive guide.

```
webln.sendPayment(invoice, metadata);
```

