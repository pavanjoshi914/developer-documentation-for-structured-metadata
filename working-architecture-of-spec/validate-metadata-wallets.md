# 🚦 Validate Metadata

Metadata is user-generated, such type of metadata should be cross-checked for its correctness and before performing any further action wallets have to do validation of metadata.

### _What is JSON Schema?_ 🧐

JSON Schema is **a JSON media type for defining the structure of JSON data**. JSON Schema provides a contract for what JSON data is required for a given application and how to interact with it.

Schemas can be created to validate received data against a predefined data model. To do this many validator plugins are available too

* Generate Schema
* Compile Schema
* Validate received data for that particular schema

[_**Zod**_](https://www.npmjs.com/package/zod) plugin can be used to validate JSON schemas as well as Object schemas. The best thing about this plugin is that it has zero external dependencies involved.

**Validator function which validates metadata against schemas generated using Zod plugin**

* Schema Created using Zod plugin

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

 export function MetadataValidator(metadata: { [key: string]: string }) {
   let hasValidType = false;
   let hasValidImage = true;
   for (const key in metadata) {
     if (key == "type") {
       if (metadata[key] == "AudioObject") {
         const parsed = audioObjectSchema.safeParse(metadata);
         if (parsed.success) {
           hasValidType = true;
         }
       }
     }
     if (key == "image") {
       hasValidImage = isBase64(metadata[key]);
     }
   }

 return hasValidType && hasValidImage;
 }
```

* To Validate Metadata Just call the function by passing metadata.

```
const isMetadataValid = MetadataValidator(metadata);
```
