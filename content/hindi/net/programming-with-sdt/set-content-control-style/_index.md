---
title: सामग्री नियंत्रण शैली सेट करें
linktitle: सामग्री नियंत्रण शैली सेट करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में सामग्री नियंत्रण की शैली को सुसंगत स्वरूपण लागू करते हुए सेट करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/set-content-control-style/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में सामग्री नियंत्रण की शैली कैसे सेट करें। आप सुसंगत स्वरूपण के लिए सामग्री नियंत्रणों पर पूर्व-निर्धारित या कस्टम शैलियाँ लागू कर सकते हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए आपके पास निम्नलिखित चीजें होनी चाहिए:

- Aspose.Words for .NET लाइब्रेरी स्थापित की गई।
- C# और वर्ड दस्तावेजों के साथ वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपने दस्तावेज़ निर्देशिका का पथ सेट करके प्रारंभ करें।`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहां आपका दस्तावेज़ स्थित है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ लोड करें और सामग्री नियंत्रण पुनः प्राप्त करें
 Word दस्तावेज़ को लोड करने के लिए निम्न का उपयोग करें:`Document` कंस्ट्रक्टर, दस्तावेज़ के पथ को पैरामीटर के रूप में पास करता है। दस्तावेज़ से वांछित सामग्री नियंत्रण प्राप्त करें। इस उदाहरण में, हम मानते हैं कि सामग्री नियंत्रण दस्तावेज़ में पहला संरचित दस्तावेज़ टैग है।

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## चरण 3: शैली पुनः प्राप्त करें और सामग्री नियंत्रण पर लागू करें
 दस्तावेज़ के स्टाइल संग्रह से वांछित स्टाइल प्राप्त करें। इस उदाहरण में, हम "कोट" स्टाइल को उपयोग करके प्राप्त करते हैं`StyleIdentifier.Quote` . फिर, पुनर्प्राप्त शैली को असाइन करें`Style` संरचित दस्तावेज़ टैग की संपत्ति.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## चरण 4: दस्तावेज़ सहेजें
 संशोधित दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save`विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.SetContentControlStyle.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके सामग्री नियंत्रण शैली सेट करने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

बस! आपने Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ में सामग्री नियंत्रण की शैली सफलतापूर्वक सेट कर ली है।