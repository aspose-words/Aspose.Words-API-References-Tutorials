---
title: खोज पैटर्न में मेटा वर्ण
linktitle: खोज पैटर्न में मेटा वर्ण
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: Word दस्तावेज़ों में हेरफेर करने के लिए .NET के लिए Aspose.Words के साथ खोज पैटर्न में मेटाकैरेक्टर का उपयोग करना सीखें।
type: docs
weight: 10
url: /hi/net/find-and-replace-text/meta-characters-in-search-pattern/
---
इस लेख में, हम .NET लाइब्रेरी के लिए Aspose.Words में खोज पैटर्न फ़ंक्शन में मेटा कैरेक्टर का उपयोग करने के तरीके को समझने के लिए उपरोक्त C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको Word दस्तावेज़ों में उन्नत खोज और प्रतिस्थापन करने के लिए विशेष मेटाअक्षरों का उपयोग करने की अनुमति देती है।

## आवश्यक शर्तें

- C# भाषा का बुनियादी ज्ञान।
- Aspose.Words लाइब्रेरी के साथ .NET विकास वातावरण स्थापित।

## चरण 1: एक नया दस्तावेज़ बनाना

 इससे पहले कि हम खोज पैटर्न में मेटाएक्टर का उपयोग शुरू करें, हमें .NET के लिए Aspose.Words का उपयोग करके एक नया दस्तावेज़ बनाना होगा। इसे इंस्टेंटियेट करके किया जा सकता है`Document` वस्तु:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## चरण 2: दस्तावेज़ में टेक्स्ट डालें

 एक बार हमारे पास दस्तावेज़ हो जाने पर, हम इसका उपयोग करके टेक्स्ट सम्मिलित कर सकते हैं`DocumentBuilder` वस्तु। हमारे उदाहरण में, हम इसका उपयोग करते हैं`Writeln` और`Write` पाठ की दो पंक्तियाँ सम्मिलित करने की विधियाँ:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## चरण 3: टेक्स्ट को मेटाकैरेक्टर से ढूंढें और बदलें

 अब हम इसका प्रयोग करेंगे`Range.Replace` विशेष मेटाअक्षरों वाले खोज पैटर्न का उपयोग करके पाठ को खोजने और बदलने का कार्य। हमारे उदाहरण में, हम वाक्यांश "यह पंक्ति 1 है और यह पंक्ति 2 है" को "यह पंक्ति प्रतिस्थापित की गई है" से प्रतिस्थापित करते हैं।`&p` पैराग्राफ़ ब्रेक का प्रतिनिधित्व करने के लिए मेटाकैरेक्टर:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## चरण 4: दस्तावेज़ में एक पृष्ठ विराम सम्मिलित करना

 किसी अन्य मेटाकैरेक्टर के उपयोग को स्पष्ट करने के लिए, हम इसका उपयोग करके दस्तावेज़ में एक पेज ब्रेक डालेंगे`InsertBreak` विधि के साथ`BreakType.PageBreak` पैरामीटर. हम सबसे पहले कर्सर को से हटाते हैं`DocumentBuilder` दस्तावेज़ के अंत में, फिर हम पृष्ठ विराम और पाठ की एक नई पंक्ति सम्मिलित करते हैं:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## चरण 5: किसी अन्य मेटाकैरेक्टर को ढूंढें और बदलें

 अब हम एक और खोज करेंगे और इसका उपयोग करके प्रतिस्थापित करेंगे`&m` पेज ब्रेक का प्रतिनिधित्व करने के लिए मेटाकैरेक्टर। हम वाक्यांश "यह पंक्ति 1&mयह पंक्ति 2 है" को "पेज ब्रेक को नए टेक्स्ट से बदल दिया गया है" से बदल देते हैं। :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## चरण 6: संपादित दस्तावेज़ को सहेजना

अंत में, हम संशोधित दस्तावेज़ को इसका उपयोग करके एक निर्दिष्ट निर्देशिका में सहेजते हैं`Save` तरीका:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके खोज पैटर्न में मेटा वर्णों के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words के साथ खोज पैटर्न में मेटाकैरेक्टर के उपयोग को प्रदर्शित करने के लिए यहां पूर्ण नमूना स्रोत कोड दिया गया है:

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

