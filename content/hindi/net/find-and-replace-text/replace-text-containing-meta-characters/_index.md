---
title: वर्ड मेटा कैरेक्टर वाले टेक्स्ट को बदलें
linktitle: वर्ड मेटा कैरेक्टर वाले टेक्स्ट को बदलें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में मेटाकैरेक्टर युक्त टेक्स्ट को प्रतिस्थापित करना सीखें।
type: docs
weight: 10
url: /hi/net/find-and-replace-text/replace-text-containing-meta-characters/
---
इस लेख में, हम ऊपर दिए गए C# स्रोत कोड का पता लगाएंगे ताकि यह समझ सकें कि Aspose.Words for .NET लाइब्रेरी में Word Replace Text Containing Meta Characters फ़ंक्शन का उपयोग कैसे करें। यह सुविधा आपको किसी दस्तावेज़ में टेक्स्ट के उन हिस्सों को बदलने की अनुमति देती है जिसमें विशिष्ट मेटा-वर्ण होते हैं।

## आवश्यक शर्तें

- C# भाषा का मूलभूत ज्ञान.
- Aspose.Words लाइब्रेरी के साथ .NET विकास वातावरण स्थापित।

## चरण 1: नया दस्तावेज़ बनाना

 मेटाकैरेक्टर टेक्स्ट रिप्लेसमेंट का उपयोग शुरू करने से पहले, हमें .NET के लिए Aspose.Words का उपयोग करके एक नया दस्तावेज़ बनाना होगा। यह एक इंस्टेंटिएट करके किया जा सकता है`Document` वस्तु:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## चरण 2: दस्तावेज़ में पाठ डालें

 एक बार जब हमारे पास कोई दस्तावेज़ तैयार हो जाता है, तो हम इसका उपयोग करके पाठ सम्मिलित कर सकते हैं`DocumentBuilder` ऑब्जेक्ट. हमारे उदाहरण में, हम का उपयोग करते हैं`Writeln` विभिन्न अनुभागों में पाठ के कई पैराग्राफ सम्मिलित करने की विधि:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder. Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

## चरण 3: खोजें और बदलें विकल्प कॉन्फ़िगर करना

 अब हम एक का उपयोग करके खोज और प्रतिस्थापन विकल्पों को कॉन्फ़िगर करेंगे`FindReplaceOptions` ऑब्जेक्ट। हमारे उदाहरण में, हमने प्रतिस्थापित पैराग्राफ़ के संरेखण को "केंद्रित" पर सेट किया है:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

## चरण 4: मेटाकैरेक्टर युक्त पाठ को प्रतिस्थापित करना

 हम उपयोग करते हैं`Range.Replace`मेटाकैरेक्टर वाले टेक्स्ट को बदलने की विधि। हमारे उदाहरण में, हम "सेक्शन" शब्द के प्रत्येक आने के बाद पैराग्राफ़ ब्रेक को उसी शब्द से बदल देते हैं, जिसके बाद कई डैश और एक नया पैराग्राफ़ ब्रेक होता है:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## चरण 5: कस्टम टेक्स्ट टैग को बदलना

 हम इसका भी उपयोग करते हैं`Range.Replace` कस्टम को प्रतिस्थापित करने की विधि "{insert-section}" टेक्स्ट टैग को सेक्शन ब्रेक से बदलें। हमारे उदाहरण में, हम " को प्रतिस्थापित करते हैं{insert-section}"&b" के साथ अनुभाग विराम सम्मिलित करने के लिए:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## चरण 6: संपादित दस्तावेज़ को सहेजना

अंत में, हम संशोधित दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजते हैं`Save` तरीका:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके मेटा वर्णों वाले टेक्स्ट को बदलने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words के साथ मेटाकैरेक्टर युक्त पाठ प्रतिस्थापन के उपयोग को प्रदर्शित करने के लिए यहां पूर्ण उदाहरण स्रोत कोड दिया गया है:

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Font.Name = "Arial";
	builder.Writeln("First section");
	builder.Writeln("  1st paragraph");
	builder.Writeln("  2nd paragraph");
	builder.Writeln("{insert-section}");
	builder.Writeln("Second section");
	builder.Writeln("  1st paragraph");

	FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
	findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;

	// प्रत्येक पैराग्राफ में "सेक्शन" शब्द के बाद दोहरा ब्रेक लगाएं, रेखांकन जोड़ें और उसे केन्द्र में रखें।
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	// कस्टम टेक्स्ट टैग के स्थान पर अनुभाग विराम डालें।
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## निष्कर्ष

