---
title: स्वरूपित तालिका
linktitle: स्वरूपित तालिका
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में स्वरूपित तालिका बनाने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/formatted-table/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में फ़ॉर्मेट की गई तालिका कैसे बनाई जाए। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत में, आप अपने Word दस्तावेज़ों में प्रोग्रामेटिक रूप से कस्टम फ़ॉर्मेटिंग के साथ तालिकाएँ बनाने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. Visual Studio लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. Aspose.Words for .NET लाइब्रेरी में संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ बनाना और दस्तावेज़ जनरेटर को आरंभ करना
फ़ॉर्मेटेड टेबल बनाना शुरू करने के लिए, हमें एक नया दस्तावेज़ बनाना होगा और दस्तावेज़ जनरेटर को आरंभ करना होगा। इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ बनाएँ और दस्तावेज़ जनरेटर आरंभ करें
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

"आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से प्रतिस्थापित करना सुनिश्चित करें।

## चरण 3: स्वरूपित तालिका बनाना
इसके बाद, हम दस्तावेज़ बिल्डर द्वारा प्रदान की गई विधियों का उपयोग करके स्वरूपित तालिका का निर्माण करेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
// सरणी निर्माण शुरू करें
Table table = builder. StartTable();

// तालिका शीर्ष पंक्ति का निर्माण
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// सरणी निकाय का निर्माण
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// सारणी निर्माण का अंत
builder. EndTable();
```

 यहाँ हम टेबल को चरण दर चरण बनाने के लिए डॉक्यूमेंट बिल्डर का उपयोग करते हैं। हम कॉल करके शुरू करते हैं`StartTable()` तालिका को आरंभ करने के लिए। फिर हम उपयोग करते हैं`InsertCell()` कोशिकाओं को सम्मिलित करने के लिए और`Write()` प्रत्येक सेल में सामग्री जोड़ने के लिए। हम टेबल पंक्तियों, सेल और टेक्स्ट के स्वरूपण को परिभाषित करने के लिए विभिन्न स्वरूपण गुणों का भी उपयोग करते हैं।

## चरण 4: दस्तावेज़ सहेजें
अंत में, हमें फ़ॉर्मेट की गई तालिका वाले दस्तावेज़ को सहेजना होगा। निम्नलिखित कोड का उपयोग करें:

```csharp
// दस्तावेज़ सहेजें
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके स्वरूपित तालिका के लिए नमूना स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// तालिका में कम से कम एक पंक्ति मौजूद होने के बाद तालिका वाइड फ़ॉर्मेटिंग लागू की जानी चाहिए.
	table.LeftIndent = 20.0;
	// शीर्ष पंक्ति के लिए ऊंचाई निर्धारित करें और ऊंचाई नियम परिभाषित करें।
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// हमें इस सेल की चौड़ाई निर्दिष्ट करने की आवश्यकता नहीं है क्योंकि यह पिछले सेल से विरासत में मिली है।
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// ऊंचाई रीसेट करें और तालिका बॉडी के लिए एक अलग ऊंचाई नियम परिभाषित करें।
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// फ़ॉन्ट स्वरूपण रीसेट करें.
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में फ़ॉर्मेट की गई तालिका कैसे बनाई जाती है। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप अपने Word दस्तावेज़ों में प्रोग्रामेटिक रूप से विशिष्ट फ़ॉर्मेटिंग के साथ कस्टम टेबल बना सकते हैं। यह सुविधा आपको अपने डेटा को आकर्षक और व्यवस्थित तरीके से प्रस्तुत करने और संरचित करने की अनुमति देती है।