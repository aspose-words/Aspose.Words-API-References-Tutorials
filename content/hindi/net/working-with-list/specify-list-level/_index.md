---
title: सूची स्तर निर्दिष्ट करें
linktitle: सूची स्तर निर्दिष्ट करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में सूची स्तर निर्दिष्ट करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-list/specify-list-level/
---

इस चरण-दर-चरण ट्यूटोरियल में, हम आपको दिखाएंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में सूची स्तर कैसे निर्दिष्ट करें। हम प्रदान किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको दिखाएंगे कि इसे अपनी परियोजनाओं में कैसे लागू किया जाए।

 आरंभ करने के लिए, सुनिश्चित करें कि आपके पास अपने विकास परिवेश में .NET के लिए Aspose.Words स्थापित और कॉन्फ़िगर किया गया है। यदि आपने पहले से ऐसा नहीं किया है, तो लाइब्रेरी को डाउनलोड करें और इंस्टॉल करें[Aspose.Releases]https://releases.aspose.com/words/net/.

## चरण 1: दस्तावेज़ और दस्तावेज़ जनरेटर बनाना

सबसे पहले, एक नया दस्तावेज़ और उससे संबंधित दस्तावेज़ जनरेटर बनाएँ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: क्रमांकित सूची बनाना और लागू करना

इसके बाद, Microsoft Word के सूची टेम्पलेट्स में से किसी एक के आधार पर क्रमांकित सूची बनाएं और उसे दस्तावेज़ बिल्डर में वर्तमान पैराग्राफ पर लागू करें:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## चरण 3: सूची स्तर विनिर्देश

 दस्तावेज़ बिल्डर का उपयोग करें`ListLevelNumber` सूची स्तर निर्दिष्ट करने और पैराग्राफ़ में पाठ जोड़ने के लिए संपत्ति:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

सूची स्तर निर्दिष्ट करने और प्रत्येक स्तर पर पाठ जोड़ने के लिए इन चरणों को दोहराएँ.

## चरण 4: बुलेटेड सूची बनाना और लागू करना

आप Microsoft Word के किसी सूची टेम्पलेट का उपयोग करके बुलेटेड सूची भी बना सकते हैं और लागू कर सकते हैं:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## चरण 5: बुलेटेड सूची स्तरों में पाठ जोड़ना

 उपयोग`ListLevelNumber` बुलेटेड सूची स्तर निर्दिष्ट करने और पाठ जोड़ने के लिए प्रॉपर्टी को फिर से खोलें:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## चरण 6: सूची को फ़ॉर्मेट करना बंद करें

 सूची स्वरूपण रोकने के लिए, सेट करें`null` तक`List`दस्तावेज़ जनरेटर की संपत्ति:

```csharp
builder. ListFormat. List = null;
```

## चरण 7: संशोधित दस्तावेज़ को सहेजना

संशोधित दस्तावेज़ सहेजें:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

तो ! आपने .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में सूची स्तर को सफलतापूर्वक निर्दिष्ट किया है।

### सूची स्तर निर्दिष्ट करने के लिए नमूना स्रोत कोड

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Microsoft Word सूची टेम्पलेट्स में से किसी एक के आधार पर क्रमांकित सूची बनाएं
//और इसे दस्तावेज़ निर्माता के वर्तमान पैराग्राफ़ पर लागू करें.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// इस सूची में नौ स्तर हैं, आइए उन सभी को आज़माएँ।
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Microsoft Word सूची टेम्पलेट्स में से किसी एक के आधार पर बुलेटेड सूची बनाएं
//और इसे दस्तावेज़ निर्माता के वर्तमान पैराग्राफ़ पर लागू करें.
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

 उत्तर: Aspose.Words में सूची स्तर निर्दिष्ट करने के लिए, आपको इसका एक उदाहरण बनाना होगा`List` क्लास में जाकर उसे क्रमांकित सूची दें। फिर आप इसका उपयोग कर सकते हैं`Paragraph.ListFormat.ListLevelNumber` प्रत्येक सूची आइटम का स्तर निर्दिष्ट करने के लिए प्रॉपर्टी। आप इस सूची को अपने दस्तावेज़ के किसी अनुभाग से संबद्ध कर सकते हैं ताकि सूची आइटम में वांछित स्तर हो।

#### प्रश्न: क्या Aspose.Words में सूची आइटमों के क्रमांकन प्रारूप को बदलना संभव है?

 उत्तर: हां, आप Aspose.Words में सूची आइटमों के क्रमांकन प्रारूप को बदल सकते हैं।`ListLevel` क्लास इसके लिए कई गुण प्रदान करता है, जैसे`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`, आदि। आप इन गुणों का उपयोग सूची आइटमों के लिए क्रमांकन प्रारूप सेट करने के लिए कर सकते हैं, जैसे अरबी अंक, रोमन अंक, अक्षर, आदि।

#### प्रश्न: क्या मैं Aspose.Words में क्रमांकित सूची में अतिरिक्त स्तर जोड़ सकता हूँ?

 उत्तर: हां, Aspose.Words में क्रमांकित सूची में अतिरिक्त स्तर जोड़ना संभव है।`ListLevel`क्लास आपको सूची के प्रत्येक स्तर के लिए स्वरूपण गुण सेट करने की अनुमति देता है। आप उपसर्ग, प्रत्यय, संरेखण, इंडेंट आदि जैसे विकल्प सेट कर सकते हैं। यह आपको पदानुक्रम के कई स्तरों वाली सूचियाँ बनाने की अनुमति देता है।


