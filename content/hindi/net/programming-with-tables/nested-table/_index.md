---
title: नेस्टेड टेबल
linktitle: नेस्टेड टेबल
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में नेस्टेड तालिका बनाना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/nested-table/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में नेस्टेड टेबल कैसे बनाएं। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण दर चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत तक, आप अपने वर्ड दस्तावेज़ों में प्रोग्रामेटिक रूप से नेस्टेड टेबल बनाने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. विज़ुअल स्टूडियो लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ बनाना और दस्तावेज़ जनरेटर प्रारंभ करना
दस्तावेज़ और दस्तावेज़ जनरेटर के साथ वर्ड प्रोसेसिंग शुरू करने के लिए, इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ निर्माण
Document doc = new Document();

// दस्तावेज़ जेनरेटर प्रारंभ करें
DocumentBuilder builder = new DocumentBuilder(doc);
```

अपने दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ "आपकी दस्तावेज़ निर्देशिका" को बदलना सुनिश्चित करें।

## चरण 3: नेस्टेड टेबल का निर्माण
इसके बाद, हम बाहरी तालिका में सेल सम्मिलित करके और पहले सेल के अंदर एक नई तालिका बनाकर नेस्टेड तालिका का निर्माण करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
// बाहरी तालिका का पहला सेल डालें
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// बाहरी तालिका का दूसरा सेल डालें
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// बाहरी तालिका की समाप्ति
builder. EndTable();

// बाहरी तालिका के प्रथम कक्ष में जाएँ
builder.MoveTo(cell.FirstParagraph);

// आंतरिक तालिका बनाएँ
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// भीतरी मेज का अंत
builder. EndTable();
```

यहां हम बाहरी तालिका में सेल और सामग्री सम्मिलित करने के लिए दस्तावेज़ बिल्डर का उपयोग करते हैं। फिर हम दस्तावेज़ बिल्डर कर्सर को बाहरी तालिका के पहले सेल में ले जाते हैं और अंदर सेल और सामग्री डालकर एक नई तालिका बनाते हैं।

## चरण 4: संशोधित दस्तावेज़ को सहेजना
अंत में, हमें संशोधित दस्तावेज़ को नेस्टेड तालिका के साथ सहेजना होगा। निम्नलिखित कोड का प्रयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और नाम फ़ाइल निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके नेस्टेड टेबल के लिए नमूना स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// पहली तालिका के भीतर नेस्टेड तालिका बनाने के लिए यह कॉल महत्वपूर्ण है।
	// इस कॉल के बिना, नीचे डाली गई कोशिकाओं को बाहरी तालिका में जोड़ दिया जाएगा।
	builder.EndTable();
	// बाहरी तालिका के प्रथम कक्ष में जाएँ।
	builder.MoveTo(cell.FirstParagraph);
	// आंतरिक तालिका बनाएँ.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में नेस्टेड तालिका कैसे बनाई जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप प्रोग्रामेटिक रूप से अपने Word दस्तावेज़ों में अपनी विशिष्ट आवश्यकताओं के अनुसार नेस्टेड तालिकाएँ बना सकते हैं।
