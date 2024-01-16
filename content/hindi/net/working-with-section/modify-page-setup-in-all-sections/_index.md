---
title: सभी अनुभागों में वर्ड पेज सेटअप को संशोधित करें
linktitle: सभी अनुभागों में वर्ड पेज सेटअप को संशोधित करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: इस ट्यूटोरियल में, सीखें कि .NET के लिए Aspose.Words के साथ Word दस्तावेज़ के सभी अनुभागों में वर्ड पेज सेटअप को कैसे संशोधित किया जाए।
type: docs
weight: 10
url: /hi/net/working-with-section/modify-page-setup-in-all-sections/
---

इस ट्यूटोरियल में, हम आपको दिखाने जा रहे हैं कि .NET के लिए Aspose.Words लाइब्रेरी का उपयोग करके किसी Word दस्तावेज़ के सभी अनुभागों में वर्ड पेज सेटअप को कैसे संशोधित किया जाए। पेज सेटअप को बदलने में पेपर आकार, मार्जिन, ओरिएंटेशन आदि जैसी सेटिंग्स शामिल हो सकती हैं। हम आपके .NET प्रोजेक्ट में कोड को समझने और लागू करने में आपकी मदद करने के लिए चरण-दर-चरण कदम उठाएंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित चीज़ें हैं:
- C# प्रोग्रामिंग भाषा का कार्यसाधक ज्ञान
- आपके प्रोजेक्ट में .NET के लिए Aspose.Words लाइब्रेरी स्थापित है

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें
 सबसे पहले, आपको अपने Word दस्तावेज़ के स्थान पर निर्देशिका पथ सेट करना होगा। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उचित पथ के साथ कोड में।

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: एक दस्तावेज़ बनाएं और सामग्री और अनुभाग जोड़ें
 इसके बाद, हम इंस्टेंटियेट करके एक खाली दस्तावेज़ बनाएंगे`Document` वर्ग और एक संबद्ध`DocumentBuilder` दस्तावेज़ में सामग्री और अनुभाग जोड़ने के लिए कंस्ट्रक्टर। इस उदाहरण में, हम सामग्री और तीन अनुभाग जोड़ रहे हैं।

```csharp
// एक दस्तावेज़ बनाएँ
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// सामग्री और अनुभाग जोड़ें
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");
```

## चरण 3: सभी अनुभागों में पृष्ठ सेटअप संपादित करें
 दस्तावेज़ के सभी अनुभागों में पृष्ठ सेटअप को बदलने के लिए, हम इसका उपयोग करते हैं`foreach` प्रत्येक अनुभाग के माध्यम से लूप करें और उस तक पहुंचें`PageSetup` संपत्ति। इस उदाहरण में, हम मान सेट करके सभी अनुभागों के पेपर आकार को बदलते हैं`PaperSize.Letter`.

```csharp
foreach(Section section in doc.Sections)
     section.PageSetup.PaperSize = PaperSize.Letter;
```

### .NET के लिए Aspose.Words का उपयोग करके सभी अनुभागों में वर्ड पेज सेटअप को संशोधित करने के लिए नमूना स्रोत कोड 

```csharp

// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");

// यह समझना महत्वपूर्ण है कि एक दस्तावेज़ में कई अनुभाग हो सकते हैं,
// और प्रत्येक अनुभाग का अपना पेज सेटअप है। इस मामले में, हम उन सभी को संशोधित करना चाहते हैं।
foreach (Section section in doc)
	section.PageSetup.PaperSize = PaperSize.Letter;
doc.Save(dataDir + "WorkingWithSection.ModifyPageSetupInAllSections.doc");

```

## निष्कर्ष
इस ट्यूटोरियल में, हमने देखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ के सभी अनुभागों में वर्ड पेज सेटअप को कैसे संशोधित किया जाए। वर्णित चरणों का पालन करके, आप आसानी से प्रत्येक अनुभाग तक पहुंच सकते हैं और पृष्ठ कॉन्फ़िगरेशन सेटिंग्स को अनुकूलित कर सकते हैं। अपनी विशिष्ट आवश्यकताओं को पूरा करने के लिए इस सुविधा को अपनाने और उपयोग करने के लिए स्वतंत्र महसूस करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में दस्तावेज़ निर्देशिका कैसे सेट करें?

 उ: अपने दस्तावेज़ों वाली निर्देशिका का पथ सेट करने के लिए, आपको प्रतिस्थापित करना होगा`"YOUR DOCUMENT DIRECTORY"` उचित पथ के साथ कोड में। इसे करने का तरीका यहां बताया गया है:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

#### प्रश्न: दस्तावेज़ कैसे बनाएं और .NET के लिए Aspose.Words में सामग्री और अनुभाग कैसे जोड़ें?

 ए: इंस्टेंटियेट करके एक खाली दस्तावेज़ बनाने के लिए`Document` वर्ग और एक संबद्ध`DocumentBuilder` दस्तावेज़ में सामग्री और अनुभाग जोड़ने के लिए कंस्ट्रक्टर, आप निम्नलिखित कोड का उपयोग कर सकते हैं:

```csharp
// एक दस्तावेज़ बनाएँ
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// सामग्री और अनुभाग जोड़ें
builder. Writen("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder. Writen("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");
```

#### प्रश्न: .NET के लिए Aspose.Words में सभी अनुभागों में पेज सेटअप कैसे बदलें?

 उ: दस्तावेज़ के सभी अनुभागों में पृष्ठ सेटअप बदलने के लिए, आप इसका उपयोग कर सकते हैं`foreach` प्रत्येक अनुभाग के माध्यम से लूप करें और उस तक पहुंचें`PageSetup` संपत्ति। इस उदाहरण में, हम मान सेट करके सभी अनुभागों के पेपर आकार को बदलते हैं`PaperSize.Letter`.

```csharp
foreach(Section section in doc.Sections)
      section.PageSetup.PaperSize = PaperSize.Letter;
```

#### प्रश्न: संशोधित दस्तावेज़ को .NET के लिए Aspose.Words में कैसे सहेजें?

उ: एक बार जब आप सभी अनुभागों में पेज सेटअप बदल लेते हैं, तो आप निम्न कोड का उपयोग करके बदले हुए दस्तावेज़ को फ़ाइल में सहेज सकते हैं:

```csharp
doc.Save(dataDir + "Document_Modified.docx");
```