इस लेख में, हमने C# स्रोत कोड का पता लगाया ताकि यह समझा जा सके कि Aspose.Words के मेटा कैरेक्टर वाले टेक्स्ट को कैसे बदलें। हमने दस्तावेज़ बनाने, टेक्स्ट डालने, मेटाकैरेक्टर वाले टेक्स्ट को बदलने और संशोधित दस्तावेज़ को सहेजने के लिए चरण-दर-चरण मार्गदर्शिका का पालन किया।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: Aspose.Words for .NET में मेटा कैरेक्टर युक्त टेक्स्ट बदलें फ़ंक्शन क्या है?

उत्तर: Aspose.Words for .NET में मेटा कैरेक्टर वाले टेक्स्ट को बदलें सुविधा आपको किसी दस्तावेज़ में विशिष्ट मेटा कैरेक्टर वाले टेक्स्ट के भागों को बदलने की अनुमति देती है। आप इस सुविधा का उपयोग अपने दस्तावेज़ में मेटाकैरेक्टर को ध्यान में रखते हुए उन्नत प्रतिस्थापन करने के लिए कर सकते हैं।

#### प्रश्न: .NET के लिए Aspose.Words में नया दस्तावेज़ कैसे बनाएं?

 उत्तर: मेटा कैरेक्टर युक्त टेक्स्ट को बदलें फ़ंक्शन का उपयोग करने से पहले, आपको .NET के लिए Aspose.Words का उपयोग करके एक नया दस्तावेज़ बनाना होगा। यह एक इंस्टेंटिएट करके किया जा सकता है`Document` ऑब्जेक्ट. नया दस्तावेज़ बनाने के लिए यहाँ एक नमूना कोड है:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में पाठ कैसे सम्मिलित करें?

 उत्तर: एक बार आपके पास एक दस्तावेज़ हो जाने पर, आप इसका उपयोग करके पाठ सम्मिलित कर सकते हैं`DocumentBuilder` ऑब्जेक्ट. हमारे उदाहरण में, हम का उपयोग करते हैं`Writeln` विभिन्न अनुभागों में पाठ के कई पैराग्राफ सम्मिलित करने की विधि:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder.Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

#### प्रश्न: .NET के लिए Aspose.Words में खोज और प्रतिस्थापन विकल्पों को कैसे कॉन्फ़िगर करें?

 उत्तर: अब हम एक का उपयोग करके खोज और प्रतिस्थापन विकल्पों को कॉन्फ़िगर करेंगे`FindReplaceOptions` ऑब्जेक्ट। हमारे उदाहरण में, हमने प्रतिस्थापित पैराग्राफ़ के संरेखण को "केंद्रित" पर सेट किया है:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में मेटाकैरेक्टर युक्त पाठ को कैसे बदलें?

 उत्तर: हम इसका प्रयोग करते हैं`Range.Replace` मेटा-अक्षरों वाले पाठ को बदलने की विधि। हमारे उदाहरण में, हम "सेक्शन" शब्द के प्रत्येक आने के बाद पैराग्राफ़ ब्रेक को उसी शब्द से बदलते हैं जिसके बाद कई डैश और एक नया पैराग्राफ़ ब्रेक होता है:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में मेटा वर्णों वाले कस्टम टेक्स्ट टैग को कैसे बदलें?

 उत्तर: हम भी इसका उपयोग करते हैं`Range.Replace` कस्टम को प्रतिस्थापित करने की विधि "{insert-section}" टेक्स्ट टैग को सेक्शन ब्रेक से बदलें। हमारे उदाहरण में, हम " को प्रतिस्थापित करते हैं{insert-section}"&b" के साथ अनुभाग विराम सम्मिलित करने के लिए:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

#### प्रश्न: .NET के लिए Aspose.Words में संपादित दस्तावेज़ को कैसे सहेजा जाए?

 उत्तर: एक बार जब आप दस्तावेज़ में परिवर्तन कर लेते हैं, तो आप इसे निर्दिष्ट निर्देशिका में सहेज सकते हैं`Save` तरीका:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```