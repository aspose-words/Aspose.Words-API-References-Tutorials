---
title: शैली से कक्षों और पंक्तियों पर स्वरूपण का विस्तार करें
linktitle: शैली से कक्षों और पंक्तियों पर स्वरूपण का विस्तार करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके तालिका शैली से कक्षों और पंक्तियों में स्वरूपण का विस्तार करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

इस ट्यूटोरियल में, हम आपको Aspose.Words for .NET का उपयोग करके स्टाइल से सेल और पंक्तियों में फ़ॉर्मेटिंग का विस्तार करने की चरण-दर-चरण प्रक्रिया से अवगत कराएँगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको अपने स्वयं के प्रोजेक्ट में इस सुविधा को समझने और लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ों में विशिष्ट सेल और पंक्तियों में टेबल स्टाइल फ़ॉर्मेटिंग कैसे लागू करें।


## चरण 1: दस्तावेज़ निर्देशिका निर्धारित करें
सबसे पहले, आपको अपने दस्तावेज़ निर्देशिका का पथ सेट करना होगा। यह वह जगह है जहाँ आपका Word दस्तावेज़ स्थित है। "आपके दस्तावेज़ निर्देशिका" को उचित पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: मौजूदा दस्तावेज़ लोड करें
 इसके बाद, आपको मौजूदा वर्ड दस्तावेज़ को एक इंस्टेंस में लोड करना होगा`Document` कक्षा।

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## चरण 3: पहली तालिका के पहले सेल पर जाएँ
 शुरू करने के लिए, हमें दस्तावेज़ में पहली तालिका के पहले सेल पर नेविगेट करना होगा। हम इसका उपयोग करते हैं`GetChild()` और`FirstRow.FirstCell` पहले सेल का संदर्भ प्राप्त करने के लिए विधियाँ।

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

## चरण 5: तालिका शैलियों को प्रत्यक्ष स्वरूपण में विस्तारित करें
 अब हम दस्तावेज़ के प्रारूप का उपयोग करके तालिका शैलियों को प्रत्यक्ष स्वरूपण में विस्तारित करते हैं`ExpandTableStylesToDirectFormatting()` तरीका।

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## चरण 6: शैली विस्तार के बाद सेल फ़ॉर्मेटिंग दिखाएँ
अब हम टेबल स्टाइल्स को विस्तृत करने के बाद सेल का बैकग्राउंड रंग प्रदर्शित करते हैं। टेबल स्टाइल से एक नीला बैकग्राउंड रंग लागू किया जाना चाहिए।

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### .NET के लिए Aspose.Words का उपयोग करके सेल और पंक्ति से स्टाइल पर स्वरूपण का विस्तार करने के लिए नमूना स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// दस्तावेज़ में पहली तालिका का पहला कक्ष प्राप्त करें.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// सबसे पहले सेल शेडिंग का रंग प्रिंट करें।
	// यह रिक्त होना चाहिए क्योंकि वर्तमान छायांकन तालिका शैली में संग्रहीत है।
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// अब तालिका शैलियों का विस्तार करने के बाद सेल शेडिंग प्रिंट करें।
	// तालिका शैली से एक नीला पृष्ठभूमि पैटर्न रंग लागू किया जाना चाहिए था।
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके टेबल स्टाइल से सेल और रो में फ़ॉर्मेटिंग का विस्तार कैसे करें। इस चरण-दर-चरण गाइड का पालन करके, आप अपने Word दस्तावेज़ों में विशिष्ट सेल और पंक्तियों में टेबल स्टाइल फ़ॉर्मेटिंग को आसानी से लागू कर सकते हैं। Aspose.Words आपके दस्तावेज़ों में टेबल में हेरफेर और फ़ॉर्मेटिंग के लिए एक शक्तिशाली और लचीला API प्रदान करता है। इस ज्ञान के साथ, आप अपने Word दस्तावेज़ों के लेआउट और प्रस्तुति को और अधिक अनुकूलित कर सकते हैं।