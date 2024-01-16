---
title: वर्ड दस्तावेज़ में एशियाई और लैटिन पाठ के बीच का स्थान
linktitle: वर्ड दस्तावेज़ में एशियाई और लैटिन पाठ के बीच का स्थान
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ वर्ड दस्तावेज़ में एशियाई और लैटिन पाठ के बीच के स्थान को स्वचालित रूप से समायोजित करना सीखें।
type: docs
weight: 10
url: /hi/net/document-formatting/space-between-asian-and-latin-text/
---
इस ट्यूटोरियल में, हम आपको दिखाने जा रहे हैं कि .NET के लिए Aspose.Words के साथ वर्ड डॉक्यूमेंट फीचर में एशियाई और लैटिन टेक्स्ट के बीच स्पेस फीचर का उपयोग कैसे करें। स्रोत कोड को समझने और परिवर्तन लागू करने के लिए नीचे दिए गए चरणों का पालन करें।

## चरण 1: दस्तावेज़ बनाना और कॉन्फ़िगर करना

आरंभ करने के लिए, एक नया दस्तावेज़ और एक संबद्ध DocumentBuilder ऑब्जेक्ट बनाएं। ऐसे:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: एशियाई और लैटिन पाठ के बीच स्थान निर्धारित करना

अब हम पैराग्राफफॉर्मेट ऑब्जेक्ट के गुणों का उपयोग करके एशियाई और लैटिन पाठ के बीच के स्थान को कॉन्फ़िगर करेंगे। ऐसे:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## चरण 3: दस्तावेज़ सहेजना

 टेक्स्ट इनपुट फॉर्म फ़ील्ड डालने के बाद, दस्तावेज़ को वांछित स्थान पर सहेजें`Save` तरीका। उचित फ़ाइल पथ प्रदान करना सुनिश्चित करें:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके एशियाई और लैटिन टेक्स्ट के बीच स्पेस के लिए उदाहरण स्रोत कोड

यहां .NET के लिए Aspose.Words के साथ स्पेस बिटवीन एशियन और लैटिन टेक्स्ट फीचर का संपूर्ण स्रोत कोड दिया गया है:


```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Automatically adjust space between Asian and Latin text");
builder.Writeln("Automatically adjust space between Asian text and numbers");

doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

इस कोड के साथ आप .NET के लिए Aspose.Words का उपयोग करके अपने दस्तावेज़ में एशियाई और लैटिन पाठ के बीच के स्थान को स्वचालित रूप से समायोजित करने में सक्षम होंगे।

## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Words के साथ एक वर्ड दस्तावेज़ में एशियाई और लैटिन पाठ के बीच अंतर को समायोजित करने के लिए स्पेस सुविधा का उपयोग करने की प्रक्रिया का पता लगाया। उल्लिखित चरणों का पालन करके, आप उचित रिक्ति और संरेखण सुनिश्चित कर सकते हैं, विशेष रूप से मिश्रित एशियाई और लैटिन सामग्री से निपटने में सहायक।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: वर्ड दस्तावेज़ में एशियाई और लैटिन पाठ के बीच स्पेस सुविधा क्या है?

उ: किसी वर्ड दस्तावेज़ में एशियाई और लैटिन पाठ के बीच रिक्ति सुविधा विभिन्न लिपियों, जैसे एशियाई (उदाहरण के लिए, चीनी, जापानी) और लैटिन (उदाहरण के लिए, अंग्रेजी) में लिखे गए पाठ के बीच अंतर को स्वचालित रूप से समायोजित करने की क्षमता को संदर्भित करती है।

#### प्रश्न: एशियाई और लैटिन पाठ के बीच स्थान का समायोजन क्यों महत्वपूर्ण है?

उ: एशियाई और लैटिन पाठ के बीच स्थान को समायोजित करना यह सुनिश्चित करने के लिए महत्वपूर्ण है कि विभिन्न लिपियाँ दस्तावेज़ के भीतर सामंजस्यपूर्ण रूप से मिश्रित हों। उचित रिक्ति पठनीयता और समग्र दृश्य उपस्थिति को बढ़ाती है, जिससे पाठ को बहुत तंग या फैला हुआ दिखने से रोका जा सकता है।

#### प्रश्न: क्या मैं विभिन्न स्क्रिप्टों के बीच स्थान समायोजन को अनुकूलित कर सकता हूँ?

 उ: हां, आप इसका उपयोग करके विभिन्न स्क्रिप्ट के बीच स्थान समायोजन को अनुकूलित कर सकते हैं`AddSpaceBetweenFarEastAndAlpha` और`AddSpaceBetweenFarEastAndDigit` गुण। इन गुणों को सक्षम या अक्षम करके, आप एशियाई और लैटिन पाठ के साथ-साथ एशियाई पाठ और संख्याओं के बीच के स्थान को नियंत्रित कर सकते हैं।

#### प्रश्न: क्या .NET के लिए Aspose.Words अन्य दस्तावेज़ स्वरूपण सुविधाओं का समर्थन करता है?

उत्तर: हाँ, .NET के लिए Aspose.Words विभिन्न दस्तावेज़ स्वरूपण सुविधाओं के लिए व्यापक समर्थन प्रदान करता है। इसमें फ़ॉन्ट शैलियों, पैराग्राफ, तालिकाओं, छवियों और बहुत कुछ के लिए कार्यक्षमताएं शामिल हैं। आप अपने Word दस्तावेज़ों को प्रोग्रामेटिक रूप से प्रभावी ढंग से हेरफेर और प्रारूपित कर सकते हैं।

#### प्रश्न: मुझे .NET के लिए Aspose.Words के लिए अतिरिक्त संसाधन और दस्तावेज़ कहां मिल सकते हैं?

 उ: .NET के लिए Aspose.Words का उपयोग करने पर व्यापक संसाधनों और दस्तावेज़ीकरण के लिए, पर जाएँ[Aspose.Words API संदर्भ](https://reference.aspose.com/words/net/). वहां, आपको .NET के लिए Aspose.Words की शक्तिशाली सुविधाओं का प्रभावी ढंग से उपयोग करने में मदद करने के लिए विस्तृत गाइड, ट्यूटोरियल, कोड उदाहरण और एपीआई संदर्भ मिलेंगे।