---
title: पंक्ति स्वरूपण संशोधित करें
linktitle: पंक्ति स्वरूपण संशोधित करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके तालिका पंक्ति स्वरूपण को बदलने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words का उपयोग करके तालिका पंक्ति के स्वरूपण को बदलने की चरण-दर-चरण प्रक्रिया के बारे में बताएंगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को समझने और अपनी परियोजनाओं में लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ों में तालिका पंक्ति की सीमाएँ, ऊँचाई और लाइन ब्रेक कैसे बदलें।

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें
सबसे पहले, आपको अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करना होगा। यह वह जगह है जहां आपका Word दस्तावेज़ स्थित है। "आपकी दस्तावेज़ निर्देशिका" को उचित पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: मौजूदा दस्तावेज़ लोड करें
 इसके बाद, आपको मौजूदा वर्ड दस्तावेज़ को एक उदाहरण में लोड करना होगा`Document` कक्षा।

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## चरण 3: संशोधित करने के लिए लाइन तक पहुंचें
 तालिका पंक्ति के स्वरूपण को बदलने के लिए, हमें तालिका में विशिष्ट पंक्ति पर नेविगेट करना होगा। हम उपयोग करते हैं`GetChild()` और`FirstRow` तालिका की पहली पंक्ति का संदर्भ प्राप्त करने की विधियाँ।

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## चरण 4: पंक्ति स्वरूपण बदलें
 अब हम के गुणों का उपयोग करके पंक्ति स्वरूपण को बदल सकते हैं`RowFormat` कक्षा। उदाहरण के लिए, हम लाइन बॉर्डर हटा सकते हैं, ऑटो ऊंचाई सेट कर सकते हैं और लाइन ब्रेक की अनुमति दे सकते हैं।

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### .NET के लिए Aspose.Words का उपयोग करके पंक्ति स्वरूपण को संशोधित करने के लिए नमूना स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// तालिका में पहली पंक्ति पुनः प्राप्त करें.
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके तालिका पंक्ति के स्वरूपण को कैसे बदला जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने Word दस्तावेज़ों में अपनी तालिकाओं में पंक्तियों की सीमाओं, ऊँचाई और पंक्ति विराम को आसानी से समायोजित कर सकते हैं। Aspose.Words आपके दस्तावेज़ों में तालिकाओं में हेरफेर और फ़ॉर्मेटिंग के लिए एक शक्तिशाली और लचीली API प्रदान करता है। इस ज्ञान के साथ, आप अपनी तालिकाओं के विज़ुअल लेआउट को अपनी विशिष्ट आवश्यकताओं के अनुसार अनुकूलित कर सकते हैं।