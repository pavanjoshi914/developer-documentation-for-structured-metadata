---
description: Data Model Type - ImageObject
---

# 🖼 ImageObject

## ImageObject

Type ImageObject is a derived type from [https://schema.org/ImageObject](https://schema.org/ImageObject), which means that for this particular data model type, any of the properties also mentioned at schema.org, may also be used. However, to structure metadata supported properties mentioned shall be used only.

## **Properties**

### **Required properties**

| Property  | Expected Type                     | Description                                                |
| --------- | --------------------------------- | ---------------------------------------------------------- |
| **@type** | [`Text`](https://schema.org/Text) | Must always be present and set to `"@type": "ImageObject"` |

#### **Optional properties**

| Property       | Expected Type                                                                                                                                                                          | Description                                                                                                                                                                                                                       |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **contentUrl** | ``[`URL`](https://schema.org/URL)``                                                                                                                                                    | <p>Actual bytes of the media object, for example the image file or video file.</p><p><br><strong>Example</strong></p><p><code>"contentUrl": "https://example.com/media/stayin/getfit.png"</code></p><p>The URL for the image.</p> |
| **url**        | ``[`URL`](https://schema.org/URL)``                                                                                                                                                    | <p>Url that provides additional information about the ImageObject</p><p><strong>Example</strong></p><p><code>"url": "https://soundcloud.com/joshy-lift12/alan-walker-vs-coldplay-hymm-description.png"</code></p>                 |
| **creator**    | <p><a href="https://schema.org/Organization"><code>Organization</code></a><code>or</code><br><code></code><a href="https://schema.org/Person"><code>Person</code></a><code></code></p> | The creator/author of this CreativeWork. This is the same as the Author property for CreativeWork.                                                                                                                                |
| **caption**    | ``[`Text`](https://schema.org/Text)``                                                                                                                                                  | The caption for this object. For downloadable machine formats.                                                                                                                                                                    |
| **about**      | ``[`Text`](https://schema.org/Text)``                                                                                                                                                  | The subject matter of the content.                                                                                                                                                                                                |
| **height**     | [`Integer`](https://schema.org/Integer)                                                                                                                                                | <p>The height of the media in pixels.</p><p><br><strong>Example</strong></p><p><code>"height": 300</code></p>                                                                                                                     |
| **thumbnail**  | [`URL`](https://schema.org/URL)``                                                                                                                                                      | The Base64 encoded thumbnail image for the audio.                                                                                                                                                                                 |
| **width**      | [`Integer`](https://schema.org/Integer)                                                                                                                                                | <p>The width of the media in pixels.</p><p><br><strong>Example</strong></p><p><code>"width": 400</code></p>                                                                                                                       |
