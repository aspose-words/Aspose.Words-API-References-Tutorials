---
title: पसंदीदा चौड़ाई सेटिंग्स
linktitle: पसंदीदा चौड़ाई सेटिंग्स
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में पसंदीदा तालिका सेल चौड़ाई सेट करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/preferred-width-settings/
---

इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में टेबल सेल के लिए पसंदीदा चौड़ाई सेटिंग कैसे सेट करें। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत तक, आप अपने Word दस्तावेज़ों में अपने टेबल सेल के लिए अलग-अलग पसंदीदा चौड़ाई निर्दिष्ट करने में सक्षम होंगे।

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

## चरण 3: पसंदीदा चौड़ाई के साथ तालिका बनाना
इसके बाद, हम तीन सेल वाली एक टेबल बनाएंगे जिनकी चौड़ाई अलग-अलग होगी। निम्नलिखित कोड का उपयोग करें:

```csharp
// तालिका की शुरुआत
builder. StartTable();

// पूर्ण आकार का सेल डालें
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// सापेक्ष आकार का एक सेल डालें (प्रतिशत में)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// स्वतः आकारित सेल सम्मिलित करें
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// तालिका का अंत
builder. EndTable();
```

यहाँ हम तीन सेल वाली एक टेबल बनाने के लिए डॉक्यूमेंट बिल्डर का उपयोग करते हैं। पहले सेल की पसंदीदा चौड़ाई 40 पॉइंट है, दूसरे सेल की पसंदीदा चौड़ाई टेबल की चौड़ाई का 20% है, और तीसरे सेल की एक स्वचालित पसंदीदा चौड़ाई है जो समायोजित होती है

  उपलब्ध स्थान के आधार पर।

## चरण 4: संशोधित दस्तावेज़ को सहेजना
अंत में, हमें संशोधित दस्तावेज़ को तालिका कक्षों के लिए परिभाषित पसंदीदा चौड़ाई सेटिंग्स के साथ सहेजना होगा। निम्नलिखित कोड का उपयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके पसंदीदा चौड़ाई सेटिंग्स के लिए नमूना स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// तीन कक्षों से बनी एक तालिका पंक्ति डालें जिनकी अलग-अलग पसंदीदा चौड़ाई हो।
	builder.StartTable();
	// एक पूर्ण आकार का सेल डालें.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// सापेक्ष (प्रतिशत) आकार का सेल डालें.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// एक स्वतः आकार का सेल डालें.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में टेबल सेल के लिए पसंदीदा चौड़ाई सेटिंग कैसे सेट करें। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और प्रदान किए गए C# कोड को लागू करके, आप अपने Word दस्तावेज़ों में अपनी विशिष्ट आवश्यकताओं के अनुसार अपनी टेबल सेल की चौड़ाई को अनुकूलित कर सकते हैं।