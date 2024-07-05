---
title: डॉक्यूमेंट बिल्डर के बिना ASKField डालें
linktitle: डॉक्यूमेंट बिल्डर के बिना ASKField डालें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ अपने Word दस्तावेज़ों में ASK फ़ील्ड सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-fields/insert-askfield-with-out-document-builder/
---

नीचे C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है, जो .NET के लिए Aspose.Words की "DocumentBuilder के बिना ASK फ़ील्ड डालें" सुविधा का उपयोग करता है। वांछित परिणाम प्राप्त करने के लिए प्रत्येक चरण का सावधानीपूर्वक पालन करना सुनिश्चित करें।

## चरण 1: दस्तावेज़ निर्देशिका सेटअप

दिए गए कोड में, आपको अपने दस्तावेज़ों की निर्देशिका निर्दिष्ट करनी होगी। "आपकी दस्तावेज़ निर्देशिका" मान को अपने दस्तावेज़ निर्देशिका के लिए उपयुक्त पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ और पैराग्राफ़ बनाना

हम एक नया दस्तावेज़ बनाकर और पहला पैराग्राफ लाकर शुरुआत करते हैं।

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## चरण 3: ASK फ़ील्ड सम्मिलित करना

 हम उपयोग करते हैं`AppendField()` पैराग्राफ में ASK फ़ील्ड सम्मिलित करने की विधि।

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

फिर हम वांछित मान निर्दिष्ट करके ASK फ़ील्ड के विभिन्न गुणों को कॉन्फ़िगर करते हैं।

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 अंत में, हम कॉल करते हैं`Update()` क्षेत्र को अद्यतन करने की विधि.

```csharp
field. Update();
```

### .NET के लिए Aspose.Words के साथ DocumentBuilder के बिना ASK फ़ील्ड सम्मिलित करने के लिए स्रोत कोड का उदाहरण

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ निर्माण.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// ASK फ़ील्ड डालें.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

इस उदाहरण में, हमने एक नया दस्तावेज़ बनाया, DocumentBuilder का उपयोग किए बिना ASK फ़ील्ड डाला, फ़ील्ड के विभिन्न गुणों को कॉन्फ़िगर किया, और दस्तावेज़ को निर्दिष्ट फ़ाइल नाम के साथ सहेजा।

यह .NET के लिए Aspose.Words के साथ "Insert ASK Field Without DocumentBuilder" सुविधा का उपयोग करने पर हमारी मार्गदर्शिका का समापन करता है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: Aspose.Words में ASK फ़ील्ड क्या है?

उत्तर: Aspose.Words में ASK फ़ील्ड का उपयोग दस्तावेज़ खोलते समय उपयोगकर्ता से प्रश्न पूछने के लिए किया जाता है। इसका उपयोग अक्सर विशिष्ट जानकारी या फ़ीडबैक का अनुरोध करने के लिए किया जाता है जो उपयोगकर्ता से उपयोगकर्ता के लिए अलग-अलग हो सकता है।

#### प्रश्न: Aspose.Words में डॉक्यूमेंट बिल्डर का उपयोग किए बिना Word दस्तावेज़ में ASK फ़ील्ड कैसे सम्मिलित करें?

उत्तर: Aspose.Words में डॉक्यूमेंट बिल्डर का उपयोग किए बिना Word दस्तावेज़ में ASK फ़ील्ड सम्मिलित करने के लिए, आप इन चरणों का पालन कर सकते हैं:

1. Aspose.Words.Fields नामस्थान से दस्तावेज़ और फ़ील्ड वर्ग आयात करें।
2. अपने मौजूदा दस्तावेज़ को लोड करके दस्तावेज़ का एक उदाहरण बनाएँ.
3. प्रश्न का नाम निर्दिष्ट करके ASK फ़ील्ड सम्मिलित करने के लिए InsertField विधि का उपयोग करें।
4. दस्तावेज़ सहेजें.

#### प्रश्न: मैं Word दस्तावेज़ में ASK फ़ील्ड के लिए उपयोगकर्ता प्रतिक्रिया कैसे प्राप्त करूं?

उत्तर: Word दस्तावेज़ में ASK फ़ील्ड के लिए उपयोगकर्ता की प्रतिक्रिया प्राप्त करने के लिए, आप दस्तावेज़ वर्ग में उपलब्ध GetFieldNames विधि का उपयोग कर सकते हैं। यह विधि दस्तावेज़ में मौजूद फ़ील्ड के नामों की एक सूची लौटाती है। फिर आप जाँच सकते हैं कि ASK फ़ील्ड नाम सूची में मौजूद है या नहीं और संबंधित प्रतिक्रिया प्राप्त कर सकते हैं।

#### प्रश्न: क्या ASK फ़ील्ड का उपयोग उपयोगकर्ता से अधिक जानकारी मांगने के लिए किया जा सकता है?

उत्तर: हां, ASK फ़ील्ड का उपयोग उपयोगकर्ता से कई जानकारी मांगने के लिए किया जा सकता है। आप अपने दस्तावेज़ में कई ASK फ़ील्ड डाल सकते हैं, जिनमें से प्रत्येक में एक अलग प्रश्न होगा। जब दस्तावेज़ खोला जाता है, तो उपयोगकर्ता को संबंधित उत्तरों के लिए संकेत दिया जाएगा।