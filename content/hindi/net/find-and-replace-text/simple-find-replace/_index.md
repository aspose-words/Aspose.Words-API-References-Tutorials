---
title: वर्ड में सरल टेक्स्ट ढूंढें और बदलें
linktitle: वर्ड में सरल टेक्स्ट ढूंढें और बदलें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में सरल टेक्स्ट ढूँढने और बदलने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/find-and-replace-text/simple-find-replace/
---
इस लेख में, हम .NET लाइब्रेरी के लिए Aspose.Words में सिंपल टेक्स्ट फाइंड एंड रिप्लेस का उपयोग कैसे करें, यह समझने के लिए उपरोक्त C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको वर्णों की एक विशिष्ट स्ट्रिंग की खोज करके और उसे Word दस्तावेज़ में वर्णों की किसी अन्य स्ट्रिंग के साथ प्रतिस्थापित करके सरल पाठ प्रतिस्थापन करने की अनुमति देती है।

## आवश्यक शर्तें

- C# भाषा का बुनियादी ज्ञान।
- Aspose.Words लाइब्रेरी के साथ .NET विकास वातावरण स्थापित।

## चरण 1: एक नया दस्तावेज़ बनाना

 इससे पहले कि हम सरल खोज और प्रतिस्थापन का उपयोग शुरू करें, हमें .NET के लिए Aspose.Words का उपयोग करके एक नया दस्तावेज़ बनाना होगा। इसे इंस्टेंटियेट करके किया जा सकता है`Document` वस्तु:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## चरण 2: दस्तावेज़ में टेक्स्ट डालें

 एक बार हमारे पास दस्तावेज़ हो जाने पर, हम इसका उपयोग करके टेक्स्ट सम्मिलित कर सकते हैं`DocumentBuilder` वस्तु। हमारे उदाहरण में, हम इसका उपयोग करते हैं`Writeln` "हैलो" वाक्यांश सम्मिलित करने की विधि_CustomerName_,":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## चरण 3: सरल पाठ प्रतिस्थापन

 हम उपयोग करते हैं`Range.Replace` सरल पाठ प्रतिस्थापन करने की विधि। हमारे उदाहरण में, हम स्ट्रिंग की सभी घटनाओं को प्रतिस्थापित करते हैं "_ClientName_ "जेम्स बॉन्ड" का उपयोग करते हुए`FindReplaceOptions` के साथ विकल्प`FindReplaceDirection.Forward` खोज दिशा:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## चरण 4: संपादित दस्तावेज़ को सहेजना

अंत में, हम संशोधित दस्तावेज़ को इसका उपयोग करके एक निर्दिष्ट निर्देशिका में सहेजते हैं`Save` तरीका:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके सरल खोज प्रतिस्थापन के लिए उदाहरण स्रोत कोड

यहां सरल खोज के उपयोग को प्रदर्शित करने और .NET के लिए Aspose.Words से बदलने के लिए पूर्ण उदाहरण स्रोत कोड दिया गया है:

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// संशोधित दस्तावेज़ सहेजें
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## निष्कर्ष

इस लेख में, हमने .NET के लिए Aspose.Words के सिंपल फाइंड रिप्लेस फ़ंक्शन का उपयोग करने के तरीके को समझने के लिए C# स्रोत कोड की खोज की। हमने दस्तावेज़ बनाने, टेक्स्ट सम्मिलित करने, सरल टेक्स्ट प्रतिस्थापन करने और संपादित दस्तावेज़ को सहेजने के लिए चरण-दर-चरण मार्गदर्शिका का पालन किया।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में सरल टेक्स्ट ढूँढें और बदलें फ़ंक्शन क्या है?

उ: .NET के लिए Aspose.Words में सरल टेक्स्ट ढूंढें और बदलें सुविधा आपको Word दस्तावेज़ में सरल टेक्स्ट प्रतिस्थापन करने की अनुमति देती है। यह आपको एक विशिष्ट वर्ण स्ट्रिंग की खोज करने और उसे किसी अन्य वर्ण स्ट्रिंग से बदलने की अनुमति देता है। यह तब उपयोगी हो सकता है जब आप किसी दस्तावेज़ में वैश्विक परिवर्तन करना चाहते हैं, जैसे नाम, दिनांक या अन्य जानकारी बदलना।

#### प्रश्न: .NET के लिए Aspose.Words में एक नया दस्तावेज़ कैसे बनाएं?

 उ: सिंपल टेक्स्ट फाइंड एंड रिप्लेस फ़ंक्शन का उपयोग करने से पहले, आपको .NET के लिए Aspose.Words का उपयोग करके एक नया दस्तावेज़ बनाना होगा। इसे इंस्टेंटियेट करके किया जा सकता है`Document` वस्तु। नया दस्तावेज़ बनाने के लिए यहां एक नमूना कोड दिया गया है:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में टेक्स्ट कैसे सम्मिलित करें?

 उ: एक बार जब आपके पास दस्तावेज़ हो जाए, तो आप इसका उपयोग करके टेक्स्ट सम्मिलित कर सकते हैं`DocumentBuilder` वस्तु। हमारे उदाहरण में, हम इसका उपयोग करते हैं`Writeln` "हैलो" वाक्यांश सम्मिलित करने की विधि_CustomerName_:":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_:");
```

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में सरल टेक्स्ट प्रतिस्थापन कैसे करूँ?

 उ: एक साधारण पाठ प्रतिस्थापन करने के लिए, आप इसका उपयोग कर सकते हैं`Range.Replace` तरीका। हमारे उदाहरण में, हम स्ट्रिंग की सभी घटनाओं को प्रतिस्थापित करते हैं "_ClientName_ "जेम्स बॉन्ड" का उपयोग करते हुए`FindReplaceOptions` के साथ विकल्प`FindReplaceDirection.Forward` खोज दिशा:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### प्रश्न: संपादित दस्तावेज़ को .NET के लिए Aspose.Words में कैसे सहेजें?

 उ: एक बार जब आप पाठ प्रतिस्थापन कर लेते हैं, तो आप संशोधित दस्तावेज़ को इसका उपयोग करके एक निर्दिष्ट निर्देशिका में सहेज सकते हैं`Save` तरीका:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```