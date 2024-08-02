---
title: सूची संख्या पुनः आरंभ करें
linktitle: सूची संख्या पुनः आरंभ करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: Aspose.Words for .NET के साथ Word दस्तावेज़ में सूची की संख्या को रीसेट करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-list/restart-list-number/
---
इस चरण-दर-चरण ट्यूटोरियल में, हम आपको दिखाएंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में किसी सूची की संख्या को कैसे रीसेट किया जाए। हम प्रदान किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको दिखाएंगे कि इसे अपने प्रोजेक्ट में कैसे लागू किया जाए।

 आरंभ करने के लिए, सुनिश्चित करें कि आपके पास अपने विकास परिवेश में .NET के लिए Aspose.Words स्थापित और कॉन्फ़िगर किया गया है। यदि आपने पहले से ऐसा नहीं किया है, तो लाइब्रेरी को डाउनलोड करें और इंस्टॉल करें[Aspose.Releases]https://releases.aspose.com/words/net/.

## चरण 1: दस्तावेज़ और दस्तावेज़ जनरेटर बनाना

सबसे पहले, एक नया दस्तावेज़ और उससे संबंधित दस्तावेज़ जनरेटर बनाएँ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: पहली सूची बनाना और उसे अनुकूलित करना

इसके बाद, किसी मौजूदा टेम्पलेट के आधार पर एक सूची बनाएं, फिर उसके स्तरों को अनुकूलित करें:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## चरण 3: पहली सूची में आइटम जोड़ना

पहली सूची में आइटम जोड़ने और सूची संख्याएँ हटाने के लिए दस्तावेज़ बिल्डर का उपयोग करें:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## चरण 4: दूसरी सूची बनाना और उसे अनुकूलित करना

संख्या को रीसेट करके पहली सूची का पुनः उपयोग करने के लिए, मूल सूची लेआउट की एक प्रतिलिपि बनाएँ:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

यदि आवश्यक हो तो आप दूसरी सूची में अतिरिक्त परिवर्तन भी कर सकते हैं।

## चरण 5: दूसरी सूची में आइटम जोड़ना

दूसरी सूची में आइटम जोड़ने और सूची संख्याएँ निकालने के लिए दस्तावेज़ बिल्डर का पुनः उपयोग करें:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## चरण 6: संशोधित दस्तावेज़ को सहेजें

अंत में, संशोधित दस्तावेज़ को सहेजें:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

तो ! आपने .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में सूची की संख्या को सफलतापूर्वक रीसेट कर दिया है।

### सूची संख्या रीसेट के लिए नमूना स्रोत कोड

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// एक टेम्पलेट के आधार पर एक सूची बनाएं.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// पहली सूची का पुनः उपयोग करने के लिए, हमें मूल सूची स्वरूपण की प्रतिलिपि बनाकर क्रमांकन पुनः आरंभ करना होगा।
List list2 = doc.Lists.AddCopy(list1);

// हम नई सूची को किसी भी तरह से संशोधित कर सकते हैं, जिसमें नई आरंभ संख्या निर्धारित करना भी शामिल है।
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words में किसी सूची की क्रमांकन पुनः कैसे शुरू कर सकता हूँ?

 A: Aspose.Words में किसी सूची की क्रमांकन पुनः आरंभ करने के लिए, आप इसका उपयोग कर सकते हैं`ListRestartAtNumber` की विधि`List` क्लास। यह विधि आपको एक नया डायल मान सेट करने की अनुमति देती है जिससे सूची को फिर से शुरू किया जाना चाहिए। उदाहरण के लिए, आप उपयोग कर सकते हैं`list.ListRestartAtNumber(1)` 1 से क्रमांकन पुनः आरंभ करने के लिए.

#### प्रश्न: क्या Aspose.Words में पुनः आरंभ की गई सूची क्रमांकन के उपसर्ग और प्रत्यय को अनुकूलित करना संभव है?

 उत्तर: हां, आप Aspose.Words में पुनः आरंभ की गई सूची क्रमांकन के उपसर्ग और प्रत्यय को अनुकूलित कर सकते हैं।`ListLevel`वर्ग जैसे गुण प्रदान करता है`ListLevel.NumberPrefix`और`ListLevel.NumberSuffix` जो आपको सूची में प्रत्येक स्तर के लिए उपसर्ग और प्रत्यय निर्दिष्ट करने की अनुमति देता है। आप इन गुणों का उपयोग आवश्यकतानुसार उपसर्ग और प्रत्यय को अनुकूलित करने के लिए कर सकते हैं।

#### प्रश्न: मैं एक विशिष्ट क्रमांकन मान कैसे निर्दिष्ट कर सकता हूं जिससे सूची को पुनः प्रारंभ किया जाना चाहिए?

 उत्तर: एक विशिष्ट संख्या मान निर्दिष्ट करने के लिए जिससे सूची को पुनः आरंभ किया जाना चाहिए, आप इसका उपयोग कर सकते हैं`ListRestartAtNumber` वांछित मान को तर्क के रूप में पास करने वाली विधि। उदाहरण के लिए, 5 से नंबरिंग को फिर से शुरू करने के लिए, आप इसका उपयोग कर सकते हैं`list.ListRestartAtNumber(5)`.

#### प्रश्न: क्या Aspose.Words में बहु-स्तरीय सूची क्रमांकन को पुनः आरंभ करना संभव है?

 उत्तर: हाँ, Aspose.Words कई सूची स्तरों की पुनः आरंभ संख्या का समर्थन करता है। आप लागू कर सकते हैं`ListRestartAtNumber` प्रत्येक सूची स्तर पर अलग-अलग क्रमांकन पुनः आरंभ करने के लिए विधि। उदाहरण के लिए, आप उपयोग कर सकते हैं`list.Levels[0].ListRestartAtNumber(1)` प्रथम सूची स्तर को 1 से पुनः आरंभ करने के लिए, तथा`list.Levels[1].ListRestartAtNumber(1)` 1 से शुरू करके दूसरे स्तर की सूची को पुनः आरंभ करने के लिए, और इसी प्रकार आगे भी।



