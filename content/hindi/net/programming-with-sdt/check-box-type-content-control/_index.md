---
title: चेक बॉक्स प्रकार सामग्री नियंत्रण
linktitle: चेक बॉक्स प्रकार सामग्री नियंत्रण
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में चेक बॉक्स प्रकार सामग्री नियंत्रण बनाने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/check-box-type-content-control/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में चेक बॉक्स प्रकार सामग्री नियंत्रण कैसे बनाया जाए। चेक बॉक्स सामग्री नियंत्रण उपयोगकर्ताओं को दस्तावेज़ के भीतर एक चेकबॉक्स का चयन या साफ़ करने की अनुमति देता है।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए आपके पास निम्नलिखित चीजें होनी चाहिए:

- Aspose.Words for .NET लाइब्रेरी स्थापित की गई।
- C# और वर्ड दस्तावेजों के साथ वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपने दस्तावेज़ निर्देशिका का पथ सेट करके प्रारंभ करें।`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहाँ आप दस्तावेज़ को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ और दस्तावेज़बिल्डर बनाएँ
 एक नया उदाहरण बनाएँ`Document` कक्षा और एक`DocumentBuilder` दस्तावेज़ की सामग्री बनाने के लिए.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: चेक बॉक्स प्रकार सामग्री नियंत्रण जोड़ें
 एक बनाने के`StructuredDocumentTag` साथ`SdtType.Checkbox` चेक बॉक्स सामग्री नियंत्रण का प्रतिनिधित्व करने के लिए। निर्दिष्ट करें`MarkupLevel.Inline` इसे पाठ के भीतर रखने के लिए.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## चरण 4: दस्तावेज़ सहेजें
 दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.CheckBoxTypeContentControl.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### .NET के लिए Aspose.Words का उपयोग करके चेक बॉक्स प्रकार सामग्री नियंत्रण के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

बस! आपने .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ में सफलतापूर्वक चेक बॉक्स प्रकार सामग्री नियंत्रण बनाया है।