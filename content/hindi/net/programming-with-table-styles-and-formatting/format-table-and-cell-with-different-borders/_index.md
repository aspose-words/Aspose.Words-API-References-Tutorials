---
title: टेबल और सेल को अलग-अलग बॉर्डर के साथ फ़ॉर्मेट करें
linktitle: टेबल और सेल को अलग-अलग बॉर्डर के साथ फ़ॉर्मेट करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके विभिन्न सीमाओं के साथ तालिका और सेल को प्रारूपित करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

इस ट्यूटोरियल में, हम आपको Aspose.Words for .NET का उपयोग करके अलग-अलग बॉर्डर वाली टेबल और सेल को फ़ॉर्मेट करने की चरण-दर-चरण प्रक्रिया से अवगत कराएँगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को अपने प्रोजेक्ट में समझने और लागू करने में मदद करने के लिए एक व्यापक गाइड प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ों में विशिष्ट टेबल और सेल पर कस्टम बॉर्डर कैसे लागू करें।

## चरण 1: दस्तावेज़ निर्देशिका निर्धारित करें
सबसे पहले, आपको अपने दस्तावेज़ निर्देशिका का पथ सेट करना होगा। यह वह स्थान है जहाँ आप अपना संपादित Word दस्तावेज़ सहेजना चाहते हैं। "आपके दस्तावेज़ निर्देशिका" को उचित पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: नया दस्तावेज़ और दस्तावेज़ निर्माता बनाएँ
 इसके बाद, आपको एक नया उदाहरण बनाना होगा`Document` क्लास और उस दस्तावेज़ के लिए एक दस्तावेज़ निर्माता।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: एक नई तालिका शुरू करें और कक्ष जोड़ें
तालिका बनाना शुरू करने के लिए, हम उपयोग करते हैं`StartTable()` दस्तावेज़ बिल्डर की विधि, फिर हम तालिका में कोशिकाओं को जोड़ते हैं`InsertCell()` विधि और हम कोशिकाओं की सामग्री को का उपयोग करके लिखते हैं`Writeln()` तरीका।

```csharp
Table table = builder. StartTable();
builder.InsertCell();
// संपूर्ण तालिका के लिए सीमाएं निर्धारित करें.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// इस सेल के लिए पैडिंग सेट करें.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
// दूसरे सेल के लिए भिन्न सेल पैडिंग निर्दिष्ट करें.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
// पिछले ऑपरेशन से सेल फ़ॉर्मेटिंग साफ़ करें.
builder.CellFormat.ClearFormatting();
builder.InsertCell();
// इस पंक्ति में पहले सेल के लिए मोटी बॉर्डर बनाएं। यह अलग होगा
// तालिका के लिए परिभाषित सीमाओं के सापेक्ष.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## चरण 4: दस्तावेज़ सहेजें

  संशोधन
अंत में संशोधित दस्तावेज़ को फ़ाइल में सहेजें। आप आउटपुट दस्तावेज़ के लिए उपयुक्त नाम और स्थान चुन सकते हैं।

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

बधाई हो! आपने अब Aspose.Words for .NET का उपयोग करके एक तालिका और एक सेल को अलग-अलग सीमाओं के साथ स्वरूपित किया है।

### .NET के लिए Aspose.Words का उपयोग करके टेबल और सेल को अलग-अलग बॉर्डर के साथ प्रारूपित करने के लिए नमूना स्रोत कोड 

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();
builder.InsertCell();
//संपूर्ण तालिका के लिए सीमाएं निर्धारित करें.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// इस सेल के लिए सेल शेडिंग सेट करें.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
// दूसरे सेल के लिए भिन्न सेल शेडिंग निर्दिष्ट करें.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
// पिछले ऑपरेशन से सेल फ़ॉर्मेटिंग साफ़ करें.
builder.CellFormat.ClearFormatting();
builder.InsertCell();
// इस पंक्ति के पहले सेल के लिए बड़ी बॉर्डर बनाएं। यह अलग होगा
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
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी टेबल और सेल को अलग-अलग बॉर्डर के साथ कैसे फ़ॉर्मेट किया जाए। इस चरण-दर-चरण गाइड का पालन करके, आप अपने Word दस्तावेज़ों में अपनी टेबल और सेल बॉर्डर को आसानी से कस्टमाइज़ कर सकते हैं। Aspose.Words आपके दस्तावेज़ों में टेबल को मैनिपुलेट करने और फ़ॉर्मेट करने के लिए एक शक्तिशाली और लचीला API प्रदान करता है। इस ज्ञान के साथ, आप अपने Word दस्तावेज़ों की विज़ुअल प्रस्तुति को बेहतर बना सकते हैं और विशिष्ट आवश्यकताओं को पूरा कर सकते हैं।