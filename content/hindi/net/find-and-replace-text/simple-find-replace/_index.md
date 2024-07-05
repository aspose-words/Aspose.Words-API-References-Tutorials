---
title: वर्ड में सरल टेक्स्ट खोजें और बदलें
linktitle: वर्ड में सरल टेक्स्ट खोजें और बदलें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में सरल पाठ ढूँढ़ने और बदलने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/find-and-replace-text/simple-find-replace/
---
इस लेख में, हम ऊपर दिए गए C# स्रोत कोड का पता लगाएंगे ताकि यह समझ सकें कि वर्ड में Aspose.Words for .NET लाइब्रेरी में सरल टेक्स्ट ढूँढ़ें और बदलें का उपयोग कैसे करें। यह सुविधा आपको वर्ड दस्तावेज़ में वर्णों की एक विशिष्ट स्ट्रिंग की खोज करके और उसे वर्णों की दूसरी स्ट्रिंग से बदलकर सरल टेक्स्ट प्रतिस्थापन करने की अनुमति देती है।

## आवश्यक शर्तें

- C# भाषा का मूलभूत ज्ञान.
- Aspose.Words लाइब्रेरी के साथ .NET विकास वातावरण स्थापित।

## चरण 1: नया दस्तावेज़ बनाना

 सरल खोज और प्रतिस्थापन का उपयोग शुरू करने से पहले, हमें .NET के लिए Aspose.Words का उपयोग करके एक नया दस्तावेज़ बनाने की आवश्यकता है। यह एक इंस्टेंटिएटिंग द्वारा किया जा सकता है`Document` वस्तु:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## चरण 2: दस्तावेज़ में पाठ डालें

 एक बार जब हमारे पास कोई दस्तावेज़ तैयार हो जाता है, तो हम इसका उपयोग करके पाठ सम्मिलित कर सकते हैं`DocumentBuilder` ऑब्जेक्ट. हमारे उदाहरण में, हम का उपयोग करते हैं`Writeln` "हैलो" वाक्यांश डालने की विधि_CustomerName_,":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## चरण 3: सरल पाठ प्रतिस्थापन

 हम उपयोग करते हैं`Range.Replace` सरल पाठ प्रतिस्थापन करने की विधि। हमारे उदाहरण में, हम स्ट्रिंग की सभी घटनाओं को प्रतिस्थापित करते हैं "_ClientName_ "जेम्स बॉन्ड" का उपयोग करते हुए`FindReplaceOptions` विकल्प के साथ`FindReplaceDirection.Forward` खोज दिशा:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## चरण 4: संपादित दस्तावेज़ को सहेजना

अंत में, हम संशोधित दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजते हैं`Save` तरीका:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके सरल खोज प्रतिस्थापन के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words के साथ सरल खोज और प्रतिस्थापन के उपयोग को प्रदर्शित करने के लिए यहां पूर्ण उदाहरण स्रोत कोड दिया गया है:

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

इस लेख में, हमने .NET के लिए Aspose.Words के सरल खोज प्रतिस्थापन फ़ंक्शन का उपयोग करने के तरीके को समझने के लिए C# स्रोत कोड का पता लगाया। हमने दस्तावेज़ बनाने, टेक्स्ट डालने, सरल टेक्स्ट प्रतिस्थापन करने और संपादित दस्तावेज़ को सहेजने के लिए चरण-दर-चरण मार्गदर्शिका का पालन किया।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में सरल टेक्स्ट खोज और प्रतिस्थापन फ़ंक्शन क्या है?

उत्तर: Aspose.Words for .NET में सरल टेक्स्ट ढूँढ़ें और बदलें सुविधा आपको Word दस्तावेज़ में सरल टेक्स्ट प्रतिस्थापन करने की अनुमति देती है। यह आपको किसी विशिष्ट वर्ण स्ट्रिंग की खोज करने और उसे किसी अन्य वर्ण स्ट्रिंग से बदलने की अनुमति देता है। यह तब उपयोगी हो सकता है जब आप किसी दस्तावेज़ में वैश्विक परिवर्तन करना चाहते हैं, जैसे नाम, तिथियाँ या अन्य जानकारी बदलना।

#### प्रश्न: .NET के लिए Aspose.Words में नया दस्तावेज़ कैसे बनाएं?

 उत्तर: सिंपल टेक्स्ट फाइंड एंड रिप्लेस फंक्शन का उपयोग करने से पहले, आपको .NET के लिए Aspose.Words का उपयोग करके एक नया दस्तावेज़ बनाना होगा। यह एक इंस्टेंटिएट करके किया जा सकता है`Document` ऑब्जेक्ट. नया दस्तावेज़ बनाने के लिए यहाँ एक नमूना कोड है:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में पाठ कैसे सम्मिलित करें?

 उत्तर: एक बार आपके पास एक दस्तावेज़ हो जाने पर, आप इसका उपयोग करके पाठ सम्मिलित कर सकते हैं`DocumentBuilder` ऑब्जेक्ट. हमारे उदाहरण में, हम का उपयोग करते हैं`Writeln` "हैलो" वाक्यांश डालने की विधि_CustomerName_:":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_:");
```

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में सरल पाठ प्रतिस्थापन कैसे करूँ?

 उत्तर: सरल पाठ प्रतिस्थापन करने के लिए, आप इसका उपयोग कर सकते हैं`Range.Replace` विधि। हमारे उदाहरण में, हम स्ट्रिंग की सभी घटनाओं को प्रतिस्थापित करते हैं "_ClientName_ "जेम्स बॉन्ड" का उपयोग करते हुए`FindReplaceOptions` विकल्प के साथ`FindReplaceDirection.Forward` खोज दिशा:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### प्रश्न: .NET के लिए Aspose.Words में संपादित दस्तावेज़ को कैसे सहेजा जाए?

 उत्तर: एक बार जब आप पाठ प्रतिस्थापन कर लेते हैं, तो आप संशोधित दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेज सकते हैं`Save` तरीका:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```