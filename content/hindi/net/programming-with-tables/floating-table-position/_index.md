---
title: फ़्लोटिंग टेबल स्थिति
linktitle: फ़्लोटिंग टेबल स्थिति
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: Aspose.Words for .NET के साथ Word दस्तावेज़ में तालिका को फ़्लोटिंग स्थिति में रखना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/floating-table-position/
---

इस ट्यूटोरियल में, हम सीखेंगे कि वर्ड डॉक्यूमेंट में टेबल को फ्लोटिंग पोजीशन में रखने के लिए Aspose.Words for .NET का उपयोग कैसे करें। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत में, आप अपने वर्ड डॉक्यूमेंट में फ्लोटिंग टेबल की स्थिति और संरेखण को प्रोग्रामेटिक रूप से नियंत्रित करने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. Visual Studio लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. Aspose.Words for .NET लाइब्रेरी में संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ लोड करना और तालिका तक पहुँचना
तालिका के साथ वर्ड प्रोसेसिंग शुरू करने के लिए, हमें उस दस्तावेज़ को लोड करना होगा जिसमें यह शामिल है और इसे एक्सेस करना होगा। इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// सरणी तक पहुंच
Table table = doc.FirstSection.Body.Tables[0];
```

"आपकी दस्तावेज़ निर्देशिका" को अपने दस्तावेज़ निर्देशिका के वास्तविक पथ से बदलना सुनिश्चित करें। साथ ही, सुनिश्चित करें कि दस्तावेज़ में एक तालिका है जो फ़्लोटिंग स्थिति में स्थित होगी।

## चरण 3: फ़्लोटिंग बोर्ड की स्थिति निर्धारित करना
इसके बाद, हम .NET के लिए Aspose.Words द्वारा प्रदान किए गए गुणों का उपयोग करके तालिका को फ़्लोटिंग स्थिति में रखेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
// फ़्लोटिंग टेबल की स्थिति निर्धारित करना
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 यहाँ हम उपयोग करते हैं`AbsoluteHorizontalDistance` पृष्ठ के बाएं किनारे से तालिका की पूर्ण क्षैतिज दूरी निर्धारित करने के लिए गुण। हम इसका भी उपयोग करते हैं`RelativeVerticalAlignment` आस-पास की सामग्री के लिए तालिका के सापेक्ष ऊर्ध्वाधर संरेखण को सेट करने के लिए गुण।

## चरण 4: संशोधित दस्तावेज़ को सहेजना
अंत में, हमें संशोधित दस्तावेज़ को टेबल को फ़्लोटिंग स्थिति में रखकर सहेजना होगा। निम्नलिखित कोड का उपयोग करें:

```csharp
// संशोधित दस्तावेज़ सहेजें
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके फ्लोटिंग टेबल पोजिशन के लिए नमूना स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में किसी टेबल को फ़्लोटिंग स्थिति में कैसे रखा जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप अपने Word दस्तावेज़ों में फ़्लोटिंग टेबल की स्थिति और संरेखण को प्रोग्रामेटिक रूप से नियंत्रित कर सकते हैं।