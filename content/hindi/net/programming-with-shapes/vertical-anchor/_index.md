---
title: लंबवत एंकर
linktitle: लंबवत एंकर
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words में वर्टिकल एंकर सुविधा का उपयोग करके किसी दस्तावेज़ के भीतर किसी आकृति को लंबवत रूप से रखने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-shapes/vertical-anchor/
---

यह ट्यूटोरियल बताता है कि किसी दस्तावेज़ के भीतर किसी आकृति को लंबवत स्थिति में लाने के लिए .NET के लिए Aspose.Words में वर्टिकल एंकर सुविधा का उपयोग कैसे करें। किसी आकृति के ऊर्ध्वाधर एंकर गुण को सेट करके, आप पाठ या पृष्ठ के सापेक्ष उसके ऊर्ध्वाधर संरेखण को नियंत्रित कर सकते हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, आपके पास निम्नलिखित होना चाहिए:

- .NET लाइब्रेरी के लिए Aspose.Words स्थापित।
- वर्ड दस्तावेजों के साथ सी# और वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करके प्रारंभ करें। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आप दस्तावेज़ को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक नया दस्तावेज़ और दस्तावेज़बिल्डर बनाएँ
 का एक नया उदाहरण बनाएं`Document` कक्षा और ए`DocumentBuilder` दस्तावेज़ के साथ काम करने पर आपत्ति।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: एक आकृति डालें और कॉन्फ़िगर करें
 का उपयोग करके दस्तावेज़ में एक आकृति सम्मिलित करें`InsertShape` की विधि`DocumentBuilder` वस्तु। आकृति के लिए वांछित आयाम सेट करें.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## चरण 4: वर्टिकल एंकर सेट करें
आकृति के ऊर्ध्वाधर संरेखण को नियंत्रित करने के लिए उसके ऊर्ध्वाधर एंकर गुण को सेट करें। इस उदाहरण में, हम टेक्स्ट या पेज के नीचे आकृति को एंकर करने के लिए इसे "बॉटम" पर सेट करते हैं।

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## चरण 5: आकृति में सामग्री जोड़ें
 उपयोग`MoveTo` की विधि`DocumentBuilder` कर्सर को आकृति के पहले पैराग्राफ पर ले जाने के लिए ऑब्जेक्ट। फिर, का उपयोग करें`Write` आकृति में सामग्री जोड़ने की विधि.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## चरण 6: दस्तावेज़ सहेजें
 का उपयोग करके दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save`तरीका। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithShapes.VerticalAnchor.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके वर्टिकल एंकर के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

इतना ही! आपने किसी दस्तावेज़ के भीतर किसी आकृति को लंबवत स्थिति में रखने के लिए .NET के लिए Aspose.Words में वर्टिकल एंकर सुविधा का सफलतापूर्वक उपयोग किया है।