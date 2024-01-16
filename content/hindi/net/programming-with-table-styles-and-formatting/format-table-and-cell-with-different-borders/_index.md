---
title: विभिन्न सीमाओं के साथ तालिका और सेल को प्रारूपित करें
linktitle: विभिन्न सीमाओं के साथ तालिका और सेल को प्रारूपित करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके विभिन्न सीमाओं के साथ तालिका और सेल को प्रारूपित करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words का उपयोग करके विभिन्न बॉर्डर वाली तालिका और सेल को प्रारूपित करने की चरण-दर-चरण प्रक्रिया के बारे में बताएंगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को समझने और अपनी परियोजनाओं में लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ों में विशिष्ट तालिका और कक्षों पर कस्टम बॉर्डर कैसे लागू करें।

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें
सबसे पहले, आपको अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करना होगा। यह वह स्थान है जहां आप अपने संपादित Word दस्तावेज़ को सहेजना चाहते हैं। "आपकी दस्तावेज़ निर्देशिका" को उचित पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: एक नया दस्तावेज़ और दस्तावेज़ निर्माता बनाएं
 इसके बाद, आपको इसका एक नया उदाहरण बनाना होगा`Document` क्लास और उस दस्तावेज़ के लिए एक दस्तावेज़ निर्माता।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: एक नई तालिका प्रारंभ करें और कक्ष जोड़ें
तालिका बनाना शुरू करने के लिए, हम इसका उपयोग करते हैं`StartTable()` दस्तावेज़ निर्माता की विधि, फिर हम इसका उपयोग करके तालिका में सेल जोड़ते हैं`InsertCell()` विधि और हम इसका उपयोग करके कोशिकाओं की सामग्री लिखते हैं`Writeln()` तरीका।

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// संपूर्ण तालिका के लिए सीमाएँ निर्धारित करें.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// इस सेल के लिए पैडिंग सेट करें.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// दूसरे सेल के लिए एक अलग सेल पैडिंग निर्दिष्ट करें।
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// पिछले ऑपरेशन से सेल फ़ॉर्मेटिंग साफ़ करें।
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// इस पंक्ति में पहली सेल के लिए मोटे बॉर्डर बनाएं। यह अलग होगा
// तालिका के लिए परिभाषित सीमाओं के सापेक्ष।
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder. InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## चरण 4: दस्तावेज़ सहेजें

  संशोधन
अंत में संशोधित दस्तावेज़ को एक फ़ाइल में सहेजें। आप आउटपुट दस्तावेज़ के लिए उपयुक्त नाम और स्थान चुन सकते हैं।

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

बधाई हो! अब आपने .NET के लिए Aspose.Words का उपयोग करके विभिन्न सीमाओं के साथ एक तालिका और एक सेल को स्वरूपित किया है।

### .NET के लिए Aspose.Words का उपयोग करके विभिन्न बॉर्डर्स के साथ फ़ॉर्मेट तालिका और सेल के लिए नमूना स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//संपूर्ण तालिका के लिए सीमाएँ निर्धारित करें.
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	// इस सेल के लिए सेल शेडिंग सेट करें।
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// दूसरे सेल के लिए एक अलग सेल शेडिंग निर्दिष्ट करें।
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	// पिछले ऑपरेशन से सेल फ़ॉर्मेटिंग साफ़ करें।
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	// इस पंक्ति की पहली सेल के लिए बड़े बॉर्डर बनाएं। ये अलग होगा
	// तालिका के लिए निर्धारित सीमाओं की तुलना में।
	builder.CellFormat.Borders.Left.LineWidth = 4.0;
	builder.CellFormat.Borders.Right.LineWidth = 4.0;
	builder.CellFormat.Borders.Top.LineWidth = 4.0;
	builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
	builder.Writeln("Cell #3");
	builder.InsertCell();
	builder.CellFormat.ClearFormatting();
	builder.Writeln("Cell #4");
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके विभिन्न बॉर्डर वाली तालिका और सेल को कैसे प्रारूपित किया जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने Word दस्तावेज़ों में अपनी तालिका और सेल बॉर्डर को आसानी से अनुकूलित कर सकते हैं। Aspose.Words आपके दस्तावेज़ों में तालिकाओं में हेरफेर और फ़ॉर्मेटिंग के लिए एक शक्तिशाली और लचीली API प्रदान करता है। इस ज्ञान से, आप अपने Word दस्तावेज़ों की दृश्य प्रस्तुति में सुधार कर सकते हैं और विशिष्ट आवश्यकताओं को पूरा कर सकते हैं।