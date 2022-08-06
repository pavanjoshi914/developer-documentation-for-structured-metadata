---
description: Step Three - Validate Metadata
---

# 🚦 Validate Metadata

Metadata is user-generated. Wallets have to confirm their correctness. Before performing any further action on metadata, wallets have to validate metadata.

### _What is JSON Schema?_ 🧐

JSON Schema is **a JSON media type for defining the structure of the JSON data**. JSON Schema provides a contract for what JSON data is required and how to interact with it.

JSON schemas can be created and used to validate received data against a predefined data model. \
\
There are many validator NPM packages available to validate metadata and provide the functionality to:

* Generate Schema
* Compile Schema
* Validate received data for that particular schema

[_**Zod**_](https://www.npmjs.com/package/zod) _****_ NPM package _****_ is one of the validators used to validate JSON and object schema. The best thing about this package is that it has zero external dependencies involved.

**Validator function to validate metadata against predefined schema generated using the Zod NPM package**

* Schema Created using Zod NPM package

```
 import { z } from "zod";

 export const audioObjectSchema = z.object({
   type: z.string(),
   name: z.string().optional(),
   creator: z.string().optional(),
   image: z.string().optional(),
 });
```

* Custom and Reusable Validator function to validate metadata

```
import { audioObjectSchema } from "./audioObjectSchema";

export function isBase64(str: string) {
  if (str === "" || str.trim() === "") {
    return false;
  }
  try {
    return btoa(atob(str)) == str;
  } catch (err) {
    return false;
  }
}

export function MetadataValidator(metadata: object) {
  let hasValidType: boolean = false;
  let hasValidImage: boolean = true;
  for (const [key, value] of Object.entries(metadata)) {
    if (key == "type") {
      if (value == "AudioObject") {
        const parsed = audioObjectSchema.safeParse(metadata);
        if (parsed.success) {
          hasValidType = true;
        }
      }
    }
    if (key == "image") {
      hasValidImage = isBase64(value);
    }
  }

  return hasValidType && hasValidImage;
}
```

* To Validate metadata, call the function by passing metadata.

```
const isMetadataValid = MetadataValidator(metadata);
```
