---
title: वर्ड दस्तावेज़ में अप्रतिबंधित संपादन योग्य क्षेत्र
linktitle: वर्ड दस्तावेज़ में अप्रतिबंधित संपादन योग्य क्षेत्र
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में अप्रतिबंधित संपादन योग्य क्षेत्र बनाने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/document-protection/unrestricted-editable-regions/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words की अप्रतिबंधित संपादन योग्य क्षेत्र सुविधा का उपयोग करने के चरणों के माध्यम से मार्गदर्शन करेंगे। यह सुविधा आपको Word दस्तावेज़ में ऐसे क्षेत्र निर्धारित करने देती है जहाँ सामग्री को बिना किसी प्रतिबंध के संपादित किया जा सकता है, भले ही दस्तावेज़ का बाकी हिस्सा केवल पढ़ने के लिए हो। नीचे दिए गए चरणों का पालन करें:

## चरण 1: दस्तावेज़ लोड करना और सुरक्षा सेट करना

मौजूदा दस्तावेज़ लोड करके प्रारंभ करें:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

केवल पढ़ने के लिए सुरक्षा प्रकार और पासवर्ड सेट करके दस्तावेज़ को सुरक्षित करें

## चरण 2: संपादन योग्य क्षेत्र बनाना

EditableRangeStart और EditableRangeEnd ऑब्जेक्ट का उपयोग करके संपादन योग्य क्षेत्र बनाकर आरंभ करें:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// हमारे द्वारा अभी बनाए गए EditableRangeStart के लिए एक EditableRange ऑब्जेक्ट बनाया गया है।
EditableRange editableRange = edRangeStart.EditableRange;

// संपादन योग्य सीमा के अंदर कुछ रखें.
builder.Writeln("Paragraph inside first editable range");

// एक संपादन योग्य श्रेणी अच्छी तरह से बनाई गई है यदि उसका प्रारंभ और अंत है।
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## चरण 3: संपादन योग्य क्षेत्रों के बाहर सामग्री जोड़ें

आप संपादन योग्य क्षेत्रों के बाहर भी सामग्री जोड़ सकते हैं, जो केवल पढ़ने के लिए ही रहेगी:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## चरण 4: दस्तावेज़ सहेजें

अंत में, संशोधित दस्तावेज़ को सहेजें:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

दस्तावेज़ को संपादन योग्य क्षेत्रों के साथ सहेजने के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके अप्रतिबंधित संपादन योग्य क्षेत्रों के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके अप्रतिबंधित संपादन योग्य क्षेत्रों के लिए पूर्ण स्रोत कोड यहां दिया गया है:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// एक दस्तावेज़ अपलोड करें और उसे केवल पढ़ने योग्य बनाएं।
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

// संपादन योग्य श्रेणी प्रारंभ करें.
EditableRangeStart edRangeStart = builder.StartEditableRange();
// हमारे द्वारा अभी बनाए गए EditableRangeStart के लिए एक EditableRange ऑब्जेक्ट बनाया गया है।
EditableRange editableRange = edRangeStart.EditableRange;

// संपादन योग्य सीमा के अंदर कुछ रखें.
builder.Writeln("Paragraph inside first editable range");

// एक संपादन योग्य श्रेणी अच्छी तरह से बनाई गई है यदि उसका प्रारंभ और अंत है।
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
इन चरणों का पालन करके, आप आसानी से Aspose.Words for .NET के साथ अपने Word दस्तावेज़ में अप्रतिबंधित संपादन योग्य क्षेत्र बना सकते हैं।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में अप्रतिबंधित संपादन योग्य क्षेत्र कैसे बनाएं। दिए गए चरणों का पालन करके, आप दस्तावेज़ के भीतर विशिष्ट क्षेत्रों को परिभाषित कर सकते हैं जहाँ उपयोगकर्ता शेष दस्तावेज़ को केवल पढ़ने के लिए रखते हुए सामग्री को स्वतंत्र रूप से संपादित कर सकते हैं। Aspose.Words for .NET दस्तावेज़ सुरक्षा और अनुकूलन के लिए शक्तिशाली सुविधाएँ प्रदान करता है, जो आपको अपने Word दस्तावेज़ों की संपादन क्षमताओं पर नियंत्रण प्रदान करता है।

