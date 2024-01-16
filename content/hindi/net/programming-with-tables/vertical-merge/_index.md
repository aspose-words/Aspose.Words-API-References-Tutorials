---
title: लंबवत विलय
linktitle: लंबवत विलय
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में किसी तालिका में सेल्स को वर्टिकल मर्ज करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/vertical-merge/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका में सेल्स को वर्टिकल मर्ज कैसे करें। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण दर चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत में, आप Word दस्तावेज़ों में अपनी तालिकाओं में सेल्स को वर्टिकल मर्ज करने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. विज़ुअल स्टूडियो लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ लोड करना
दस्तावेज़ के साथ वर्ड प्रोसेसिंग प्रारंभ करने के लिए, इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

अपने दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ "आपकी दस्तावेज़ निर्देशिका" को बदलना सुनिश्चित करें।

## चरण 3: कोशिकाओं को लंबवत रूप से मर्ज करना
आगे हम तालिका में लंबवत कोशिकाओं को मर्ज करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
// एक सेल डालें
builder. InsertCell();

// पहले सेल पर वर्टिकल मर्ज लागू करें
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// दूसरा सेल डालें
builder. InsertCell();

// सेल पर कोई लंबवत मर्ज लागू न करें
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// एक सेल डालें
builder. InsertCell();

// पिछले सेल के साथ वर्टिकल मर्ज लागू करें
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// दूसरा सेल डालें
builder. InsertCell();

// सेल पर कोई लंबवत मर्ज लागू न करें
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//तालिका का निर्माण समाप्त करें
builder. EndTable();
```

इस कोड में, हम तालिका में सेल सम्मिलित करने के लिए DocumentBuilder कंस्ट्रक्टर का उपयोग करते हैं। हम CellFormat.VerticalMerge प्रॉपर्टी का उपयोग करके सेल में वर्टिकल मर्जिंग लागू करते हैं। हम पहले सेल मर्ज के लिए CellMerge.First का उपयोग करते हैं, पिछले सेल के साथ मर्ज करने के लिए CellMerge.Previous का उपयोग करते हैं, और बिना किसी वर्टिकल मर्ज के लिए CellMerge.None का उपयोग करते हैं।

## चरण 4: संशोधित दस्तावेज़ को सहेजना
अंत में, हमें संशोधित दस्तावेज़ को मर्ज किए गए सेल के साथ सहेजना होगा। निम्नलिखित कोड का प्रयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके वर्टिकल मर्ज के लिए नमूना स्रोत कोड 
```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// यह सेल ऊपर वाले सेल में लंबवत रूप से मर्ज किया गया है और खाली होना चाहिए।
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका में सेल्स को वर्टिकल मर्ज कैसे किया जाता है। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप आसानी से अपनी तालिकाओं में सेल वर्टिकल को मर्ज कर सकते हैं।