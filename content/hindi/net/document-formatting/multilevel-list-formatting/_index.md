---
title: Word दस्तावेज़ में बहुस्तरीय सूची स्वरूपण
linktitle: Word दस्तावेज़ में बहुस्तरीय सूची स्वरूपण
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि बहुस्तरीय सूची कैसे बनाएं और .NET के लिए Aspose.Words के साथ वर्ड दस्तावेज़ में कस्टम फ़ॉर्मेटिंग कैसे लागू करें।
type: docs
weight: 10
url: /hi/net/document-formatting/multilevel-list-formatting/
---
इस ट्यूटोरियल में, हम आपको दिखाने जा रहे हैं कि .NET के लिए Aspose.Words के साथ वर्ड डॉक्यूमेंट फीचर में मल्टीलेवल लिस्ट फ़ॉर्मेटिंग का उपयोग कैसे करें। स्रोत कोड को समझने और परिवर्तन लागू करने के लिए नीचे दिए गए चरणों का पालन करें।

## चरण 1: दस्तावेज़ बनाना और कॉन्फ़िगर करना

आरंभ करने के लिए, एक नया दस्तावेज़ और एक संबद्ध DocumentBuilder ऑब्जेक्ट बनाएं। ऐसे:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: बहुस्तरीय सूची का प्रारूपण

अब हम DocumentBuilder ऑब्जेक्ट में उपलब्ध विधियों का उपयोग करके बहुस्तरीय सूची स्वरूपण लागू करेंगे। ऐसे:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## चरण 3: दस्तावेज़ सहेजना

 टेक्स्ट इनपुट फॉर्म फ़ील्ड डालने के बाद, दस्तावेज़ को वांछित स्थान पर सहेजें`Save` तरीका। उचित फ़ाइल पथ प्रदान करना सुनिश्चित करें:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके बहुस्तरीय सूची फ़ॉर्मेटिंग के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words के साथ बहुस्तरीय सूची स्वरूपण सुविधा के लिए संपूर्ण स्रोत कोड यहां दिया गया है:


```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

इस कोड के साथ आप एक बहु-स्तरीय सूची बनाने और .NET के लिए Aspose.Words का उपयोग करके प्रत्येक स्तर पर उचित स्वरूपण लागू करने में सक्षम होंगे।


## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में बहुस्तरीय सूची स्वरूपण सुविधा का उपयोग करने की प्रक्रिया का पता लगाया है। उल्लिखित चरणों का पालन करके, आप अपने दस्तावेज़ों की संरचना और पठनीयता को बढ़ाते हुए, कई स्तरों के साथ सुव्यवस्थित सूचियाँ बना सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: वर्ड दस्तावेज़ में बहुस्तरीय सूची क्या है?

ए: वर्ड दस्तावेज़ में एक बहुस्तरीय सूची एक पदानुक्रमित सूची है जो आपको आइटम को उप-आइटम के विभिन्न स्तरों में व्यवस्थित करने की अनुमति देती है। यह जानकारी को संरचित तरीके से प्रस्तुत करने में मदद करता है, जिससे पाठकों के लिए सामग्री को समझना आसान हो जाता है।

#### प्रश्न: क्या मैं बहुस्तरीय सूची के स्वरूप को अनुकूलित कर सकता हूँ?

उ: हां, आप अपने वर्ड दस्तावेज़ में बहुस्तरीय सूची की उपस्थिति को अनुकूलित कर सकते हैं। विभिन्न शैलियों, जैसे कि बुलेट पॉइंट, संख्याएँ, या अक्षर, को लागू करके और इंडेंटेशन और रिक्ति को समायोजित करके, आप एक आकर्षक और व्यवस्थित सूची बना सकते हैं।

#### प्रश्न: क्या .NET के लिए Aspose.Words अन्य सूची फ़ॉर्मेटिंग विकल्पों का समर्थन करता है?

उत्तर: हां, .NET के लिए Aspose.Words सूची स्वरूपण के लिए सुविधाओं का एक व्यापक सेट प्रदान करता है। यह विभिन्न प्रकार की सूची का समर्थन करता है, जिसमें बुलेटेड सूचियाँ, क्रमांकित सूचियाँ और बहुस्तरीय सूचियाँ शामिल हैं। आप सूचियों के स्वरूपण में हेरफेर कर सकते हैं, आइटम जोड़ या हटा सकते हैं और उनकी उपस्थिति को अनुकूलित कर सकते हैं।

#### प्रश्न: क्या मैं अन्य दस्तावेज़ तत्वों के साथ काम करने के लिए .NET के लिए Aspose.Words का उपयोग कर सकता हूँ?

उत्तर: हां, .NET के लिए Aspose.Words विभिन्न दस्तावेज़ तत्वों, जैसे पैराग्राफ, तालिकाओं, छवियों और बहुत कुछ के साथ काम करने के लिए व्यापक क्षमताएं प्रदान करता है। यह आपको दस्तावेज़ प्रसंस्करण कार्यों को सुव्यवस्थित करते हुए, Word दस्तावेज़ों को प्रोग्रामेटिक रूप से बनाने, संशोधित करने और परिवर्तित करने में सक्षम बनाता है।