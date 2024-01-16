---
title: मेटा कैरेक्टर वाले वर्ड रिप्लेस टेक्स्ट
linktitle: मेटा कैरेक्टर वाले वर्ड रिप्लेस टेक्स्ट
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में मेटाकैरेक्टर वाले टेक्स्ट को शब्दों से कैसे बदला जाए।
type: docs
weight: 10
url: /hi/net/find-and-replace-text/replace-text-containing-meta-characters/
---
इस लेख में, हम .NET लाइब्रेरी के लिए Aspose.Words में वर्ड रिप्लेस टेक्स्ट युक्त मेटा कैरेक्टर फ़ंक्शन का उपयोग करने के तरीके को समझने के लिए उपरोक्त C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको विशिष्ट मेटा-अक्षरों वाले दस्तावेज़ में पाठ के कुछ हिस्सों को बदलने की अनुमति देती है।

## आवश्यक शर्तें

- C# भाषा का बुनियादी ज्ञान।
- Aspose.Words लाइब्रेरी के साथ .NET विकास वातावरण स्थापित।

## चरण 1: एक नया दस्तावेज़ बनाना

 इससे पहले कि हम मेटाकैरेक्टर टेक्स्ट प्रतिस्थापन का उपयोग शुरू करें, हमें .NET के लिए Aspose.Words का उपयोग करके एक नया दस्तावेज़ बनाना होगा। इसे इंस्टेंटियेट करके किया जा सकता है`Document` वस्तु:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## चरण 2: दस्तावेज़ में टेक्स्ट डालें

 एक बार हमारे पास दस्तावेज़ हो जाने पर, हम इसका उपयोग करके टेक्स्ट सम्मिलित कर सकते हैं`DocumentBuilder` वस्तु। हमारे उदाहरण में, हम इसका उपयोग करते हैं`Writeln` पाठ के अनेक अनुच्छेदों को विभिन्न अनुभागों में सम्मिलित करने की विधि:

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

## चरण 3: विकल्प ढूंढें और बदलें को कॉन्फ़िगर करना

 अब हम a का उपयोग करके विकल्पों को ढूंढने और बदलने को कॉन्फ़िगर करेंगे`FindReplaceOptions` वस्तु। हमारे उदाहरण में, हमने प्रतिस्थापित अनुच्छेदों के संरेखण को "केंद्रित" पर सेट किया है:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

## चरण 4: मेटाकैरेक्टर वाले टेक्स्ट को बदलना

 हम उपयोग करते हैं`Range.Replace`मेटाअक्षरों वाले पाठ का प्रतिस्थापन करने की विधि। हमारे उदाहरण में, हम "सेक्शन" शब्द की प्रत्येक घटना को एक पैराग्राफ ब्रेक के बाद उसी शब्द से बदल देते हैं जिसके बाद कई डैश और एक नया पैराग्राफ ब्रेक होता है:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## चरण 5: कस्टम टेक्स्ट टैग को बदलना

 हम भी उपयोग करते हैं`Range.Replace` किसी कस्टम को बदलने की विधि "{insert-section}" सेक्शन ब्रेक के साथ टेक्स्ट टैग। हमारे उदाहरण में, हम प्रतिस्थापित करते हैं "{insert-section}अनुभाग विराम सम्मिलित करने के लिए "&b" के साथ:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## चरण 6: संपादित दस्तावेज़ को सहेजना

अंत में, हम संशोधित दस्तावेज़ को इसका उपयोग करके एक निर्दिष्ट निर्देशिका में सहेजते हैं`Save` तरीका:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके मेटा कैरेक्टर वाले टेक्स्ट को बदलने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words के साथ मेटाएक्टर वाले टेक्स्ट प्रतिस्थापन के उपयोग को प्रदर्शित करने के लिए यहां पूर्ण उदाहरण स्रोत कोड दिया गया है:

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

	// शब्द "सेक्शन" के बाद प्रत्येक पैराग्राफ ब्रेक को दोगुना करें, एक प्रकार की अंडरलाइन जोड़ें और इसे केन्द्रित करें।
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	// कस्टम टेक्स्ट टैग के बजाय सेक्शन ब्रेक डालें।
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## निष्कर्ष

