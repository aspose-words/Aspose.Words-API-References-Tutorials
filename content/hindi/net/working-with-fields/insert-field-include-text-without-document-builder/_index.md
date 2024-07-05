---
title: दस्तावेज़ बिल्डर के बिना टेक्स्ट शामिल करने के लिए फ़ील्ड डालें
linktitle: डॉक्यूमेंट बिल्डर के बिना FieldIncludeText डालें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ अपने Word दस्तावेज़ों में FieldIncludeText फ़ील्ड सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-fields/insert-field-include-text-without-document-builder/
---

नीचे C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है, जो .NET के लिए Aspose.Words की "Insert a FieldIncludeText field" कार्यक्षमता का उपयोग करती है। वांछित परिणाम प्राप्त करने के लिए प्रत्येक चरण का सावधानीपूर्वक पालन करना सुनिश्चित करें।

## चरण 1: दस्तावेज़ निर्देशिका सेटअप

दिए गए कोड में, आपको अपने दस्तावेज़ों की निर्देशिका निर्दिष्ट करनी होगी। "आपकी दस्तावेज़ निर्देशिका" मान को अपने दस्तावेज़ निर्देशिका के लिए उपयुक्त पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ और पैराग्राफ़ बनाना

हम एक नया दस्तावेज़ बनाकर और एक पैराग्राफ़ आरंभ करके शुरुआत करते हैं।

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## चरण 3: FieldIncludeText फ़ील्ड सम्मिलित करना

 हम उपयोग करते हैं`AppendField()` पैराग्राफ में FieldIncludeText फ़ील्ड सम्मिलित करने की विधि।

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

फिर हम बुकमार्क का नाम और स्रोत फ़ाइल का नाम निर्दिष्ट करके FieldIncludeText फ़ील्ड के गुणों को कॉन्फ़िगर करते हैं।

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

इसके बाद, हम पैराग्राफ को दस्तावेज़ के मुख्य भाग में जोड़ते हैं।

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 अंत में, हम कॉल करते हैं`Update()` क्षेत्र को अद्यतन करने की विधि.

```csharp
fieldIncludeText.Update();
```

### .NET के लिए Aspose.Words के साथ FieldIncludeText फ़ील्ड सम्मिलित करने के लिए स्रोत कोड का उदाहरण

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ और पैराग्राफ़ बनाएँ.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// FieldIncludeText फ़ील्ड सम्मिलित करें.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

इस उदाहरण में, हमने एक नया दस्तावेज़ बनाया, एक पैराग्राफ़ आरंभ किया, बुकमार्क नाम और स्रोत फ़ाइल नाम निर्दिष्ट करते हुए FieldIncludeTexten डाला, और दस्तावेज़ को निर्दिष्ट फ़ाइल नाम के साथ सहेजा।

यह .NET के लिए Aspose.Words के साथ "Insert a FieldIncludeText" सुविधा का उपयोग करने पर हमारी मार्गदर्शिका का समापन करता है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं .NET के लिए Aspose.Words में पाठ समावेशन फ़ील्ड के लिए स्रोत फ़ाइल कैसे निर्दिष्ट कर सकता हूं?

 उत्तर: Aspose.Words for .NET में पाठ समावेशन फ़ील्ड के लिए स्रोत फ़ाइल निर्दिष्ट करने के लिए, आप इसका उपयोग कर सकते हैं`FieldIncludeText.SourceFullName`स्रोत फ़ाइल का पूरा पथ सेट करने के लिए प्रॉपर्टी का उपयोग करें। सुनिश्चित करें कि स्रोत फ़ाइल सुलभ है और उसमें वह सामग्री है जिसे आप टेक्स्ट समावेशन फ़ील्ड में शामिल करना चाहते हैं।

#### प्रश्न: क्या मैं Aspose.Words for .NET के साथ टेक्स्ट समावेशन फ़ील्ड में मैक्रो से टेक्स्ट शामिल कर सकता हूं?

 उत्तर: हाँ, आप Aspose.Words for .NET के साथ टेक्स्ट समावेशन फ़ील्ड में मैक्रो से टेक्स्ट शामिल कर सकते हैं। आप इसका उपयोग कर सकते हैं`FieldIncludeText.IncludeText` मैक्रो का नाम निर्दिष्ट करने के लिए गुण जिसकी सामग्री फ़ील्ड में शामिल की जानी चाहिए।

#### प्रश्न: क्या दस्तावेज़ बिल्डर के बिना पाठ सम्मिलित फ़ील्ड सम्मिलित करने से Aspose.Words for .NET के साथ Word दस्तावेज़ संरचना प्रभावित होती है?

उत्तर: डॉक्यूमेंट बिल्डर के बिना टेक्स्ट इनक्लूड फ़ील्ड डालने से सीधे वर्ड डॉक्यूमेंट की संरचना प्रभावित नहीं होती है। हालाँकि, यह डॉक्यूमेंट कंटेंट में एक नया फ़ील्ड एलिमेंट जोड़ता है। आप अपनी ज़रूरतों के हिसाब से मौजूदा एलिमेंट को जोड़कर, हटाकर या संशोधित करके डॉक्यूमेंट स्ट्रक्चर में बदलाव कर सकते हैं।

#### प्रश्न: क्या मैं Aspose.Words for .NET के साथ Word दस्तावेज़ में पाठ समावेशन फ़ील्ड की उपस्थिति को अनुकूलित कर सकता हूं?

उत्तर: टेक्स्ट समावेशन फ़ील्ड सीधे Word दस्तावेज़ में अपनी उपस्थिति को अनुकूलित नहीं करता है। हालाँकि, आप पैराग्राफ़ गुण, फ़ॉन्ट गुण और Aspose.Words for .NET में उपलब्ध अन्य फ़ॉर्मेटिंग ऑब्जेक्ट का उपयोग करके शामिल किए गए टेक्स्ट को फ़ॉर्मेट कर सकते हैं।