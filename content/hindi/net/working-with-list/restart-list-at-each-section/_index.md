---
title: प्रत्येक अनुभाग पर सूची पुनः आरंभ करें
linktitle: प्रत्येक अनुभाग पर सूची पुनः आरंभ करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में प्रत्येक अनुभाग में क्रमांकित सूची को रीसेट करने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/working-with-list/restart-list-at-each-section/
---

इस चरण-दर-चरण ट्यूटोरियल में, हम आपको दिखाएंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में प्रत्येक अनुभाग में क्रमांकित सूची को कैसे रीसेट किया जाए। हम दिए गए C# स्रोत कोड की व्याख्या करेंगे और आपको दिखाएंगे कि इसे अपनी परियोजनाओं में कैसे लागू किया जाए।

 आरंभ करने के लिए, सुनिश्चित करें कि आपके पास अपने विकास परिवेश में .NET के लिए Aspose.Words स्थापित और कॉन्फ़िगर है। यदि आपने पहले से नहीं किया है, तो यहां से लाइब्रेरी डाउनलोड और इंस्टॉल करें[Aspose.Releases]https://releases.aspose.com/words/net/।

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

 फिर ए का प्रयोग करें`DocumentBuilder` सूची में आइटम जोड़ने के लिए. आप सूची में एकाधिक आइटम जोड़ने के लिए लूप का उपयोग कर सकते हैं:

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

इस उदाहरण में, हम पुन: क्रमांकन को स्पष्ट करने के लिए 15वीं सूची आइटम के बाद एक अनुभाग विराम सम्मिलित कर रहे हैं।

## चरण 3: संशोधित दस्तावेज़ सहेजें

अंत में, संशोधित दस्तावेज़ सहेजें:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

इसलिए ! आपने .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में प्रत्येक अनुभाग में क्रमांकित सूची को सफलतापूर्वक रीसेट कर दिया है।

### प्रत्येक अनुभाग में सूची को रीसेट करने के लिए उदाहरण स्रोत कोड

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

बेझिझक इस कोड को अपनी परियोजनाओं में उपयोग करें और इसे अपनी विशिष्ट आवश्यकताओं के अनुरूप संशोधित करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words में प्रत्येक अनुभाग पर एक सूची को कैसे पुनः आरंभ कर सकता हूं?

 उ: Aspose.Words में प्रत्येक अनुभाग पर एक सूची को पुनः आरंभ करने के लिए, आपको इसका एक उदाहरण बनाना होगा`List` कक्षा बनाएं और उसे एक क्रमांकित सूची निर्दिष्ट करें। तो आप इसका उपयोग कर सकते हैं`List.IsRestartAtEachSection` यह निर्दिष्ट करने के लिए संपत्ति कि प्रत्येक अनुभाग पर क्रमांकन पुनः आरंभ किया जाना चाहिए। आप इस सूची को अपने दस्तावेज़ के एक या अधिक अनुभागों के साथ संबद्ध कर सकते हैं ताकि प्रत्येक अनुभाग पर क्रमांकन सही ढंग से पुनः आरंभ हो सके।

#### प्रश्न: क्या मैं Aspose.Words में सूचियों के क्रमांकन प्रारूप को अनुकूलित कर सकता हूँ?

उ: हाँ, आप Aspose.Words में सूचियों के क्रमांकन प्रारूप को अनुकूलित कर सकते हैं।`List` क्लास इसके लिए कई गुण प्रदान करता है, जैसे`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`, आदि। आप इन गुणों का उपयोग सूची प्रकार (क्रमांकित, बुलेटेड, आदि), क्रमांकन प्रारूप (अरबी अंक, रोमन अंक, अक्षर, आदि), और अन्य क्रमांकन स्वरूपण विकल्प सेट करने के लिए कर सकते हैं।

#### प्रश्न: क्या Aspose.Words में क्रमांकित सूची में अतिरिक्त स्तर जोड़ना संभव है?

 उत्तर: हां, Aspose.Words में क्रमांकित सूची में अतिरिक्त स्तर जोड़ना संभव है।`ListLevel` क्लास आपको सूची के प्रत्येक स्तर के लिए फ़ॉर्मेटिंग गुण सेट करने की अनुमति देता है। आप उपसर्ग, प्रत्यय, संरेखण, इंडेंट इत्यादि जैसे विकल्प सेट कर सकते हैं। यह आपको पदानुक्रम के कई स्तरों के साथ सूचियां बनाने की अनुमति देता है।