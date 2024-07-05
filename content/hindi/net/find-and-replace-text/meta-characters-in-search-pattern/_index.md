---
title: खोज पैटर्न में मेटा वर्ण
linktitle: खोज पैटर्न में मेटा वर्ण
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: Word दस्तावेज़ों में हेरफेर करने के लिए .NET के लिए Aspose.Words के साथ खोज पैटर्न में मेटाकैरेक्टर का उपयोग करना सीखें।
type: docs
weight: 10
url: /hi/net/find-and-replace-text/meta-characters-in-search-pattern/
---
इस लेख में, हम ऊपर दिए गए C# स्रोत कोड का पता लगाएंगे ताकि यह समझ सकें कि Aspose.Words for .NET लाइब्रेरी में मेटा कैरेक्टर इन सर्च पैटर्न फ़ंक्शन का उपयोग कैसे करें। यह सुविधा आपको Word दस्तावेज़ों में उन्नत खोज और प्रतिस्थापन करने के लिए विशेष मेटाकैरेक्टर का उपयोग करने की अनुमति देती है।

## आवश्यक शर्तें

- C# भाषा का मूलभूत ज्ञान.
- Aspose.Words लाइब्रेरी के साथ .NET विकास वातावरण स्थापित।

## चरण 1: नया दस्तावेज़ बनाना

 खोज पैटर्न में मेटाकैरेक्टर का उपयोग शुरू करने से पहले, हमें .NET के लिए Aspose.Words का उपयोग करके एक नया दस्तावेज़ बनाना होगा। यह एक इंस्टेंटिएट करके किया जा सकता है`Document` वस्तु:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## चरण 2: दस्तावेज़ में पाठ डालें

 एक बार जब हमारे पास कोई दस्तावेज़ तैयार हो जाता है, तो हम इसका उपयोग करके पाठ सम्मिलित कर सकते हैं`DocumentBuilder` ऑब्जेक्ट. हमारे उदाहरण में, हम का उपयोग करते हैं`Writeln` और`Write` पाठ की दो पंक्तियाँ सम्मिलित करने की विधियाँ:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## चरण 3: टेक्स्ट को मेटाकैरेक्टर से ढूंढें और बदलें

 अब हम इसका प्रयोग करेंगे`Range.Replace` विशेष मेटाकैरेक्टर वाले खोज पैटर्न का उपयोग करके टेक्स्ट को खोजने और बदलने के लिए फ़ंक्शन। हमारे उदाहरण में, हम "यह पंक्ति 1 है और यह पंक्ति 2 है" वाक्यांश को "यह पंक्ति बदली गई है" के साथ प्रतिस्थापित करते हैं`&p` पैराग्राफ़ ब्रेक को दर्शाने के लिए मेटाकैरेक्टर:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## चरण 4: दस्तावेज़ में पृष्ठ विराम सम्मिलित करना

 किसी अन्य मेटाकैरेक्टर के उपयोग को स्पष्ट करने के लिए, हम दस्तावेज़ में पृष्ठ विराम डालेंगे`InsertBreak` विधि के साथ`BreakType.PageBreak` पैरामीटर. हम पहले कर्सर को`DocumentBuilder` दस्तावेज़ के अंत में, फिर हम पृष्ठ विराम और पाठ की एक नई पंक्ति सम्मिलित करते हैं:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## चरण 5: किसी अन्य मेटाकैरेक्टर को ढूंढें और उसके साथ प्रतिस्थापित करें

 अब हम एक और खोज करेंगे और इसका उपयोग करके प्रतिस्थापित करेंगे`&m` पृष्ठ विराम को दर्शाने के लिए मेटाकैरेक्टर। हम "यह पंक्ति 1 है&mयह पंक्ति 2 है" वाक्यांश को "पृष्ठ विराम को नए पाठ से प्रतिस्थापित किया गया है" से प्रतिस्थापित करते हैं।

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## चरण 6: संपादित दस्तावेज़ को सहेजना

अंत में, हम संशोधित दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजते हैं`Save` तरीका:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके खोज पैटर्न में मेटा वर्णों के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words के साथ खोज पैटर्न में मेटाकैरेक्टर्स के उपयोग को प्रदर्शित करने के लिए यहां पूर्ण नमूना स्रोत कोड दिया गया है:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## निष्कर्ष

