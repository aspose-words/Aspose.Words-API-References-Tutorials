---
title: क्षैतिज विलय
linktitle: क्षैतिज विलय
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ Word तालिका में सेल्स को क्षैतिज रूप से मर्ज करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/horizontal-merge/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका में कोशिकाओं को क्षैतिज रूप से कैसे मर्ज किया जाए। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण दर चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत तक, आप प्रोग्रामेटिक रूप से अपने वर्ड टेबल में कोशिकाओं को क्षैतिज रूप से मर्ज करने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. विज़ुअल स्टूडियो लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ बनाना और दस्तावेज़ जनरेटर प्रारंभ करना
तालिका और कक्षों के साथ वर्ड प्रोसेसिंग शुरू करने के लिए, हमें एक नया दस्तावेज़ बनाना होगा और दस्तावेज़ जनरेटर को आरंभ करना होगा। इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ बनाएं और दस्तावेज़ जनरेटर प्रारंभ करें
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

अपने दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ "आपकी दस्तावेज़ निर्देशिका" को बदलना सुनिश्चित करें।

## चरण 3: कोशिकाओं के क्षैतिज विलय के साथ तालिका का निर्माण
इसके बाद, हम तालिका बनाएंगे और .NET के लिए Aspose.Words द्वारा प्रदान किए गए गुणों का उपयोग करके क्षैतिज सेल विलय लागू करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// यह सेल पिछले सेल के साथ मर्ज हो गया है और खाली होना चाहिए।
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 यहां हम तालिका बनाने और सेल क्षैतिज मर्ज गुण सेट करने के लिए दस्तावेज़ बिल्डर का उपयोग करते हैं। हम उपयोग करते हैं`HorizontalMerge` की संपत्ति`CellFormat` प्रत्येक सेल पर लागू होने वाले क्षैतिज मर्ज के प्रकार को निर्दिष्ट करने के लिए ऑब्जेक्ट। का उपयोग करते हुए`CellMerge.First` उपयोग करते समय हम पहली सेल को अगली सेल के साथ मर्ज कर देते हैं`CellMerge.Previous` हम वर्तमान सेल को पिछले सेल के साथ मर्ज करते हैं।`CellMerge.None` इंगित करता है कि सेल का विलय नहीं किया जाना चाहिए।

## चरण 4: संशोधित दस्तावेज़ को सहेजना
अंत में, हमें संशोधित दस्तावेज़ को क्षैतिज रूप से मर्ज की गई कोशिकाओं के साथ सहेजने की आवश्यकता है। निम्नलिखित कोड का प्रयोग करें:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके क्षैतिज मर्ज के लिए नमूना स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// यह सेल पिछले सेल में मर्ज हो गया है और खाली होना चाहिए।
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका में कोशिकाओं को क्षैतिज रूप से कैसे मर्ज किया जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप प्रोग्रामेटिक रूप से अपने वर्ड टेबल में क्षैतिज सेल मर्जिंग लागू कर सकते हैं। यह सुविधा आपको अधिक जटिल तालिका लेआउट बनाने और अपने डेटा को बेहतर ढंग से व्यवस्थित करने की अनुमति देती है।