इस लेख में, हमने .NET के लिए Aspose.Words के खोज पैटर्न में मेटाकैरेक्टर का उपयोग करने के तरीके को समझने के लिए C# स्रोत कोड की खोज की। हमने दस्तावेज़ बनाने, टेक्स्ट डालने, खोज करने और विशेष मेटाचैक्टर का उपयोग करके बदलने, पेज ब्रेक डालने और संपादित दस्तावेज़ को सहेजने के लिए चरण-दर-चरण मार्गदर्शिका का पालन किया।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में मेटा कैरेक्टर्स इन सर्च पैटर्न फीचर क्या है?

उत्तर: .NET के लिए Aspose.Words में खोज पैटर्न में मेटा वर्ण सुविधा आपको Word दस्तावेज़ों में उन्नत खोज और प्रतिस्थापन करने के लिए विशेष मेटा वर्णों का उपयोग करने की अनुमति देती है। ये मेटाएक्टर आपको अपने खोज पैटर्न में पैराग्राफ ब्रेक, सेक्शन ब्रेक, पेज ब्रेक और अन्य विशेष तत्वों का प्रतिनिधित्व करने की अनुमति देते हैं।

#### प्रश्न: .NET के लिए Aspose.Words में एक नया दस्तावेज़ कैसे बनाएं?

 उ: खोज टेम्प्लेट में मेटाकैरेक्टर का उपयोग करने से पहले, आपको .NET के लिए Aspose.Words का उपयोग करके एक नया दस्तावेज़ बनाना होगा। इसे इंस्टेंटियेट करके किया जा सकता है`Document` वस्तु। नया दस्तावेज़ बनाने के लिए यहां एक नमूना कोड दिया गया है:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में टेक्स्ट कैसे सम्मिलित करें?

 उ: एक बार जब आपके पास दस्तावेज़ हो जाए, तो आप इसका उपयोग करके टेक्स्ट सम्मिलित कर सकते हैं`DocumentBuilder` वस्तु। हमारे उदाहरण में, हम इसका उपयोग करते हैं`Writeln` और`Write` पाठ की दो पंक्तियाँ सम्मिलित करने की विधियाँ:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में टेक्स्ट को मेटाकैरेक्टर से कैसे खोजें और बदलें?

 उ: टेक्स्ट को मेटाकैरेक्टर से खोजने और बदलने के लिए, आप इसका उपयोग कर सकते हैं`Range.Replace` तरीका। हमारे उदाहरण में, हम वाक्यांश "यह पंक्ति 1 है और यह पंक्ति 2 है" को "यह पंक्ति प्रतिस्थापित की गई है" से प्रतिस्थापित करते हैं।`&p` पैराग्राफ़ ब्रेक का प्रतिनिधित्व करने के लिए मेटाकैरेक्टर:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में पेज ब्रेक कैसे डालें?

उ: किसी अन्य मेटाकैरेक्टर के उपयोग को स्पष्ट करने के लिए, हम इसका उपयोग करके दस्तावेज़ में एक पेज ब्रेक डालेंगे`InsertBreak` विधि के साथ`BreakType.PageBreak` पैरामीटर. हम सबसे पहले कर्सर को से हटाते हैं`DocumentBuilder` दस्तावेज़ के अंत में, फिर हम पृष्ठ विराम और पाठ की एक नई पंक्ति सम्मिलित करते हैं:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में किसी अन्य मेटाकैरेक्टर को कैसे खोजें और बदलें?

 उ: अब हम एक और खोज करेंगे और इसका उपयोग करके प्रतिस्थापित करेंगे`&m` पेज ब्रेक का प्रतिनिधित्व करने के लिए मेटाकैरेक्टर। हम वाक्यांश "यह पंक्ति 1&mयह पंक्ति 2 है" को "पेज ब्रेक को नए टेक्स्ट से बदल दिया गया है" से बदल देते हैं। :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### प्रश्न: संपादित दस्तावेज़ को .NET के लिए Aspose.Words में कैसे सहेजें?

 उ: एक बार जब आप दस्तावेज़ में परिवर्तन कर लेते हैं, तो आप इसका उपयोग करके इसे एक निर्दिष्ट निर्देशिका में सहेज सकते हैं`Save` तरीका:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```