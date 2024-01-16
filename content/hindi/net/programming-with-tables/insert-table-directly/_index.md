---
title: सीधे टेबल डालें
linktitle: सीधे टेबल डालें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ किसी Word दस्तावेज़ में सीधे तालिका सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/insert-table-directly/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में सीधे तालिका कैसे सम्मिलित करें। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण दर चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत तक, आप सीधे अपने Word दस्तावेज़ों में प्रोग्रामेटिक रूप से तालिकाएँ सम्मिलित करने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. विज़ुअल स्टूडियो लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ और तालिका बनाना
एरे के साथ वर्ड प्रोसेसिंग शुरू करने के लिए, हमें एक नया दस्तावेज़ बनाना होगा और एरे को इनिशियलाइज़ करना होगा। इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ निर्माण
Document doc = new Document();

//सरणी बनाएं
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

अपने दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ "आपकी दस्तावेज़ निर्देशिका" को बदलना सुनिश्चित करें।

## चरण 3: सरणी का निर्माण
इसके बाद, हम पंक्तियों और कोशिकाओं को जोड़कर तालिका बनाएंगे। उदाहरण के तौर पर निम्नलिखित कोड का उपयोग करें:

```csharp
// पहली पंक्ति बनाएँ
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// पहला सेल बनाएं
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// पंक्ति में दूसरे सेल के लिए सेल को डुप्लिकेट करें
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 यहां हम के साथ एक पंक्ति बनाते हैं`AllowBreakAcrossPages` संपत्ति के लिए सेट`true` पंक्तियों के बीच पेज तोड़ने की अनुमति देने के लिए। फिर हम रंगीन पृष्ठभूमि, निश्चित चौड़ाई और निर्दिष्ट पाठ सामग्री के साथ एक सेल बनाते हैं। फिर हम पंक्ति में दूसरा सेल बनाने के लिए इस सेल की नकल करते हैं।

## चरण 4: ऑटो फ़िट टेबल
हम तालिका को सही ढंग से प्रारूपित करने के लिए उसमें स्वचालित समायोजन लागू कर सकते हैं। निम्नलिखित कोड का प्रयोग करें:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

कोड की यह पंक्ति निश्चित कॉलम चौड़ाई के आधार पर ऑटो-फ़िट लागू करती है।

## चरण 5: पंजीकरण करना

  संशोधित दस्तावेज़
अंत में, हमें संशोधित दस्तावेज़ को सीधे सम्मिलित तालिका के साथ सहेजना होगा। निम्नलिखित कोड का प्रयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके सीधे तालिका सम्मिलित करने के लिए नमूना स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// हम टेबल ऑब्जेक्ट बनाकर शुरुआत करते हैं। ध्यान दें कि हमें दस्तावेज़ ऑब्जेक्ट को पास करना होगा
	//प्रत्येक नोड के कंस्ट्रक्टर को। ऐसा इसलिए है क्योंकि हमारे द्वारा बनाया गया प्रत्येक नोड संबंधित होना चाहिए
	// किसी दस्तावेज़ के लिए.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// यहां हम अपने लिए पंक्तियां और सेल बनाने के लिए EnsureMinimum को कॉल कर सकते हैं। इस विधि का प्रयोग किया जाता है
	// यह सुनिश्चित करने के लिए कि निर्दिष्ट नोड वैध है। इस स्थिति में, एक वैध तालिका में कम से कम एक पंक्ति और एक कक्ष होना चाहिए।
	// इसके बजाय, हम पंक्ति और तालिका बनाने का काम स्वयं संभालेंगे।
	// यदि हम किसी एल्गोरिथम के अंदर एक तालिका बना रहे हों तो ऐसा करने का यह सबसे अच्छा तरीका होगा।
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// अब हम कोई भी ऑटो फ़िट सेटिंग लागू कर सकते हैं.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// फिर हम तालिका में अन्य कक्षों और पंक्तियों के लिए प्रक्रिया दोहराएंगे।
	// हम मौजूदा कोशिकाओं और पंक्तियों की क्लोनिंग करके भी चीजों को गति दे सकते हैं।
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में सीधे तालिका कैसे सम्मिलित करें। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप सीधे अपने Word दस्तावेज़ों में प्रोग्रामेटिक रूप से तालिकाएँ सम्मिलित कर सकते हैं। यह सुविधा आपको अपनी विशिष्ट आवश्यकताओं के अनुसार तालिकाएँ बनाने और अनुकूलित करने की अनुमति देती है।