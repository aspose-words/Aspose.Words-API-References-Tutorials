---
title: कस्टम XML भाग में मैप किया गया तालिका दोहराव अनुभाग बनाना
linktitle: कस्टम XML भाग में मैप किया गया तालिका दोहराव अनुभाग बनाना
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में CustomXmlPart पर मैप किए गए दोहराए जाने वाले अनुभाग के साथ एक तालिका बनाना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

यह ट्यूटोरियल दर्शाता है कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में कस्टम Xml भाग में मैप किए गए दोहराए जाने वाले अनुभाग के साथ एक तालिका कैसे बनाई जाए। दोहराव अनुभाग आपको कस्टम XML भाग में संग्रहीत XML डेटा के आधार पर गतिशील रूप से पंक्तियाँ जोड़ने की अनुमति देता है।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, आपके पास निम्नलिखित होना चाहिए:

- .NET लाइब्रेरी के लिए Aspose.Words स्थापित।
- वर्ड दस्तावेजों के साथ सी# और वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करके प्रारंभ करें। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आप दस्तावेज़ को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक दस्तावेज़ और दस्तावेज़बिल्डर बनाएँ
 का एक नया उदाहरण बनाएं`Document` कक्षा और ए`DocumentBuilder` दस्तावेज़ की सामग्री बनाने के लिए.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: कस्टम XML डेटा को CustomXmlPart में जोड़ें
 एक बनाने के`CustomXmlPart` और इसमें कस्टम XML डेटा जोड़ें। इस उदाहरण में, हम एक XML स्ट्रिंग बनाते हैं जो पुस्तकों के संग्रह को उनके शीर्षकों और लेखकों के साथ दर्शाती है।

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## चरण 4: एक टेबल और टेबल संरचना बनाएं
 का उपयोग करके एक तालिका बनाना प्रारंभ करें`StartTable` की विधि`DocumentBuilder` . का उपयोग करके तालिका कक्ष और सामग्री जोड़ें`InsertCell` और`Write` तरीके.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## चरण 5: कस्टम XML पर मैप किया गया दोहराव अनुभाग बनाएं
 एक बनाने के`StructuredDocumentTag` साथ`SdtType.RepeatingSection` दोहराए जाने वाले अनुभाग का प्रतिनिधित्व करने के लिए। का उपयोग करके दोहराए जाने वाले अनुभाग के लिए XML मैपिंग सेट करें`SetMapping` की विधि`XmlMapping` संपत्ति। इस उदाहरण में, हम दोहराए जाने वाले अनुभाग को मैप करते हैं`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## चरण 6: दोहराव अनुभाग आइटम बनाएं और सेल जोड़ें
 एक बनाने के`StructuredDocumentTag` साथ`SdtType.RepeatingSectionItem` दोहराए जाने वाले अनुभाग आइटम का प्रतिनिधित्व करने के लिए। इसे दोहराए जाने वाले अनुभाग में एक बच्चे के रूप में जोड़ें।

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 एक बनाने के`Row`दोहराए जाने वाले अनुभाग में प्रत्येक आइटम का प्रतिनिधित्व करना और इसे दोहराए जाने वाले अनुभाग आइटम में जोड़ना।

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## चरण 7: दोहराव अनुभाग के भीतर सामग्री नियंत्रण जोड़ें
 बनाएं`StructuredDocumentTag` वस्तुओं के साथ`SdtType.PlainText`

  शीर्षक और लेखक सामग्री नियंत्रण का प्रतिनिधित्व करने के लिए। का उपयोग करके प्रत्येक सामग्री नियंत्रण के लिए XML मैपिंग सेट करें`SetMapping` की विधि`XmlMapping` संपत्ति। इस उदाहरण में, हम शीर्षक नियंत्रण को मैप करते हैं`/books[1]/book[1]/title[1]` और लेखक का नियंत्रण`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## चरण 8: दस्तावेज़ सहेजें
 का उपयोग करके संशोधित दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` तरीका। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके कस्टम Xml पार्ट में मैप किए गए टेबल रिपीटिंग सेक्शन बनाने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ में CustomXmlPart पर मैप किए गए दोहराए जाने वाले अनुभाग के साथ सफलतापूर्वक एक तालिका बनाई है।