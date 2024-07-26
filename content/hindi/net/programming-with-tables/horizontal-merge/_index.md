---
title: क्षैतिज मर्ज
linktitle: क्षैतिज मर्ज
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ Word तालिका में कक्षों को क्षैतिज रूप से मर्ज करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/horizontal-merge/
---

इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में तालिका में कोशिकाओं को क्षैतिज रूप से कैसे मर्ज किया जाए। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत तक, आप अपने Word तालिकाओं में कोशिकाओं को प्रोग्रामेटिक रूप से क्षैतिज रूप से मर्ज करने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. Visual Studio लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. Aspose.Words for .NET लाइब्रेरी में संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ बनाना और दस्तावेज़ जनरेटर को आरंभ करना
टेबल और सेल के साथ वर्ड्स प्रोसेसिंग शुरू करने के लिए, हमें एक नया दस्तावेज़ बनाना होगा और दस्तावेज़ जनरेटर को आरंभ करना होगा। इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//दस्तावेज़ बनाएँ और दस्तावेज़ जनरेटर आरंभ करें
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

"आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से प्रतिस्थापित करना सुनिश्चित करें।

## चरण 3: कोशिकाओं के क्षैतिज विलय के साथ तालिका का निर्माण
इसके बाद, हम टेबल बनाएंगे और .NET के लिए Aspose.Words द्वारा प्रदान किए गए गुणों का उपयोग करके क्षैतिज सेल मर्जिंग लागू करेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// यह सेल पिछले सेल के साथ विलय हो गया है और खाली होना चाहिए।
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 यहाँ हम टेबल बनाने और सेल क्षैतिज मर्ज गुण सेट करने के लिए दस्तावेज़ बिल्डर का उपयोग करते हैं।`HorizontalMerge` की संपत्ति`CellFormat` प्रत्येक सेल पर लागू करने के लिए क्षैतिज मर्ज के प्रकार को निर्दिष्ट करने के लिए ऑब्जेक्ट का उपयोग करें।`CellMerge.First` हम पहले सेल को अगले सेल के साथ मिलाते हैं, जबकि`CellMerge.Previous` हम वर्तमान सेल को पिछले सेल के साथ विलय कर देते हैं।`CellMerge.None` यह इंगित करता है कि सेल को मर्ज नहीं किया जाना चाहिए.

## चरण 4: संशोधित दस्तावेज़ को सहेजना
अंत में, हमें संशोधित दस्तावेज़ को क्षैतिज रूप से मर्ज की गई कोशिकाओं के साथ सहेजना होगा। निम्नलिखित कोड का उपयोग करें:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके क्षैतिज मर्ज के लिए नमूना स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// यह सेल पिछले सेल में विलय हो गया है और खाली होना चाहिए।
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
इस ट्यूटोरियल में, हमने सीखा कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में तालिका में कोशिकाओं को क्षैतिज रूप से कैसे मर्ज किया जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और प्रदान किए गए C# कोड को लागू करके, आप अपने Word तालिकाओं में क्षैतिज सेल मर्जिंग को प्रोग्रामेटिक रूप से लागू कर सकते हैं। यह सुविधा आपको अधिक जटिल तालिका लेआउट बनाने और अपने डेटा को बेहतर ढंग से व्यवस्थित करने की अनुमति देती है।