---
title: स्पष्ट सामग्री नियंत्रण
linktitle: स्पष्ट सामग्री नियंत्रण
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में नियंत्रण की सामग्री को साफ़ करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/clear-contents-control/
---

यह ट्यूटोरियल दर्शाता है कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में SDT की सामग्री को कैसे साफ़ किया जाए। एसडीटी की सामग्री को साफ़ करने से सामग्री नियंत्रण के भीतर कोई भी टेक्स्ट या चाइल्ड नोड हट जाता है।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, आपके पास निम्नलिखित होना चाहिए:

- .NET लाइब्रेरी के लिए Aspose.Words स्थापित।
- वर्ड दस्तावेजों के साथ सी# और वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करके प्रारंभ करें। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आपका दस्तावेज़ स्थित है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ लोड करें और StructuredDocumentTag प्राप्त करें
 का उपयोग करके Word दस्तावेज़ लोड करें`Document` कंस्ट्रक्टर, एक पैरामीटर के रूप में दस्तावेज़ का पथ पास कर रहा है। फिर, वांछित पुनः प्राप्त करें`StructuredDocumentTag` दस्तावेज़ से. इस उदाहरण में, हम मानते हैं कि एसडीटी दस्तावेज़ में पहला चाइल्ड नोड है।

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## चरण 3: StructuredDocumentTag की सामग्री साफ़ करें
 का उपयोग करके एसडीटी की सामग्री साफ़ करें`Clear` तरीका। यह सामग्री नियंत्रण के भीतर किसी भी पाठ या चाइल्ड नोड्स को हटा देता है।

```csharp
sdt.Clear();
```

## चरण 4: दस्तावेज़ सहेजें
 का उपयोग करके संशोधित दस्तावेज़ को सहेजें`Save`तरीका। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.ClearContentsControl.doc" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### .NET के लिए Aspose.Words का उपयोग करके स्पष्ट सामग्री नियंत्रण के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ में StructuredDocumentTag की सामग्री को सफलतापूर्वक साफ़ कर दिया है।