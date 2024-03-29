---
title: सामग्री के लिए ऑटो फ़िट तालिका
linktitle: सामग्री के लिए ऑटो फ़िट तालिका
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में किसी तालिका को उसकी सामग्री में स्वचालित रूप से फ़िट करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/auto-fit-table-to-contents/
---

इस ट्यूटोरियल में, हम सीखेंगे कि C# का उपयोग करके किसी Word दस्तावेज़ में किसी तालिका को उसकी सामग्री में स्वचालित रूप से फ़िट करने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें। हम इस कार्यक्षमता को प्राप्त करने के लिए कोड लिखने की चरण-दर-चरण प्रक्रिया से गुजरेंगे। इस ट्यूटोरियल के अंत तक, आपको इस बात की स्पष्ट समझ हो जाएगी कि Word दस्तावेज़ों में तालिकाओं को प्रोग्रामेटिक रूप से कैसे हेरफेर किया जाए।

## चरण 1: प्रोजेक्ट सेट करें
1. विज़ुअल स्टूडियो लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ जोड़ें।

## चरण 2: वर्ड दस्तावेज़ लोड करें
तालिका के साथ वर्ड प्रोसेसिंग शुरू करने के लिए, हमें उस वर्ड दस्तावेज़ को लोड करना होगा जिसमें तालिका शामिल है। इन चरणों का पालन करें:

```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Word दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Tables.docx");
```

अपने दस्तावेज़ के वास्तविक पथ के साथ "आपकी दस्तावेज़ निर्देशिका" को बदलना सुनिश्चित करें।

## चरण 3: तालिका तक पहुंचें और उसे सामग्री में स्वत: फिट करें
इसके बाद, हमें दस्तावेज़ के भीतर तालिका तक पहुंचने और ऑटो-फ़िट व्यवहार को लागू करने की आवश्यकता है। निम्नलिखित कोड का प्रयोग करें:

```csharp
// टेबल तक पहुंचें
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

// तालिका को उसकी सामग्री में स्वतः फ़िट करें
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

 यहां, हम प्रकार का पहला चाइल्ड नोड कास्टिंग कर रहे हैं`Table` दस्तावेज़ से और फिर इसका उपयोग करना`AutoFit` विधि के साथ`AutoFitToContents` तालिका की सामग्री को फिट करने के लिए उसकी चौड़ाई को समायोजित करने का व्यवहार।

## चरण 4: संशोधित दस्तावेज़ सहेजें
अंत में, हमें संशोधित दस्तावेज़ को ऑटो-फ़िटेड तालिका के साथ सहेजने की आवश्यकता है। निम्नलिखित कोड का प्रयोग करें:

```csharp
// संशोधित दस्तावेज़ सहेजें
doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

सुनिश्चित करें कि आप आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करते हैं।

### .NET के लिए Aspose.Words का उपयोग करके सामग्री में ऑटो फ़िट तालिका के लिए नमूना स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में किसी तालिका को उसकी सामग्री में स्वचालित रूप से कैसे फ़िट किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप प्रोग्रामेटिक रूप से अपने Word दस्तावेज़ों में तालिकाओं में हेरफेर कर सकते हैं। यह आपको इसकी सामग्री के आधार पर तालिका की चौड़ाई को गतिशील रूप से समायोजित करने की अनुमति देता है, और अधिक पेशेवर और दृश्यमान रूप से आकर्षक दस्तावेज़ प्रदान करता है।