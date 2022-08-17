---
description: Data Model Type - AudioObject
---

# 🎙 AudioObject

## AudioObject

&#x20;Type AudioObject is a derived type from [https://schema.org/AudioObject](https://schema.org/AudioObject), which means that for this particular data model type, any of the properties also mentioned at schema.org, may also be used. However, to structure metadata supported properties mentioned shall be used only.

## **Properties**

### **Required properties**

| Property | Expected Type                     | Description                                                                                                                                                   |
| -------- | --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **type** | [`Text`](https://schema.org/Text) | <p>Must always be present and set to: <code>AudioObject</code></p><p><br><strong>Example</strong><br><code>"type": "AudioObject"</code></p>                   |
| **url**  | [`URL`](https://schema.org/URL)   | <p>The URL for the audio.</p><p><br><strong>Example</strong></p><p><code>"url": "https://soundcloud.com/joshy-lift12/alan-walker-vs-coldplay-hymm"</code></p> |

#### **Optional properties**

| Property       | Expected Type                           | Description                                                                                                                                                                                                                                                                                          |
| -------------- | --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **contentUrl** | [`URL`](https://schema.org/URL)         | <p>Actual bytes of the media object, for example the image file or video file.</p><p><br><strong>Example</strong></p><p><code>"contentUrl": "https://example.com/media/stayin/getfit"</code></p>                                                                                                     |
| **embedUrl**   | [`URL`](https://schema.org/URL)         | <p>A URL pointing to a player for a specific video. In general, this is the information in the src element of an embed tag and should not be the same as the content of the loc tag.</p><p><br><strong>Example</strong></p><p><code>"embedUrl": "https://example.com/media/stayin/getfit"</code></p> |
| **height**     | [`Integer`](https://schema.org/Integer) | <p>The height of the media in pixels.</p><p><br><strong>Example</strong></p><p><code>"height": 300</code></p>                                                                                                                                                                                        |
| **thumbnail**  | ``[`Image`](https://schema.org/image)`` | The Base64 encoded thumbnail image for the audio.                                                                                                                                                                                                                                                    |
| **width**      | [`Integer`](https://schema.org/Integer) | <p>The width of the media in pixels.</p><p><br><strong>Example</strong></p><p><code>"width": 400</code></p>                                                                                                                                                                                          |
