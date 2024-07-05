---
title: सामग्री नियंत्रण साफ़ करें
linktitle: सामग्री नियंत्रण साफ़ करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में नियंत्रण की सामग्री को साफ़ करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/clear-contents-control/
---

यह ट्यूटोरियल प्रदर्शित करता है कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में SDT की सामग्री को कैसे साफ़ किया जाए। SDT की सामग्री को साफ़ करने से सामग्री नियंत्रण के भीतर कोई भी टेक्स्ट या चाइल्ड नोड हट जाता है।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए आपके पास निम्नलिखित चीजें होनी चाहिए:

- Aspose.Words for .NET लाइब्रेरी स्थापित की गई।
- C# और वर्ड दस्तावेजों के साथ वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपने दस्तावेज़ निर्देशिका का पथ सेट करके प्रारंभ करें।`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहां आपका दस्तावेज़ स्थित है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ लोड करें और StructuredDocumentTag प्राप्त करें
 Word दस्तावेज़ को लोड करने के लिए निम्न का उपयोग करें:`Document` कंस्ट्रक्टर, दस्तावेज़ के पथ को पैरामीटर के रूप में पास करता है। फिर, वांछित प्राप्त करें`StructuredDocumentTag` दस्तावेज़ से। इस उदाहरण में, हम मानते हैं कि SDT दस्तावेज़ में पहला चाइल्ड नोड है।

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## चरण 3: StructuredDocumentTag की सामग्री साफ़ करें
 SDT की सामग्री को साफ़ करने के लिए निम्न का उपयोग करें:`Clear` विधि। यह सामग्री नियंत्रण के भीतर किसी भी पाठ या चाइल्ड नोड्स को हटा देता है।

```csharp
sdt.Clear();
```

## चरण 4: दस्तावेज़ सहेजें
 संशोधित दस्तावेज़ को सहेजें`Save`विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.ClearContentsControl.doc" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### .NET के लिए Aspose.Words का उपयोग करके क्लियर कंटेंट कंट्रोल के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

बस! आपने Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ में StructuredDocumentTag की सामग्री को सफलतापूर्वक साफ़ कर दिया है।