---
title: नेस्टेड तालिका
linktitle: नेस्टेड तालिका
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में नेस्टेड तालिका बनाने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/nested-table/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में नेस्टेड टेबल कैसे बनाएँ। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत तक, आप अपने Word दस्तावेज़ों में प्रोग्रामेटिक रूप से नेस्टेड टेबल बनाने में सक्षम हो जाएँगे।

## चरण 1: प्रोजेक्ट सेटअप
1. Visual Studio लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. Aspose.Words for .NET लाइब्रेरी में संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ बनाना और दस्तावेज़ जनरेटर को आरंभ करना
दस्तावेज़ और दस्तावेज़ जनरेटर के साथ वर्ड्स प्रोसेसिंग शुरू करने के लिए, इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ निर्माण
Document doc = new Document();

// दस्तावेज़ जनरेटर आरंभ करें
DocumentBuilder builder = new DocumentBuilder(doc);
```

"आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से प्रतिस्थापित करना सुनिश्चित करें।

## चरण 3: नेस्टेड टेबल का निर्माण
इसके बाद, हम बाहरी टेबल में सेल डालकर और पहले सेल के अंदर एक नई टेबल बनाकर नेस्टेड टेबल बनाएंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
// बाहरी तालिका का पहला कक्ष डालें
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// बाहरी तालिका का दूसरा कक्ष डालें
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// बाहरी तालिका की समाप्ति
builder. EndTable();

// बाहरी तालिका के पहले कक्ष पर जाएँ
builder.MoveTo(cell.FirstParagraph);

// आंतरिक तालिका बनाएं
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// आंतरिक मेज का अंत
builder. EndTable();
```

यहाँ हम बाहरी टेबल में सेल और कंटेंट डालने के लिए डॉक्यूमेंट बिल्डर का उपयोग करते हैं। फिर हम डॉक्यूमेंट बिल्डर कर्सर को बाहरी टेबल के पहले सेल पर ले जाते हैं और सेल और कंटेंट डालकर अंदर एक नई टेबल बनाते हैं।

## चरण 4: संशोधित दस्तावेज़ को सहेजना
अंत में, हमें संशोधित दस्तावेज़ को नेस्टेड टेबल के साथ सहेजना होगा। निम्नलिखित कोड का उपयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और नाम फ़ाइल निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके नेस्टेड टेबल के लिए नमूना स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// यह कॉल पहली तालिका के भीतर नेस्टेड तालिका बनाने के लिए महत्वपूर्ण है।
	// इस कॉल के बिना, नीचे डाली गई कोशिकाएं बाहरी तालिका में जोड़ दी जाएंगी।
	builder.EndTable();
	// बाहरी तालिका के प्रथम कक्ष पर जाएँ।
	builder.MoveTo(cell.FirstParagraph);
	// आंतरिक तालिका बनाएं.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में नेस्टेड टेबल कैसे बनाएँ। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप अपने Word दस्तावेज़ों में अपनी विशिष्ट आवश्यकताओं के अनुसार प्रोग्रामेटिक रूप से नेस्टेड टेबल बना सकते हैं।