इस लेख में, हमने .NET के लिए Aspose.Words के खोज पैटर्न में मेटाकैरेक्टर का उपयोग करने के तरीके को समझने के लिए C# स्रोत कोड का पता लगाया। हमने एक दस्तावेज़ बनाने, पाठ सम्मिलित करने, विशेष मेटाकैरेक्टर का उपयोग करके खोज और प्रतिस्थापन करने, पृष्ठ विराम सम्मिलित करने और संपादित दस्तावेज़ को सहेजने के लिए चरण-दर-चरण मार्गदर्शिका का पालन किया।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: Aspose.Words for .NET में मेटा कैरेक्टर इन सर्च पैटर्न सुविधा क्या है?

उत्तर: Aspose.Words for .NET में खोज पैटर्न में मेटा कैरेक्टर सुविधा आपको Word दस्तावेज़ों में उन्नत खोज और प्रतिस्थापन करने के लिए विशेष मेटा कैरेक्टर का उपयोग करने की अनुमति देती है। ये मेटाकैरेक्टर आपको अपने खोज पैटर्न में पैराग्राफ़ ब्रेक, सेक्शन ब्रेक, पेज ब्रेक और अन्य विशेष तत्वों का प्रतिनिधित्व करने की अनुमति देते हैं।

#### प्रश्न: .NET के लिए Aspose.Words में नया दस्तावेज़ कैसे बनाएं?

 उत्तर: खोज टेम्पलेट में मेटाकैरेक्टर का उपयोग करने से पहले, आपको .NET के लिए Aspose.Words का उपयोग करके एक नया दस्तावेज़ बनाना होगा। यह एक इंस्टेंटिएट करके किया जा सकता है`Document` ऑब्जेक्ट. नया दस्तावेज़ बनाने के लिए यहाँ एक नमूना कोड है:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में पाठ कैसे सम्मिलित करें?

 उत्तर: एक बार आपके पास एक दस्तावेज़ हो जाने पर, आप इसका उपयोग करके पाठ सम्मिलित कर सकते हैं`DocumentBuilder` ऑब्जेक्ट. हमारे उदाहरण में, हम का उपयोग करते हैं`Writeln` और`Write` पाठ की दो पंक्तियाँ सम्मिलित करने की विधियाँ:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में मेटाकैरेक्टर के साथ टेक्स्ट को कैसे खोजें और बदलें?

 उत्तर: टेक्स्ट को मेटाकैरेक्टर से खोजने और बदलने के लिए, आप इसका उपयोग कर सकते हैं`Range.Replace` विधि। हमारे उदाहरण में, हम वाक्यांश "यह पंक्ति 1 है और यह पंक्ति 2 है" को "यह पंक्ति प्रतिस्थापित की गई है" के साथ प्रतिस्थापित करते हैं`&p` पैराग्राफ़ ब्रेक को दर्शाने के लिए मेटाकैरेक्टर:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में पृष्ठ विराम कैसे सम्मिलित करें?

उत्तर: किसी अन्य मेटाकैरेक्टर के उपयोग को स्पष्ट करने के लिए, हम दस्तावेज़ में एक पृष्ठ विराम डालेंगे।`InsertBreak` विधि के साथ`BreakType.PageBreak` पैरामीटर. हम पहले कर्सर को`DocumentBuilder` दस्तावेज़ के अंत में, फिर हम पृष्ठ विराम और पाठ की एक नई पंक्ति सम्मिलित करते हैं:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### प्रश्न: Aspose.Words for .NET का उपयोग करके किसी दस्तावेज़ में किसी अन्य मेटाकैरेक्टर को कैसे खोजें और प्रतिस्थापित करें?

 उत्तर: अब हम एक और खोज करेंगे और इसका उपयोग करके प्रतिस्थापित करेंगे`&m` पृष्ठ विराम को दर्शाने के लिए मेटाकैरेक्टर। हम "यह पंक्ति 1 है&mयह पंक्ति 2 है" वाक्यांश को "पृष्ठ विराम को नए पाठ से प्रतिस्थापित किया गया है" से प्रतिस्थापित करते हैं।

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### प्रश्न: .NET के लिए Aspose.Words में संपादित दस्तावेज़ को कैसे सहेजा जाए?

 उत्तर: एक बार जब आप दस्तावेज़ में परिवर्तन कर लेते हैं, तो आप इसे निर्दिष्ट निर्देशिका में सहेज सकते हैं`Save` तरीका:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```