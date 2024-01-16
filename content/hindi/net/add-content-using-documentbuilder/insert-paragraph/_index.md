---
title: वर्ड डॉक्यूमेंट में पैराग्राफ डालें
linktitle: वर्ड डॉक्यूमेंट में पैराग्राफ डालें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में स्वरूपित पैराग्राफ़ सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/add-content-using-documentbuilder/insert-paragraph/
---
इस व्यापक ट्यूटोरियल में, आप सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में पैराग्राफ कैसे सम्मिलित करें। हम प्रक्रिया में आपका मार्गदर्शन करेंगे और आपको आवश्यक C# कोड स्निपेट प्रदान करेंगे। इस गाइड के अंत तक, आप अपने दस्तावेज़ों में स्वरूपित पैराग्राफ जोड़ने में सक्षम होंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- आपके सिस्टम पर .NET लाइब्रेरी के लिए Aspose.Words इंस्टॉल किया गया है।

## चरण 1: एक नया दस्तावेज़ और दस्तावेज़बिल्डर बनाएँ
आरंभ करने के लिए, दस्तावेज़ वर्ग का उपयोग करके एक नया दस्तावेज़ बनाएं और एक दस्तावेज़बिल्डर ऑब्जेक्ट प्रारंभ करें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: फ़ॉन्ट और फ़ॉर्मेटिंग सेट करें
इसके बाद, क्रमशः फ़ॉन्ट और पैराग्राफफ़ॉर्मेट ऑब्जेक्ट का उपयोग करके फ़ॉन्ट गुण और पैराग्राफ़ फ़ॉर्मेटिंग सेट करें:

```csharp
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;
```

## चरण 3: एक पैराग्राफ डालें
फ़ॉन्ट सेट करने और फ़ॉर्मेट करने के बाद, संपूर्ण पैराग्राफ़ सम्मिलित करने के लिए दस्तावेज़बिल्डर वर्ग की राइटलन विधि का उपयोग करें:

```csharp
builder.Writeln("A whole paragraph.");
```

## चरण 4: दस्तावेज़ सहेजें
पैराग्राफ डालने के बाद, दस्तावेज़ वर्ग की सेव विधि का उपयोग करके दस्तावेज़ को फ़ाइल में सहेजें:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## .NET के लिए Aspose.Words का उपयोग करके पैराग्राफ सम्मिलित करने के लिए उदाहरण स्रोत कोड
.NET के लिए Aspose.Words का उपयोग करके पैराग्राफ़ सम्मिलित करने का संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;

builder.Writeln("A whole paragraph.");

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## निष्कर्ष
बधाई हो! आपने .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में स्वरूपित पैराग्राफ़ सम्मिलित करना सफलतापूर्वक सीख लिया है। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए स्रोत कोड का उपयोग करके, अब आप अपने दस्तावेज़ों में विशिष्ट फ़ॉन्ट, फ़ॉर्मेटिंग और संरेखण के साथ अनुकूलित पैराग्राफ जोड़ सकते हैं।

### वर्ड दस्तावेज़ में पैराग्राफ़ सम्मिलित करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं एक ही दस्तावेज़ में अलग-अलग फ़ॉर्मेटिंग वाले कई पैराग्राफ़ सम्मिलित कर सकता हूँ?

 उ: हां, आप .NET के लिए Aspose.Words का उपयोग करके एक ही दस्तावेज़ में विभिन्न स्वरूपण के साथ कई पैराग्राफ सम्मिलित कर सकते हैं। कॉल करने से पहले बस फ़ॉन्ट और पैराग्राफ़ फ़ॉर्मेटिंग गुणों को समायोजित करें`Writeln` प्रत्येक अनुच्छेद के लिए विधि.

#### प्रश्न: मैं पैराग्राफ के लिए लाइन स्पेसिंग और इंडेंटेशन कैसे सेट कर सकता हूं?

 उ: .NET के लिए Aspose.Words पैराग्राफ के लिए लाइन स्पेसिंग और इंडेंटेशन सेट करने के विकल्प प्रदान करता है। आप समायोजित कर सकते हैं`LineSpacing` और`LeftIndent` के गुण`ParagraphFormat` इन पहलुओं को नियंत्रित करने के लिए वस्तु।

#### प्रश्न: क्या DocumentBuilder का उपयोग करके बुलेटेड या क्रमांकित सूचियाँ सम्मिलित करना संभव है?

 उत्तर: हां, आप इसे सेट करके बुलेटेड या क्रमांकित सूचियां बना सकते हैं`ListFormat` के गुण`DocumentBuilder` वस्तु। आप इसका उपयोग करके सूची आइटम जोड़ सकते हैं`Writeln` विधि, और क्रमांकन या बुलेट शैली स्वचालित रूप से लागू हो जाएगी।

#### प्रश्न: क्या मैं पैराग्राफ के भीतर हाइपरलिंक या अन्य तत्व सम्मिलित कर सकता हूँ?

 उत्तर: बिल्कुल! आप इसका उपयोग करके पैराग्राफ के भीतर हाइपरलिंक, चित्र और अन्य तत्व सम्मिलित कर सकते हैं`DocumentBuilder` कक्षा। यह आपको अपने पैराग्राफ में समृद्ध और इंटरैक्टिव सामग्री बनाने की अनुमति देता है।

#### प्रश्न: मैं किसी अनुच्छेद में विशेष वर्ण या प्रतीक कैसे सम्मिलित कर सकता हूँ?

 उ: विशेष वर्ण या प्रतीक सम्मिलित करने के लिए, आप इसका उपयोग कर सकते हैं`Writeln` वांछित यूनिकोड प्रतिनिधित्व के साथ विधि या का उपयोग करें`InsertSpecialChar` की विधि`DocumentBuilder` कक्षा।