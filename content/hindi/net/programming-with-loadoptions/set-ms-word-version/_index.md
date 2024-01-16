---
title: एमएस वर्ड संस्करण सेट करें
linktitle: एमएस वर्ड संस्करण सेट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके MS Word के निर्दिष्ट संस्करण के साथ दस्तावेज़ को लोड करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-loadoptions/set-ms-word-version/
---
जब C# एप्लिकेशन में Word दस्तावेज़ों के साथ Word प्रसंस्करण किया जाता है, तो दस्तावेज़ को लोड करते समय उपयोग करने के लिए Microsoft Word के संस्करण को निर्दिष्ट करना आवश्यक हो सकता है। .NET के लिए Aspose.Words लाइब्रेरी के साथ, आप LoadOptions का उपयोग करके आसानी से MS Word के किस संस्करण का उपयोग करना है यह निर्धारित कर सकते हैं। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको बताएंगे कि LoadOptions लोड विकल्पों का उपयोग करके MS Word के एक निर्दिष्ट संस्करण के साथ दस्तावेज़ को लोड करने के लिए .NET C# स्रोत कोड के लिए Aspose.Words का उपयोग कैसे करें।

## Aspose.Words लाइब्रेरी को समझना

कोड में गोता लगाने से पहले, .NET के लिए Aspose.Words लाइब्रेरी को समझना महत्वपूर्ण है। Aspose.Words .NET सहित विभिन्न प्लेटफार्मों में Word दस्तावेज़ों को बनाने, संपादित करने, परिवर्तित करने और सुरक्षित करने के लिए एक शक्तिशाली लाइब्रेरी है। यह दस्तावेज़ों में हेरफेर करने के लिए कई सुविधाएँ प्रदान करता है, जैसे टेक्स्ट सम्मिलित करना, फ़ॉर्मेटिंग बदलना, अनुभाग जोड़ना और बहुत कुछ।

## लोडिंग विकल्प कॉन्फ़िगर करना

पहला कदम हमारे दस्तावेज़ के लिए लोडिंग विकल्पों को कॉन्फ़िगर करना है। लोडिंग पैरामीटर निर्दिष्ट करने के लिए LoadOptions वर्ग का उपयोग करें। हमारे मामले में, हमें MswVersion प्रॉपर्टी को MS Word के वांछित संस्करण में सेट करने की आवश्यकता है। उदाहरण के लिए, हम Microsoft Word 2010 संस्करण का उपयोग कर रहे हैं। यहां है कि इसे कैसे करना है:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

हम एक नया LoadOptions ऑब्जेक्ट बनाते हैं और MS Word 2010 के संस्करण को निर्दिष्ट करने के लिए MswVersion प्रॉपर्टी को MsWordVersion.Word2010 पर सेट करते हैं।

## एमएस वर्ड के निर्दिष्ट संस्करण के साथ दस्तावेज़ लोड हो रहा है

अब जब हमने लोड विकल्प कॉन्फ़िगर कर लिया है, तो हम दस्तावेज़ वर्ग का उपयोग करके दस्तावेज़ लोड कर सकते हैं और लोड विकल्प निर्दिष्ट कर सकते हैं। यहाँ एक उदाहरण है :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

इस उदाहरण में, हम निर्दिष्ट लोड विकल्पों का उपयोग करके दस्तावेज़ निर्देशिका में स्थित दस्तावेज़ "Document.docx" को लोड करते हैं।

### .NET के लिए Aspose.Words का उपयोग करके "सेट एमएस वर्ड संस्करण" कार्यक्षमता के साथ लोडऑप्शंस के लिए उदाहरण स्रोत कोड

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// "सेट एमएस वर्ड संस्करण" सुविधा के साथ लोड विकल्प कॉन्फ़िगर करें
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// दस्तावेज़ को MS Word के निर्दिष्ट संस्करण के साथ लोड करें
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// दस्तावेज़ सहेजें
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## निष्कर्ष

इस गाइड में, हमने बताया है कि .NET के लिए Aspose.Words लाइब्रेरी का उपयोग करके MS Word के एक विशिष्ट संस्करण को निर्दिष्ट करने वाले दस्तावेज़ को कैसे अपलोड किया जाए। दिए गए चरणों का पालन करके और दिए गए कोड C# स्रोत का उपयोग करके, आप इस कार्यक्षमता को अपने C# एप्लिकेशन में आसानी से लागू कर सकते हैं। एमएस वर्ड के निर्दिष्ट संस्करण के साथ एक दस्तावेज़ लोड करने से आप अपने एप्लिकेशन में दस्तावेज़ की उचित संगतता और प्रसंस्करण सुनिश्चित कर सकते हैं।


### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: C# एप्लिकेशन में दस्तावेज़ लोड करते समय मुझे MS Word का संस्करण निर्दिष्ट करने की आवश्यकता क्यों होगी?

एमएस वर्ड के संस्करण को निर्दिष्ट करना यह सुनिश्चित करता है कि दस्तावेज़ सही ढंग से लोड और संसाधित किया गया है, खासकर जब विशिष्ट स्वरूपण या सुविधाओं से निपटना जो विभिन्न संस्करणों के बीच भिन्न हो सकते हैं।

#### प्रश्न: Aspose.Words एमएस वर्ड के किस संस्करण का समर्थन करता है?

उत्तर: .NET के लिए Aspose.Words एमएस वर्ड के विभिन्न संस्करणों का समर्थन करता है, जिसमें वर्ड 97, वर्ड 2003, वर्ड 2007, वर्ड 2010, वर्ड 2013, वर्ड 2016, वर्ड 2019 और बहुत कुछ शामिल हैं।

#### प्रश्न: क्या मैं अपने सिस्टम पर स्थापित एमएस वर्ड के संस्करण से भिन्न संस्करण के साथ एक दस्तावेज़ लोड कर सकता हूँ?

उ: हाँ, Aspose.Words आपको दस्तावेज़ लोड करते समय MS Word का एक अलग संस्करण निर्दिष्ट करने की अनुमति देता है, भले ही लक्ष्य प्रणाली में एक अलग MS Word संस्करण हो, भले ही अनुकूलता सुनिश्चित हो।

#### प्रश्न: MS Word संस्करण सेट करने से मेरे C# एप्लिकेशन को कैसे लाभ होता है?

उ: एमएस वर्ड संस्करण को सेट करने से यह सुनिश्चित होता है कि दस्तावेज़ को उस विशिष्ट संस्करण के इच्छित स्वरूपण और सुविधाओं के अनुसार संसाधित किया जाता है, जो लगातार आउटपुट प्रदान करता है।

#### प्रश्न: क्या Aspose.Words केवल DOCX दस्तावेज़ों को संभालने तक ही सीमित है?

उत्तर: नहीं, Aspose.Words DOC, RTF, HTML, PDF और अन्य सहित विभिन्न दस्तावेज़ प्रारूपों का समर्थन करता है, जो इसे विभिन्न प्रकार के दस्तावेज़ों को संभालने के लिए एक बहुमुखी उपकरण बनाता है।