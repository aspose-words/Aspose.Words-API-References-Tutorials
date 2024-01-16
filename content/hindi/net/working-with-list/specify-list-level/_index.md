---
title: सूची स्तर निर्दिष्ट करें
linktitle: सूची स्तर निर्दिष्ट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में सूची स्तर निर्दिष्ट करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-list/specify-list-level/
---

इस चरण-दर-चरण ट्यूटोरियल में, हम आपको दिखाएंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में सूची स्तर कैसे निर्दिष्ट करें। हम दिए गए C# स्रोत कोड की व्याख्या करेंगे और आपको दिखाएंगे कि इसे अपनी परियोजनाओं में कैसे लागू किया जाए।

 आरंभ करने के लिए, सुनिश्चित करें कि आपके पास अपने विकास परिवेश में .NET के लिए Aspose.Words स्थापित और कॉन्फ़िगर है। यदि आपने पहले से नहीं किया है, तो यहां से लाइब्रेरी डाउनलोड और इंस्टॉल करें[Aspose.Releases]https://releases.aspose.com/words/net/।

## चरण 1: दस्तावेज़ और दस्तावेज़ जेनरेटर बनाना

सबसे पहले, एक नया दस्तावेज़ और एक संबद्ध दस्तावेज़ जनरेटर बनाएं:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: क्रमांकित सूची बनाना और लागू करना

इसके बाद, माइक्रोसॉफ्ट वर्ड के सूची टेम्पलेट्स में से किसी एक के आधार पर एक क्रमांकित सूची बनाएं और इसे दस्तावेज़ निर्माता में वर्तमान पैराग्राफ पर लागू करें:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## चरण 3: सूची स्तर विशिष्टता

 दस्तावेज़ निर्माता का उपयोग करें`ListLevelNumber` सूची स्तर निर्दिष्ट करने और अनुच्छेद में पाठ जोड़ने के लिए संपत्ति:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

सूची स्तर निर्दिष्ट करने और प्रत्येक स्तर पर पाठ जोड़ने के लिए इन चरणों को दोहराएं।

## चरण 4: बुलेटेड सूची बनाना और लागू करना

आप Microsoft Word के किसी सूची टेम्पलेट का उपयोग करके बुलेटेड सूची भी बना और लागू कर सकते हैं:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## चरण 5: बुलेटेड सूची स्तरों पर टेक्स्ट जोड़ना

 उपयोग`ListLevelNumber` बुलेटेड सूची स्तर को निर्दिष्ट करने और पाठ जोड़ने के लिए फिर से संपत्ति:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## चरण 6: सूची फ़ॉर्मेट करना बंद करें

 सूची फ़ॉर्मेटिंग रोकने के लिए, सेट करें`null` तक`List` दस्तावेज़ जनरेटर की संपत्ति:

```csharp
builder. ListFormat. List = null;
```

## चरण 7: संशोधित दस्तावेज़ को सहेजना

संशोधित दस्तावेज़ सहेजें:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

इसलिए ! आपने .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में सूची स्तर को सफलतापूर्वक निर्दिष्ट किया है।

### सूची स्तर निर्दिष्ट करने के लिए नमूना स्रोत कोड

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Microsoft Word सूची टेम्प्लेट में से किसी एक के आधार पर एक क्रमांकित सूची बनाएं
//और इसे दस्तावेज़ निर्माता के वर्तमान पैराग्राफ पर लागू करें।
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// इस सूची में नौ स्तर हैं, आइए उन सभी को आज़माएँ।
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Microsoft Word सूची टेम्प्लेट में से किसी एक के आधार पर एक बुलेटेड सूची बनाएं
//और इसे दस्तावेज़ निर्माता के वर्तमान पैराग्राफ पर लागू करें।
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// यह सूची स्वरूपण को रोकने का एक तरीका है।
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words में सूची स्तर कैसे निर्दिष्ट कर सकता हूं?

 उ: Aspose.Words में सूची स्तर निर्दिष्ट करने के लिए, आपको इसका एक उदाहरण बनाना होगा`List` कक्षा बनाएं और इसे एक क्रमांकित सूची दें। तो आप इसका उपयोग कर सकते हैं`Paragraph.ListFormat.ListLevelNumber` प्रत्येक सूची आइटम का स्तर निर्दिष्ट करने के लिए संपत्ति। आप इस सूची को अपने दस्तावेज़ के एक अनुभाग के साथ जोड़ सकते हैं ताकि सूची आइटम वांछित स्तर पर हों।

#### प्रश्न: क्या Aspose.Words में सूची आइटमों के क्रमांकन प्रारूप को बदलना संभव है?

 उत्तर: हाँ, आप Aspose.Words में सूची आइटमों का क्रमांकन प्रारूप बदल सकते हैं।`ListLevel` क्लास इसके लिए कई गुण प्रदान करता है, जैसे`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`, आदि। आप इन गुणों का उपयोग सूची आइटम, जैसे अरबी अंक, रोमन अंक, अक्षर इत्यादि के लिए क्रमांकन प्रारूप सेट करने के लिए कर सकते हैं।

#### प्रश्न: क्या मैं Aspose.Words में क्रमांकित सूची में अतिरिक्त स्तर जोड़ सकता हूँ?

 उत्तर: हां, Aspose.Words में क्रमांकित सूची में अतिरिक्त स्तर जोड़ना संभव है।`ListLevel` क्लास आपको सूची के प्रत्येक स्तर के लिए फ़ॉर्मेटिंग गुण सेट करने की अनुमति देता है। आप उपसर्ग, प्रत्यय, संरेखण, इंडेंट इत्यादि जैसे विकल्प सेट कर सकते हैं। यह आपको पदानुक्रम के कई स्तरों के साथ सूचियां बनाने की अनुमति देता है।


