---
title: सामग्री नियंत्रण शैली सेट करें
linktitle: सामग्री नियंत्रण शैली सेट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि .NET के लिए Aspose.Words का उपयोग करके, लगातार फ़ॉर्मेटिंग लागू करके किसी Word दस्तावेज़ में सामग्री नियंत्रण की शैली कैसे सेट करें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/set-content-control-style/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में सामग्री नियंत्रण की शैली कैसे सेट करें। आप सुसंगत स्वरूपण के लिए सामग्री नियंत्रण में पूर्व-परिभाषित या कस्टम शैलियाँ लागू कर सकते हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, आपके पास निम्नलिखित होना चाहिए:

- .NET लाइब्रेरी के लिए Aspose.Words स्थापित।
- वर्ड दस्तावेजों के साथ सी# और वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करके प्रारंभ करें। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आपका दस्तावेज़ स्थित है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ लोड करें और सामग्री नियंत्रण पुनः प्राप्त करें
 का उपयोग करके Word दस्तावेज़ लोड करें`Document` कंस्ट्रक्टर, एक पैरामीटर के रूप में दस्तावेज़ का पथ पास कर रहा है। दस्तावेज़ से वांछित सामग्री नियंत्रण पुनः प्राप्त करें। इस उदाहरण में, हम मानते हैं कि सामग्री नियंत्रण दस्तावेज़ में पहला संरचित दस्तावेज़ टैग है।

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## चरण 3: शैली पुनः प्राप्त करें और सामग्री नियंत्रण पर लागू करें
 दस्तावेज़ के शैलियों संग्रह से वांछित शैली पुनर्प्राप्त करें। इस उदाहरण में, हम "उद्धरण" शैली का उपयोग करके पुनः प्राप्त करते हैं`StyleIdentifier.Quote` . फिर, पुनर्प्राप्त शैली को असाइन करें`Style` संरचित दस्तावेज़ टैग की संपत्ति।

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## चरण 4: दस्तावेज़ सहेजें
 का उपयोग करके संशोधित दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` तरीका। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.SetContentControlStyle.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके सामग्री नियंत्रण शैली सेट करने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ में सामग्री नियंत्रण की शैली को सफलतापूर्वक सेट कर लिया है।