### वर्ड दस्तावेज़ में अप्रतिबंधित संपादन योग्य क्षेत्रों के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: Aspose.Words for .NET में अप्रतिबंधित संपादन योग्य क्षेत्र क्या हैं?

उत्तर: Aspose.Words for .NET में अप्रतिबंधित संपादन योग्य क्षेत्र Word दस्तावेज़ के भीतर के क्षेत्र हैं जहाँ सामग्री को बिना किसी प्रतिबंध के संपादित किया जा सकता है, भले ही दस्तावेज़ का शेष भाग केवल पढ़ने के लिए सेट किया गया हो। ये क्षेत्र दस्तावेज़ के विशिष्ट भागों को परिभाषित करने का एक तरीका प्रदान करते हैं जिन्हें उपयोगकर्ता समग्र दस्तावेज़ सुरक्षा को बनाए रखते हुए संशोधित कर सकते हैं।

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके अप्रतिबंधित संपादन योग्य क्षेत्र कैसे बना सकता हूं?

उत्तर: Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में अप्रतिबंधित संपादन योग्य क्षेत्र बनाने के लिए, आप इन चरणों का पालन कर सकते हैं:
1.  मौजूदा दस्तावेज़ को लोड करें`Document` कक्षा।
2.  दस्तावेज़ सुरक्षा को केवल पढ़ने के लिए सेट करें`Protect` की विधि`Document` वस्तु।
3.  उपयोग`DocumentBuilder` क्लास में एक संपादन योग्य श्रेणी जोड़कर उसे बनाएं`EditableRangeStart` वस्तु और एक`EditableRangeEnd` वस्तु।
4.  संपादन योग्य सीमा के भीतर सामग्री जोड़ें`DocumentBuilder`.
5.  संशोधित दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु।

#### प्रश्न: क्या मैं Word दस्तावेज़ में एकाधिक अप्रतिबंधित संपादन योग्य क्षेत्र रख सकता हूँ?

उत्तर: हां, आप Word दस्तावेज़ में कई अप्रतिबंधित संपादन योग्य क्षेत्र रख सकते हैं। इसे प्राप्त करने के लिए, आप कई सेट बना सकते हैं`EditableRangeStart` और`EditableRangeEnd` वस्तुओं का उपयोग`DocumentBuilder` क्लास। ऑब्जेक्ट्स का प्रत्येक सेट एक अलग संपादन योग्य क्षेत्र को परिभाषित करेगा जहां उपयोगकर्ता बिना किसी प्रतिबंध के सामग्री को संशोधित कर सकते हैं।

#### प्रश्न: क्या मैं संपादन योग्य क्षेत्रों को एक दूसरे के भीतर रख सकता हूँ?

 उत्तर: नहीं, आप .NET के लिए Aspose.Words का उपयोग करके संपादन योग्य क्षेत्रों को एक दूसरे के भीतर नेस्ट नहीं कर सकते। प्रत्येक संपादन योग्य क्षेत्र को एक द्वारा परिभाषित किया जाता है`EditableRangeStart` और`EditableRangeEnd` जोड़ी स्वतंत्र होनी चाहिए और किसी अन्य संपादन योग्य क्षेत्र में ओवरलैप या नेस्टेड नहीं होनी चाहिए। नेस्टेड संपादन योग्य क्षेत्र समर्थित नहीं हैं।

#### प्रश्न: क्या मैं संपादन योग्य क्षेत्र के दस्तावेज़ से केवल पढ़ने के लिए सुरक्षा हटा सकता हूँ?

उत्तर: नहीं, आप संपादन योग्य क्षेत्र के भीतर दस्तावेज़ से केवल पढ़ने के लिए सुरक्षा को हटा नहीं सकते। केवल पढ़ने के लिए सुरक्षा पूरे दस्तावेज़ पर लागू होती है, और इसे विशिष्ट संपादन योग्य क्षेत्रों के भीतर चुनिंदा रूप से हटाया नहीं जा सकता है। संपादन योग्य क्षेत्रों का उद्देश्य समग्र दस्तावेज़ को केवल पढ़ने के लिए रखते हुए सामग्री संशोधन की अनुमति देना है।