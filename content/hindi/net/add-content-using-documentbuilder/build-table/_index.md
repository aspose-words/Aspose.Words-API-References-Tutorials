---
title: वर्ड डॉक्यूमेंट में टेबल बनाएं
linktitle: वर्ड डॉक्यूमेंट में टेबल बनाएं
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में तालिका बनाना सीखें।
type: docs
weight: 10
url: /hi/net/add-content-using-documentbuilder/build-table/
---
इस चरण-दर-चरण ट्यूटोरियल में, आप सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका कैसे बनाएं। हम प्रक्रिया में आपका मार्गदर्शन करेंगे और आपको आवश्यक C# कोड स्निपेट प्रदान करेंगे। इस गाइड के अंत तक, आप DocumentBuilder क्लास का उपयोग करके कस्टम फ़ॉर्मेटिंग और सामग्री के साथ एक तालिका बनाने में सक्षम होंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- आपके सिस्टम पर .NET लाइब्रेरी के लिए Aspose.Words इंस्टॉल किया गया है।

## चरण 1: एक नया दस्तावेज़ बनाएँ
आरंभ करने के लिए, दस्तावेज़ वर्ग का उपयोग करके एक नया दस्तावेज़ बनाएं:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: तालिका प्रारंभ करें
इसके बाद, तालिका बनाना शुरू करने के लिए दस्तावेज़बिल्डर वर्ग की स्टार्टटेबल विधि का उपयोग करें:

```csharp
Table table = builder.StartTable();
```

## चरण 3: सेल डालें और सामग्री जोड़ें
अब, आप तालिका में सेल सम्मिलित कर सकते हैं और DocumentBuilder क्लास के InsertCell और Write तरीकों का उपयोग करके उनमें सामग्री जोड़ सकते हैं। सेल फ़ॉर्मेटिंग को आवश्यकतानुसार अनुकूलित करें:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## चरण 4: पंक्ति समाप्त करें
पहली पंक्ति की कोशिकाओं में सामग्री जोड़ने के बाद, पंक्ति को समाप्त करने के लिए DocumentBuilder वर्ग की EndRow विधि का उपयोग करें:

```csharp
builder.EndRow();
```

## चरण 5: पंक्ति स्वरूपण को अनुकूलित करें
आप RowFormat और CellFormat ऑब्जेक्ट के गुणों को सेट करके किसी पंक्ति के स्वरूपण को अनुकूलित कर सकते हैं:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## चरण 6: तालिका समाप्त करें
तालिका को पूरा करने के लिए, DocumentBuilder वर्ग की एंडटेबल विधि का उपयोग करें:

```csharp
builder.EndTable();
```

### .NET के लिए Aspose.Words का उपयोग करके तालिका बनाने के लिए उदाहरण स्रोत कोड
.NET के लिए Aspose.Words का उपयोग करके तालिका बनाने का संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## निष्कर्ष
बधाई हो! आपने .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में तालिका बनाना सफलतापूर्वक सीख लिया है। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए स्रोत कोड का उपयोग करके, अब आप कस्टम फ़ॉर्मेटिंग के साथ तालिकाएँ बना सकते हैं।

### वर्ड दस्तावेज़ में बिल्ड टेबल के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words क्या है?

उत्तर: .NET के लिए Aspose.Words एक शक्तिशाली दस्तावेज़ प्रसंस्करण लाइब्रेरी है जो डेवलपर्स को .NET अनुप्रयोगों में Microsoft Word दस्तावेज़ों को प्रोग्रामेटिक रूप से बनाने, पढ़ने, संपादित करने और परिवर्तित करने की अनुमति देता है। यह Word दस्तावेज़ों के साथ काम करने के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है, जैसे कि टेक्स्ट हेरफेर, तालिका निर्माण, दस्तावेज़ सुरक्षा, फ़ॉर्मेटिंग, और बहुत कुछ।

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका कैसे बना सकता हूँ?

उ: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में एक तालिका बनाने के लिए, आप इन चरणों का पालन कर सकते हैं:
1.  का एक नया उदाहरण बनाएं`Document` कक्षा और ए`DocumentBuilder` वस्तु।
2.  उपयोग`StartTable` की विधि`DocumentBuilder`टेबल का निर्माण शुरू करने के लिए कक्षा।
3.  तालिका में सेल डालें और का उपयोग करके सामग्री जोड़ें`InsertCell` और`Write` के तरीके`DocumentBuilder` कक्षा।
4.  का उपयोग करके पंक्ति को समाप्त करें`EndRow` की विधि`DocumentBuilder` कक्षा।
5.  के गुण सेट करके पंक्ति स्वरूपण को अनुकूलित करें`RowFormat` और`CellFormat` वस्तुएं.
6.  का उपयोग करके तालिका को समाप्त करें`EndTable` की विधि`DocumentBuilder` कक्षा।
7. दस्तावेज़ सहेजें.

#### प्रश्न: मैं तालिका और उसके कक्षों के स्वरूपण को कैसे अनुकूलित कर सकता हूं?

 उ: आप विभिन्न गुणों को सेट करके तालिका और उसके कक्षों के स्वरूपण को अनुकूलित कर सकते हैं`RowFormat` और`CellFormat` वस्तुएं. उदाहरण के लिए, आप सेल संरेखण, लंबवत और क्षैतिज टेक्स्ट ओरिएंटेशन, सेल ऊंचाई, पंक्ति ऊंचाई और बहुत कुछ समायोजित कर सकते हैं। इन गुणों का उपयोग करके, आप तालिका और उसकी सामग्री के लिए वांछित स्वरूप प्राप्त कर सकते हैं।

#### प्रश्न: क्या मैं मर्ज की गई कोशिकाओं और अन्य उन्नत सुविधाओं के साथ जटिल तालिकाएँ बना सकता हूँ?

 उत्तर: हाँ, .NET के लिए Aspose.Words जटिल तालिकाएँ बनाने के लिए उन्नत सुविधाएँ प्रदान करता है, जिसमें मर्ज किए गए सेल, नेस्टेड टेबल और जटिल टेबल लेआउट के लिए समर्थन शामिल है। आप इसका उपयोग कर सकते हैं`MergeCells` कोशिकाओं को मर्ज करने की विधि,`StartTable`नेस्टेड तालिकाएँ बनाने की विधि, और वांछित तालिका संरचना प्राप्त करने के लिए अन्य विधियाँ।

#### प्रश्न: क्या .NET के लिए Aspose.Words विभिन्न Word दस्तावेज़ प्रारूपों के साथ संगत है?

उत्तर: हां, .NET के लिए Aspose.Words DOC, DOCX, RTF और अन्य सहित विभिन्न Word दस्तावेज़ प्रारूपों के साथ संगत है। यह लीगेसी प्रारूप (डीओसी) और आधुनिक एक्सएमएल-आधारित प्रारूप (डीओसीएक्स) दोनों का समर्थन करता है और आपको बिना किसी समस्या के विभिन्न प्रारूपों में दस्तावेजों के साथ काम करने की अनुमति देता है।

#### प्रश्न: मुझे .NET के लिए Aspose.Words के लिए अधिक जानकारी और दस्तावेज़ कहां मिल सकते हैं?

 उ: आप व्यापक दस्तावेज़ीकरण और कोड उदाहरण यहां पा सकते हैं[एपीआई संदर्भ](https://reference.aspose.com/words/net/). दस्तावेज़ीकरण लाइब्रेरी की विशेषताओं और उन्हें आपके .NET अनुप्रयोगों में उपयोग करने के तरीके के बारे में विस्तृत जानकारी प्रदान करेगा।