---
title: दस्तावेज़ निर्माता के बिना TOA फ़ील्ड सम्मिलित करें
linktitle: दस्तावेज़ निर्माता के बिना TOA फ़ील्ड सम्मिलित करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ बिल्डर के बिना TOA फ़ील्ड सम्मिलित करने के लिए चरण दर चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/working-with-fields/insert-toafield-without-document-builder/
---

नीचे C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है, जो .NET के लिए Aspose.Words की "TOA फ़ील्ड इंसर्शन" सुविधा का उपयोग करती है। वांछित परिणाम प्राप्त करने के लिए प्रत्येक चरण का सावधानीपूर्वक पालन करें।

## चरण 1: दस्तावेज़ निर्देशिका सेटअप

दिए गए कोड में, आपको अपने दस्तावेज़ों की निर्देशिका निर्दिष्ट करनी होगी। अपने दस्तावेज़ निर्देशिका के लिए उचित पथ के साथ "आपकी दस्तावेज़ निर्देशिका" मान को बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ और पैराग्राफ़ बनाना

हम एक नया दस्तावेज़ बनाकर और एक पैराग्राफ आरंभ करके शुरुआत करते हैं।

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## चरण 3: टीए फ़ील्ड सम्मिलित करना

पैराग्राफ में टीए फ़ील्ड सम्मिलित करने के लिए हम फ़ील्डटीए क्लास का उपयोग करते हैं।

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## चरण 4: दस्तावेज़ के मुख्य भाग में पैराग्राफ जोड़ना

हम दस्तावेज़ के मुख्य भाग में टीए फ़ील्ड वाला पैराग्राफ जोड़ते हैं।

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## चरण 5: TOA फ़ील्ड के लिए पैराग्राफ़ बनाना

हम TOA फ़ील्ड के लिए एक नया पैराग्राफ बनाते हैं।

```csharp
para = new Paragraph(doc);
```

## चरण 6: TOA फ़ील्ड सम्मिलित करना

पैराग्राफ में TOA फ़ील्ड सम्मिलित करने के लिए हम फ़ील्डटोआ क्लास का उपयोग करते हैं।

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## चरण 7: दस्तावेज़ के मुख्य भाग में पैराग्राफ जोड़ना

हम दस्तावेज़ के मुख्य भाग में TOA फ़ील्ड वाला पैराग्राफ़ जोड़ते हैं।

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## चरण 8: टीओए फ़ील्ड को अपडेट करें

 अंत में, हम कॉल करते हैं`Update()` TOA फ़ील्ड को अद्यतन करने की विधि।

```csharp
fieldToa.Update();
```

### .NET के लिए Aspose.Words के साथ दस्तावेज़ बिल्डर के बिना TOA फ़ील्ड प्रविष्टि के लिए स्रोत कोड उदाहरण

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// हम टीए और टीओए फ़ील्ड इस तरह सम्मिलित करना चाहते हैं:
// { TA \c 1 \l "मान 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में सम्मिलित TOA फ़ील्ड की उपस्थिति को कैसे अनुकूलित करें?

उ: आप के गुणों का उपयोग करके सम्मिलित TOA फ़ील्ड की उपस्थिति को अनुकूलित कर सकते हैं`FieldTOA` स्वरूपण विकल्प निर्दिष्ट करने के लिए ऑब्जेक्ट।

#### प्रश्न: क्या मैं .NET के लिए Aspose.Words का उपयोग करके एक ही Word दस्तावेज़ में एकाधिक TOA फ़ील्ड जोड़ सकता हूँ?

उ: हाँ, आप .NET के लिए Aspose.Words का उपयोग करके एक ही Word दस्तावेज़ में एकाधिक TOA फ़ील्ड जोड़ सकते हैं। बस प्रत्येक फ़ील्ड के लिए सम्मिलित चरण दोहराएँ।

#### प्रश्न: मैं कैसे जांच सकता हूं कि .NET के लिए Aspose.Words के साथ किसी Word दस्तावेज़ में TOA फ़ील्ड सफलतापूर्वक डाला गया था या नहीं?

उ: यह जांचने के लिए कि क्या TOA फ़ील्ड सफलतापूर्वक डाला गया था, आप दस्तावेज़ सामग्री ब्राउज़ कर सकते हैं और TOA फ़ील्ड उदाहरण खोज सकते हैं।

#### प्रश्न: क्या DocumentBuilder का उपयोग किए बिना TOA फ़ील्ड सम्मिलित करने से .NET के लिए Aspose.Words के साथ Word दस्तावेज़ स्वरूपण प्रभावित होता है?

उत्तर: DocumentBuilder का उपयोग किए बिना TOA फ़ील्ड सम्मिलित करना सीधे Word दस्तावेज़ के स्वरूपण को प्रभावित नहीं करता है। हालाँकि, TOA फ़ील्ड फ़ॉर्मेटिंग विकल्प दस्तावेज़ के समग्र फ़ॉर्मेटिंग को प्रभावित कर सकते हैं।