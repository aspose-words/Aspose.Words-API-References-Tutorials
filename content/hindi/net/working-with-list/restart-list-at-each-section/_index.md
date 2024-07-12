---
title: प्रत्येक अनुभाग पर सूची पुनः आरंभ करें
linktitle: प्रत्येक अनुभाग पर सूची पुनः आरंभ करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: Aspose.Words for .NET के साथ Word दस्तावेज़ में प्रत्येक अनुभाग में क्रमांकित सूची को रीसेट करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-list/restart-list-at-each-section/
---

इस चरण-दर-चरण ट्यूटोरियल में, हम आपको दिखाएंगे कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में प्रत्येक अनुभाग के लिए क्रमांकित सूची को कैसे रीसेट किया जाए। हम प्रदान किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको दिखाएंगे कि इसे अपनी परियोजनाओं में कैसे लागू किया जाए।

 आरंभ करने के लिए, सुनिश्चित करें कि आपके पास अपने विकास परिवेश में .NET के लिए Aspose.Words स्थापित और कॉन्फ़िगर किया गया है। यदि आपने पहले से ऐसा नहीं किया है, तो लाइब्रेरी को डाउनलोड करें और इंस्टॉल करें[Aspose.Releases]https://releases.aspose.com/words/net/.

## चरण 1: दस्तावेज़ और सूची बनाना

सबसे पहले, एक नया दस्तावेज़ बनाएं और एक डिफ़ॉल्ट क्रमांकित सूची जोड़ें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## चरण 2: सूची में आइटम जोड़ना

 फिर एक का उपयोग करें`DocumentBuilder` सूची में आइटम जोड़ने के लिए। आप सूची में कई आइटम जोड़ने के लिए लूप का उपयोग कर सकते हैं:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

इस उदाहरण में, हम पुनर्संख्याकरण को दर्शाने के लिए 15वें सूची आइटम के बाद एक अनुभाग विराम सम्मिलित कर रहे हैं।

## चरण 3: संशोधित दस्तावेज़ को सहेजें

अंत में, संशोधित दस्तावेज़ को सहेजें:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

तो ! आपने .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में प्रत्येक अनुभाग में एक क्रमांकित सूची को सफलतापूर्वक रीसेट कर दिया है।

### प्रत्येक अनुभाग पर सूची को रीसेट करने के लिए उदाहरण स्रोत कोड

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

कृपया इस कोड को अपनी परियोजनाओं में उपयोग करें तथा अपनी विशिष्ट आवश्यकताओं के अनुरूप इसमें संशोधन करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words में प्रत्येक अनुभाग पर सूची को पुनः कैसे प्रारंभ कर सकता हूँ?

 A: Aspose.Words में प्रत्येक अनुभाग पर एक सूची को पुनः आरंभ करने के लिए, आपको एक उदाहरण बनाने की आवश्यकता है`List`क्लास को चुनें और उसे एक क्रमांकित सूची असाइन करें। फिर आप इसका उपयोग कर सकते हैं`List.IsRestartAtEachSection` यह निर्दिष्ट करने के लिए कि प्रत्येक अनुभाग पर क्रमांकन को फिर से शुरू किया जाना चाहिए, संपत्ति का उपयोग करें। आप इस सूची को अपने दस्तावेज़ के एक या अधिक अनुभागों से संबद्ध कर सकते हैं ताकि प्रत्येक अनुभाग पर क्रमांकन को सही ढंग से फिर से शुरू किया जा सके।

#### प्रश्न: क्या मैं Aspose.Words में सूचियों के क्रमांकन प्रारूप को अनुकूलित कर सकता हूँ?

 उत्तर: हां, आप Aspose.Words में सूचियों के क्रमांकन प्रारूप को अनुकूलित कर सकते हैं।`List` क्लास इसके लिए कई गुण प्रदान करता है, जैसे`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`, आदि। आप इन गुणों का उपयोग सूची प्रकार (क्रमांकित, बुलेटेड, आदि), क्रमांकन प्रारूप (अरबी अंक, रोमन अंक, अक्षर, आदि) और अन्य क्रमांकन स्वरूपण विकल्प सेट करने के लिए कर सकते हैं।

#### प्रश्न: क्या Aspose.Words में क्रमांकित सूची में अतिरिक्त स्तर जोड़ना संभव है?

 उत्तर: हां, Aspose.Words में क्रमांकित सूची में अतिरिक्त स्तर जोड़ना संभव है।`ListLevel`क्लास आपको सूची के प्रत्येक स्तर के लिए स्वरूपण गुण सेट करने की अनुमति देता है। आप उपसर्ग, प्रत्यय, संरेखण, इंडेंट आदि जैसे विकल्प सेट कर सकते हैं। यह आपको पदानुक्रम के कई स्तरों वाली सूचियाँ बनाने की अनुमति देता है।