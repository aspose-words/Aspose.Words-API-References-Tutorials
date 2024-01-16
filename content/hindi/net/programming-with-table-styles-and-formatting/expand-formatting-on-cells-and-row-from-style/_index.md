---
title: स्टाइल से सेल और पंक्ति पर फ़ॉर्मेटिंग का विस्तार करें
linktitle: स्टाइल से सेल और पंक्ति पर फ़ॉर्मेटिंग का विस्तार करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके तालिका शैली से कक्षों और पंक्तियों में फ़ॉर्मेटिंग का विस्तार करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words का उपयोग करके एक शैली से कोशिकाओं और पंक्तियों में फ़ॉर्मेटिंग का विस्तार करने की चरण-दर-चरण प्रक्रिया के बारे में बताएंगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को समझने और अपनी परियोजनाओं में लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ों में विशिष्ट कक्षों और पंक्तियों में तालिका शैली स्वरूपण कैसे लागू करें।


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

## चरण 3: पहली तालिका के पहले सेल पर जाएँ
 आरंभ करने के लिए, हमें दस्तावेज़ में पहली तालिका के पहले सेल पर नेविगेट करना होगा। हम उपयोग करते हैं`GetChild()` और`FirstRow.FirstCell` प्रथम सेल का संदर्भ प्राप्त करने की विधियाँ।

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## चरण 4: प्रारंभिक सेल फ़ॉर्मेटिंग दिखाएँ
तालिका की शैलियों का विस्तार करने से पहले, हम सेल का वर्तमान पृष्ठभूमि रंग प्रदर्शित करते हैं। यह खाली होना चाहिए क्योंकि वर्तमान स्वरूपण तालिका की शैली में संग्रहीत है।

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## चरण 5: तालिका शैलियों को प्रत्यक्ष स्वरूपण तक विस्तृत करें
 अब हम दस्तावेज़ का उपयोग करके सीधे फ़ॉर्मेटिंग के लिए तालिका शैलियों का विस्तार करते हैं`ExpandTableStylesToDirectFormatting()` तरीका।

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## चरण 6: शैली विस्तार के बाद सेल फ़ॉर्मेटिंग दिखाएँ
अब हम तालिका शैलियों का विस्तार करने के बाद सेल का पृष्ठभूमि रंग प्रदर्शित करते हैं। तालिका शैली से नीला पृष्ठभूमि रंग लागू किया जाना चाहिए।

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### .NET के लिए Aspose.Words का उपयोग करके स्टाइल से सेल और पंक्ति पर फ़ॉर्मेटिंग का विस्तार करने के लिए नमूना स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// दस्तावेज़ में पहली तालिका का पहला सेल प्राप्त करें।
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// सबसे पहले सेल शेडिंग का रंग प्रिंट करें।
	// यह खाली होना चाहिए क्योंकि वर्तमान शेडिंग तालिका शैली में संग्रहीत है।
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// अब तालिका शैलियों का विस्तार करने के बाद सेल शेडिंग प्रिंट करें।
	// तालिका शैली से नीला पृष्ठभूमि पैटर्न रंग लागू किया जाना चाहिए था।
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके तालिका शैली से कोशिकाओं और पंक्तियों में फ़ॉर्मेटिंग का विस्तार कैसे किया जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने Word दस्तावेज़ों में विशिष्ट कक्षों और पंक्तियों पर तालिका शैली स्वरूपण आसानी से लागू कर सकते हैं। Aspose.Words आपके दस्तावेज़ों में तालिकाओं में हेरफेर और फ़ॉर्मेटिंग के लिए एक शक्तिशाली और लचीली API प्रदान करता है। इस ज्ञान के साथ, आप अपने Word दस्तावेज़ों के लेआउट और प्रस्तुति को और अधिक अनुकूलित कर सकते हैं।