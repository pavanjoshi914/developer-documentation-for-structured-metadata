---
description: Overview of the data models which can be used to structure metadata
---

# 📨 Data Model Overview

This specification uses data models derived from standards such as [schema.org](https://schema.org) to deliver structure to metadata and define some standard properties, which we use to describe metadata.

### Schema.org

[**Schema.org**](http://schema.org) is a collaborative, community activity on a mission to create, maintain, and promote schemas for structured data on the Internet and web pages, in email messages, and beyond. [**Schema.org**](http://schema.org) had founded by the companies such as Google, Microsoft, Yahoo and Yandex.

Schema.org vocabularies are developed by an open [community](https://www.w3.org/community/schemaorg) process, using the [public-schemaorg@w3.org](http://lists.w3.org/Archives/Public/public-schemaorg) mailing list and through [GitHub](http://github.com/schemaorg/schemaorg). Often properties are added for some specific use case, and their potential relationship to other areas of schema.org only becomes apparent later. The acquisition of new properties gives rise to changes in textual definition and property-to-type associations that gradually make schema.org coherent without introducing radical changes in meaning. Consumers of schema.org data can generally rely on schema.org term meanings not changing dramatically; however, term definitions often evolve with time to accommodate new usage scenarios and improve usability. When schema.org properties are occasionally deprecated, they stay in the context that can still be used and referenced to their replacement property.

### Using Data Models to Structure Metadata

[**Schema.org**](http://schema.org) allows the structuring of data using **JSON-LD** format. **JSON-LD** is a **JSON** having an additional _`@context`_ field. We use the same schema to structure metadata without the presence of this field.

Each data model possesses a type with the various supported attributes which a lightning web application can utilise to structure metadata. Data model types such as _**AudioObject, ImageObject, VideoObject**_ and many more are present to structure metadata_**.**_

Use our data models of the suitable type to structure metadata in **JSON** format**:**

{% content-ref url="type-reference/" %}
[type-reference](type-reference/)
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

To learn more about how to structure metadata for Bitcoin transactions:

{% content-ref url="structure-metadata-using-data-models.md" %}
[structure-metadata-using-data-models.md](structure-metadata-using-data-models.md)
{% endcontent-ref %}
