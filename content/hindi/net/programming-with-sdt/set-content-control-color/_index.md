---
title: सामग्री नियंत्रण रंग सेट करें
linktitle: सामग्री नियंत्रण रंग सेट करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में सामग्री नियंत्रण का रंग कैसे सेट करें, इसके स्वरूप को अनुकूलित करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/set-content-control-color/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में सामग्री नियंत्रण का रंग कैसे सेट किया जाए। आप सामग्री नियंत्रणों का रंग बदलकर उनकी उपस्थिति को अनुकूलित कर सकते हैं।

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
 Word दस्तावेज़ को लोड करने के लिए निम्न का उपयोग करें:`Document`कंस्ट्रक्टर, दस्तावेज़ के पथ को पैरामीटर के रूप में पास करता है। दस्तावेज़ से वांछित सामग्री नियंत्रण प्राप्त करें। इस उदाहरण में, हम मानते हैं कि सामग्री नियंत्रण दस्तावेज़ में पहला संरचित दस्तावेज़ टैग है।

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## चरण 3: सामग्री नियंत्रण रंग सेट करें
 सामग्री नियंत्रण का रंग निर्दिष्ट करके सेट करें`Color` मूल्य के लिए`Color` संरचित दस्तावेज़ टैग की संपत्ति। इस उदाहरण में, हमने रंग को लाल पर सेट किया है।

```csharp
sdt.Color = Color.Red;
```

## चरण 4: दस्तावेज़ सहेजें
 संशोधित दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.SetContentControlColor.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके सामग्री नियंत्रण रंग सेट करने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

बस! आपने Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ में सामग्री नियंत्रण का रंग सफलतापूर्वक सेट कर लिया है।