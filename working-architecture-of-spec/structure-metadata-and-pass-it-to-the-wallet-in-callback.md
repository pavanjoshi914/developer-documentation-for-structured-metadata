# 🧱 󠁻󠁻Structure and Pass Metadata

### Structure Metadata

This specification uses data models derived from standards such as [schema.org](https://schema.org) in order to provide structure and define some standard properties, which we use to describe metadata.

[**Schema.org**](http://schema.org) allows the structuring of data using **JSON-LD** format. **JSON-LD** is a **JSON** having an additional _`@context`_ field. We use the same schema to structure metadata without the _`@context`_ field.

Each data model has its own type along with the various supported attributes which can be used to structure metadata such as  _**AudioObject, ImageObject, VideoObject etc**_

Use our data models of the suitable type to structure metadata in form of **JSON :**

{% content-ref url="../data-models/data-model-overview.md" %}
[data-model-overview.md](../data-models/data-model-overview.md)
{% endcontent-ref %}

eg.

```
var Metadata = {};
Metadata = {
 "type": "AudioObject",
 "name": "title",
 "creator": "artist",
 "image": "image" 
 }
 export var Metadata;
```

To learn more about how to structure metadata for Bitcoin Transactions -

{% content-ref url="../data-models/structure-metadata-using-data-models.md" %}
[structure-metadata-using-data-models.md](../data-models/structure-metadata-using-data-models.md)
{% endcontent-ref %}

### Pass Metadata

The Client passes the Invoice along with metadata via `SendPayment` method, which is delivered to the wallet through the Provider\
\
Before passing metadata, metadata needs to be structured following the data models provided in a comprehensive guide

```
webln.sendPayment(Invoice, Metadata);
```

