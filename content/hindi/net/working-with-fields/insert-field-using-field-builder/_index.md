---
title: फ़ील्ड बिल्डर का उपयोग करके फ़ील्ड सम्मिलित करें
linktitle: फ़ील्ड बिल्डर का उपयोग करके फ़ील्ड सम्मिलित करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ अपने Word दस्तावेज़ों में कस्टम फ़ील्ड सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-fields/insert-field-using-field-builder/
---

नीचे C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है, जो .NET के लिए Aspose.Words की "फ़ील्डबिल्डर का उपयोग करके फ़ील्ड डालें" सुविधा का उपयोग करता है। वांछित परिणाम प्राप्त करने के लिए प्रत्येक चरण का सावधानीपूर्वक पालन करना सुनिश्चित करें।

## चरण 1: दस्तावेज़ निर्देशिका सेटअप

दिए गए कोड में, आपको अपने दस्तावेज़ों की निर्देशिका निर्दिष्ट करनी होगी। "आपकी दस्तावेज़ निर्देशिका" मान को अपने दस्तावेज़ निर्देशिका के लिए उपयुक्त पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ बनाना

हम एक नया दस्तावेज़ बनाकर शुरुआत करते हैं।

```csharp
Document doc = new Document();
```

## चरण 3: FieldBuilder का उपयोग करके IF फ़ील्ड बनाना

हम दो नेस्टेड MERGEFIELD फ़ील्ड के साथ IF फ़ील्ड बनाने के लिए FieldBuilder क्लास का उपयोग करते हैं। इस उदाहरण में, IF फ़ील्ड किसी शर्त के आधार पर पहला और अंतिम नाम प्रदर्शित करता है।

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## चरण 4: दस्तावेज़ में IF फ़ील्ड सम्मिलित करना

 हम उपयोग करते हैं`BuildAndInsert()` दस्तावेज़ में किसी विशिष्ट स्थान पर IF फ़ील्ड बनाने और सम्मिलित करने की विधि।

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### .NET के लिए Aspose.Words के साथ FieldBuilder का उपयोग करके फ़ील्ड सम्मिलित करने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ निर्माण.
Document doc = new Document();

// फील्डबिल्डर का उपयोग करके IF फील्ड का निर्माण।
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// दस्तावेज़ में IF फ़ील्ड डालें.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

इस उदाहरण में, हमने एक नया दस्तावेज़ बनाया, नेस्टेड MERGEFIELD फ़ील्ड के साथ एक IF फ़ील्ड बनाया, और फिर उस फ़ील्ड को दस्तावेज़ में निर्दिष्ट स्थान पर डाला। फिर दस्तावेज़ को एक विशिष्ट फ़ाइल नाम से सहेजा जाता है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: Aspose.Words में फ़ील्ड कंस्ट्रक्टर क्या है?

उत्तर: Aspose.Words में फ़ील्ड बिल्डर, Word दस्तावेज़ में फ़ील्ड बनाने और उनमें हेरफेर करने के लिए एक शक्तिशाली उपकरण है। यह फ़ील्ड कोड डालने और फ़ॉर्मेटिंग विकल्पों को प्रबंधित करने सहित फ़ील्ड बनाने और उन्हें अनुकूलित करने के लिए उन्नत सुविधाएँ प्रदान करता है।

#### प्रश्न: फ़ील्ड बिल्डर का उपयोग करके किस प्रकार के फ़ील्ड सम्मिलित किए जा सकते हैं?

उत्तर: Aspose.Words में फ़ील्ड बिल्डर आपको Word दस्तावेज़ में विभिन्न प्रकार के फ़ील्ड सम्मिलित करने की अनुमति देता है। यहाँ सामान्य रूप से उपयोग किए जाने वाले फ़ील्ड प्रकारों के कुछ उदाहरण दिए गए हैं:

- MERGEFIELD: बाहरी स्रोतों से डेटा मर्ज करने के लिए उपयोग किया जाता है।
- DATE: वर्तमान दिनांक प्रदर्शित करता है.
- पृष्ठ: वर्तमान पृष्ठ संख्या प्रदर्शित करता है.
- आईएफ: किसी शर्त के अनुसार सामग्री के प्रदर्शन को निर्धारित करने की अनुमति देता है।
- TOC: दस्तावेज़ शीर्षक शैलियों के आधार पर स्वचालित रूप से सामग्री की तालिका तैयार करता है।

#### प्रश्न: फ़ील्ड बिल्डर के साथ सम्मिलित फ़ील्ड को कैसे अनुकूलित करें?

उत्तर: फ़ील्ड बिल्डर सम्मिलित फ़ील्ड के लिए अनुकूलन विकल्प प्रदान करता है। आप फ़ील्ड फ़ॉर्मेटिंग, तर्क, स्विच और डिफ़ॉल्ट मान जैसे विकल्प सेट करने के लिए फ़ील्ड कंस्ट्रक्टर विधियों और गुणों का उपयोग कर सकते हैं। उदाहरण के लिए, आप दिनांक प्रारूप, संख्या प्रारूप, हज़ार विभाजक आदि सेट कर सकते हैं।
  