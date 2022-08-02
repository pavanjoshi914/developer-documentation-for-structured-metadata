# 📨 Data Model Overview

This specification uses data models derived from standards such as [schema.org](https://schema.org) in order to provide structure and define some standard properties, which we use to describe metadata.

### Schema.org

[**Schema.org**](http://schema.org) is a collaborative, community activity with a mission to create, maintain, and promote schemas for structured data on the Internet, on web pages, in email messages, and beyond. It is founded by Google, Microsoft, Yahoo and Yandex.&#x20;

Schema.org vocabularies are developed by an open [community](https://www.w3.org/community/schemaorg) process, using the [public-schemaorg@w3.org](http://lists.w3.org/Archives/Public/public-schemaorg) mailing list and through [GitHub](http://github.com/schemaorg/schemaorg). Often properties are added for some specific use case, and their potential relationship to other areas of schema.org only becomes clear later. This gives rise to changes in textual definition and property-to-type associations that gradually make schema.org more coherent, without introducing radical changes in meaning. Consumers of schema.org data can generally rely on schema.org term meanings not changing dramatically; however, term definitions often evolve gradually over time, to accommodate new usage scenarios or to improve usability. When schema.org properties are occasionally deprecated, they stay in the context so that they can still be used and are simply referenced to their replacement property.

### Using Data Models to Structure Metadata

[**Schema.org**](http://schema.org) allows the structuring of data using **JSON-LD** format. **JSON-LD** is a **JSON** having an additional _`@context`_ field. We use the same schema to structure metadata without the _`@context`_ field.

Each data model has its own type along with the various supported attributes which can be used to structure metadata such as  _**AudioObject, ImageObject, VideoObject etc**_

Use our data models of the suitable type to structure metadata in form of **JSON :**

{% content-ref url="type-reference/" %}
[type-reference](type-reference/)
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

{% content-ref url="structure-metadata-using-data-models.md" %}
[structure-metadata-using-data-models.md](structure-metadata-using-data-models.md)
{% endcontent-ref %}





