---
title: कस्टम XML भाग पर मैप किए गए तालिका दोहराए जाने वाले अनुभाग का निर्माण करना
linktitle: कस्टम XML भाग पर मैप किए गए तालिका दोहराए जाने वाले अनुभाग का निर्माण करना
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में CustomXmlPart पर मैप किए गए दोहराए जाने वाले अनुभाग के साथ एक तालिका बनाने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

यह ट्यूटोरियल प्रदर्शित करता है कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में कस्टम Xml भाग में मैप किए गए दोहराए जाने वाले अनुभाग के साथ एक तालिका कैसे बनाई जाए। दोहराए जाने वाला अनुभाग आपको कस्टम Xml भाग में संग्रहीत XML डेटा के आधार पर पंक्तियों को गतिशील रूप से जोड़ने की अनुमति देता है।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए आपके पास निम्नलिखित चीजें होनी चाहिए:

- Aspose.Words for .NET लाइब्रेरी स्थापित की गई।
- C# और वर्ड दस्तावेजों के साथ वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपने दस्तावेज़ निर्देशिका का पथ सेट करके आरंभ करें।`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहाँ आप दस्तावेज़ को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ और दस्तावेज़बिल्डर बनाएँ
 एक नया उदाहरण बनाएँ`Document` कक्षा और एक`DocumentBuilder` दस्तावेज़ की सामग्री बनाने के लिए.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: CustomXmlPart में कस्टम XML डेटा जोड़ें
 एक बनाने के`CustomXmlPart` और इसमें कस्टम XML डेटा जोड़ें। इस उदाहरण में, हम पुस्तकों के संग्रह को उनके शीर्षकों और लेखकों के साथ दर्शाने वाली XML स्ट्रिंग बनाते हैं।

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## चरण 4: एक तालिका और तालिका संरचना बनाएँ
का उपयोग करके तालिका बनाना प्रारंभ करें`StartTable` की विधि`DocumentBuilder` . का उपयोग करके तालिका कक्ष और सामग्री जोड़ें`InsertCell`और`Write` तरीके.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## चरण 5: कस्टम XML से मैप किया गया दोहराए जाने वाला अनुभाग बनाएँ
 एक बनाने के`StructuredDocumentTag` साथ`SdtType.RepeatingSection` दोहराए जाने वाले अनुभाग का प्रतिनिधित्व करने के लिए। दोहराए जाने वाले अनुभाग के लिए XML मैपिंग सेट करें`SetMapping` की विधि`XmlMapping` संपत्ति। इस उदाहरण में, हम दोहराए जाने वाले अनुभाग को मैप करते हैं`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## चरण 6: दोहराए जाने वाले अनुभाग आइटम बनाएं और सेल जोड़ें
 एक बनाने के`StructuredDocumentTag` साथ`SdtType.RepeatingSectionItem` दोहराए जाने वाले अनुभाग आइटम को दर्शाने के लिए। इसे दोहराए जाने वाले अनुभाग में चाइल्ड के रूप में जोड़ें।

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 एक बनाने के`Row` दोहराए जाने वाले अनुभाग में प्रत्येक आइटम का प्रतिनिधित्व करने और उसे दोहराए जाने वाले अनुभाग आइटम में जोड़ने के लिए।

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## चरण 7: दोहराए जाने वाले अनुभाग में सामग्री नियंत्रण जोड़ें
 बनाएं`StructuredDocumentTag` वस्तुओं के साथ`SdtType.PlainText`

  शीर्षक और लेखक सामग्री नियंत्रणों का प्रतिनिधित्व करने के लिए। प्रत्येक सामग्री नियंत्रण के लिए XML मैपिंग सेट करें`SetMapping` की विधि`XmlMapping` प्रॉपर्टी। इस उदाहरण में, हम शीर्षक नियंत्रण को मैप करते हैं`/books[1]/book[1]/title[1]` और लेखक का नियंत्रण`/books[1]/book[1]/author[1]`.

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
 संशोधित दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save`विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके कस्टम XML भाग में मैप किए गए तालिका दोहराए जाने वाले अनुभाग बनाने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
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

बस! आपने अपने Word दस्तावेज़ में Aspose.Words for .NET का उपयोग करके CustomXmlPart पर मैप किए गए दोहराए जाने वाले अनुभाग के साथ सफलतापूर्वक एक तालिका बना ली है।