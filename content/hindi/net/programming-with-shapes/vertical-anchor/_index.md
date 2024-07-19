---
title: वर्टिकल एंकर
linktitle: वर्टिकल एंकर
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: Aspose.Words for .NET में वर्टिकल एंकर सुविधा का उपयोग करके दस्तावेज़ के भीतर किसी आकृति को लंबवत रूप से रखना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-shapes/vertical-anchor/
---

यह ट्यूटोरियल बताता है कि दस्तावेज़ के भीतर किसी आकृति को लंबवत रूप से रखने के लिए Aspose.Words for .NET में वर्टिकल एंकर सुविधा का उपयोग कैसे करें। किसी आकृति की वर्टिकल एंकर प्रॉपर्टी सेट करके, आप टेक्स्ट या पेज के सापेक्ष उसके वर्टिकल अलाइनमेंट को नियंत्रित कर सकते हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए आपके पास निम्नलिखित चीजें होनी चाहिए:

- Aspose.Words for .NET लाइब्रेरी स्थापित की गई।
- C# और वर्ड दस्तावेजों के साथ वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपने दस्तावेज़ निर्देशिका का पथ सेट करके प्रारंभ करें।`"YOUR DOCUMENT DIRECTORY"`उस निर्देशिका का वास्तविक पथ जहाँ आप दस्तावेज़ को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: नया दस्तावेज़ और दस्तावेज़बिल्डर बनाएँ
 एक नया उदाहरण बनाएँ`Document` कक्षा और एक`DocumentBuilder` दस्तावेज़ के साथ काम करने पर आपत्ति।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: आकृति सम्मिलित करें और कॉन्फ़िगर करें
 दस्तावेज़ में आकृति सम्मिलित करने के लिए निम्न का उपयोग करें:`InsertShape` की विधि`DocumentBuilder` ऑब्जेक्ट. आकृति के लिए वांछित आयाम सेट करें.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## चरण 4: वर्टिकल एंकर सेट करें
आकृति के ऊर्ध्वाधर संरेखण को नियंत्रित करने के लिए उसके ऊर्ध्वाधर एंकर गुण को सेट करें। इस उदाहरण में, हमने आकृति को टेक्स्ट या पृष्ठ के निचले भाग में एंकर करने के लिए इसे "नीचे" पर सेट किया है।

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## चरण 5: आकृति में सामग्री जोड़ें
 उपयोग`MoveTo` की विधि`DocumentBuilder` कर्सर को आकृति के पहले पैराग्राफ़ पर ले जाने के लिए ऑब्जेक्ट का उपयोग करें। फिर, का उपयोग करें`Write` आकृति में सामग्री जोड़ने की विधि.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## चरण 6: दस्तावेज़ सहेजें
 दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save`विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithShapes.VerticalAnchor.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके वर्टिकल एंकर के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

बस! आपने दस्तावेज़ के भीतर किसी आकृति को लंबवत रूप से रखने के लिए Aspose.Words for .NET में वर्टिकल एंकर सुविधा का सफलतापूर्वक उपयोग किया है।