इस लेख में, हमने .NET के लिए Aspose.Words के रिप्लेस टेक्स्ट युक्त मेटा कैरेक्टर फीचर का उपयोग करने के तरीके को समझने के लिए C# स्रोत कोड की खोज की। हमने दस्तावेज़ बनाने, टेक्स्ट सम्मिलित करने, मेटाकैरेक्टर वाले टेक्स्ट को बदलने और संशोधित दस्तावेज़ को सहेजने के लिए चरण-दर-चरण मार्गदर्शिका का पालन किया।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में मेटा कैरेक्टर युक्त रिप्लेस टेक्स्ट फ़ंक्शन क्या है?

उ: .NET के लिए Aspose.Words में मेटा कैरेक्टर वाले टेक्स्ट को बदलें सुविधा आपको विशिष्ट मेटा कैरेक्टर वाले दस्तावेज़ में टेक्स्ट के हिस्सों को बदलने की अनुमति देती है। आप इस सुविधा का उपयोग मेटाकैरेक्टर को ध्यान में रखते हुए अपने दस्तावेज़ में उन्नत प्रतिस्थापन करने के लिए कर सकते हैं।

#### प्रश्न: .NET के लिए Aspose.Words में एक नया दस्तावेज़ कैसे बनाएं?

 उ: मेटा कैरेक्टर वाले रिप्लेस टेक्स्ट फ़ंक्शन का उपयोग करने से पहले, आपको .NET के लिए Aspose.Words का उपयोग करके एक नया दस्तावेज़ बनाना होगा। इसे इंस्टेंटियेट करके किया जा सकता है`Document` वस्तु। नया दस्तावेज़ बनाने के लिए यहां एक नमूना कोड दिया गया है:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में टेक्स्ट कैसे सम्मिलित करें?

 उ: एक बार जब आपके पास दस्तावेज़ हो जाए, तो आप इसका उपयोग करके टेक्स्ट सम्मिलित कर सकते हैं`DocumentBuilder` वस्तु। हमारे उदाहरण में, हम इसका उपयोग करते हैं`Writeln` पाठ के अनेक अनुच्छेदों को विभिन्न अनुभागों में सम्मिलित करने की विधि:

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

#### प्रश्न: .NET के लिए Aspose.Words में खोज को कैसे कॉन्फ़िगर करें और विकल्पों को कैसे बदलें?

 उ: अब हम a का उपयोग करके विकल्प ढूंढने और बदलने को कॉन्फ़िगर करेंगे`FindReplaceOptions` वस्तु। हमारे उदाहरण में, हमने प्रतिस्थापित अनुच्छेदों के संरेखण को "केंद्रित" पर सेट किया है:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में मेटाएक्टर वाले टेक्स्ट को कैसे बदलें?

 उत्तर: हम इसका उपयोग करते हैं`Range.Replace` मेटा-अक्षरों वाले पाठ का प्रतिस्थापन करने की विधि। हमारे उदाहरण में, हम "सेक्शन" शब्द की प्रत्येक घटना को एक पैराग्राफ ब्रेक के बाद उसी शब्द से बदल देते हैं जिसके बाद कई डैश और एक नया पैराग्राफ ब्रेक होता है:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में मेटा वर्ण वाले कस्टम टेक्स्ट टैग को कैसे बदलें?

 उत्तर: हम भी इसका उपयोग करते हैं`Range.Replace` किसी कस्टम को बदलने की विधि "{insert-section}" सेक्शन ब्रेक के साथ टेक्स्ट टैग। हमारे उदाहरण में, हम प्रतिस्थापित करते हैं "{insert-section}अनुभाग विराम सम्मिलित करने के लिए "&b" के साथ:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

#### प्रश्न: संपादित दस्तावेज़ को .NET के लिए Aspose.Words में कैसे सहेजें?

 उ: एक बार जब आप दस्तावेज़ में परिवर्तन कर लेते हैं, तो आप इसका उपयोग करके इसे एक निर्दिष्ट निर्देशिका में सहेज सकते हैं`Save` तरीका:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```