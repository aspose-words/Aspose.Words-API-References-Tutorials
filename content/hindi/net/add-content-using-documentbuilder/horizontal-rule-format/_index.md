---
title: वर्ड दस्तावेज़ में क्षैतिज नियम प्रारूप
linktitle: वर्ड दस्तावेज़ में क्षैतिज नियम प्रारूप
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में अनुकूलन योग्य क्षैतिज नियम सम्मिलित करना सीखें। अपने दस्तावेज़ स्वचालन को बढ़ाएँ।
type: docs
weight: 10
url: /hi/net/add-content-using-documentbuilder/horizontal-rule-format/
---
## परिचय

.NET विकास के दायरे में, Word दस्तावेज़ों को प्रोग्रामेटिक रूप से हेरफेर करना और फ़ॉर्मेट करना एक कठिन काम हो सकता है। सौभाग्य से, .NET के लिए Aspose.Words एक मजबूत समाधान प्रदान करता है, जो डेवलपर्स को दस्तावेज़ निर्माण, संपादन और प्रबंधन को आसानी से स्वचालित करने के लिए सशक्त बनाता है। यह आलेख आवश्यक विशेषताओं में से एक पर प्रकाश डालता है: Word दस्तावेज़ों में क्षैतिज नियम सम्मिलित करना। चाहे आप एक अनुभवी डेवलपर हों या Aspose.Words से शुरुआत कर रहे हों, इस क्षमता में महारत हासिल करने से आपकी दस्तावेज़ निर्माण प्रक्रिया में वृद्धि होगी।

## आवश्यक शर्तें

.NET के लिए Aspose.Words का उपयोग करके क्षैतिज नियमों को लागू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

- विजुअल स्टूडियो: .NET विकास के लिए विजुअल स्टूडियो आईडीई स्थापित करें।
- .NET के लिए Aspose.Words: .NET के लिए Aspose.Words को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/words/net/).
- बुनियादी सी# ज्ञान: सी# प्रोग्रामिंग भाषा की बुनियादी बातों से परिचित होना।
-  डॉक्यूमेंटबिल्डर क्लास: की समझ`DocumentBuilder` दस्तावेज़ हेरफेर के लिए Aspose.Words में कक्षा।

## नामस्थान आयात करें

आरंभ करने के लिए, अपने C# प्रोजेक्ट में आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Words;
using System.Drawing;
```

ये नेमस्पेस दस्तावेज़ हेरफेर के लिए Aspose.Words कक्षाओं और रंगों को संभालने के लिए मानक .NET कक्षाओं तक पहुंच प्रदान करते हैं।

आइए .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में क्षैतिज नियम जोड़ने की प्रक्रिया को व्यापक चरणों में विभाजित करें:

## चरण 1: डॉक्यूमेंटबिल्डर और सेट डायरेक्टरी को आरंभ करें

 सबसे पहले, आरंभ करें a`DocumentBuilder` ऑब्जेक्ट बनाएं और निर्देशिका पथ सेट करें जहां दस्तावेज़ सहेजा जाएगा।

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
DocumentBuilder builder = new DocumentBuilder();
```

## चरण 2: क्षैतिज नियम डालें

 उपयोग`InsertHorizontalRule()` की विधि`DocumentBuilder` क्षैतिज नियम जोड़ने के लिए कक्षा।

```csharp
Shape shape = builder.InsertHorizontalRule();
```

## चरण 3: क्षैतिज नियम प्रारूप को अनुकूलित करें

 तक पहुंच`HorizontalRuleFormat` क्षैतिज नियम की उपस्थिति को अनुकूलित करने के लिए सम्मिलित आकार की संपत्ति।

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

- संरेखण: क्षैतिज नियम के संरेखण को निर्दिष्ट करता है (`HorizontalRuleAlignment.Center` इस उदाहरण में)।
- चौड़ाई प्रतिशत: क्षैतिज नियम की चौड़ाई को पृष्ठ की चौड़ाई के प्रतिशत के रूप में सेट करता है (इस उदाहरण में 70%)।
- ऊंचाई: क्षैतिज नियम की ऊंचाई को बिंदुओं में परिभाषित करता है (इस उदाहरण में 3 बिंदु)।
- रंग: क्षैतिज नियम का रंग सेट करता है (`Color.Blue` इस उदाहरण में)।
- NoShade: निर्दिष्ट करता है कि क्षैतिज नियम में छाया होनी चाहिए या नहीं (`true` इस उदाहरण में)।

## चरण 4: दस्तावेज़ सहेजें

 अंत में, संशोधित दस्तावेज़ को का उपयोग करके सहेजें`Save` की विधि`Document` वस्तु।

```csharp
builder.Document.Save(dataDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

## निष्कर्ष

.NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में क्षैतिज नियमों को सम्मिलित करने में महारत हासिल करना आपके दस्तावेज़ स्वचालन क्षमताओं को बढ़ाता है। Aspose.Words के लचीलेपन और शक्ति का लाभ उठाकर, डेवलपर्स दस्तावेज़ निर्माण और स्वरूपण प्रक्रियाओं को कुशलतापूर्वक सुव्यवस्थित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### .NET के लिए Aspose.Words क्या है?
.NET के लिए Aspose.Words .NET अनुप्रयोगों में प्रोग्रामेटिक रूप से Word दस्तावेज़ों के साथ काम करने के लिए एक शक्तिशाली लाइब्रेरी है।

### मैं .NET के लिए Aspose.Words कैसे डाउनलोड कर सकता हूँ?
 आप .NET के लिए Aspose.Words डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/words/net/).

### क्या मैं Aspose.Words में क्षैतिज नियमों की उपस्थिति को अनुकूलित कर सकता हूँ?
हां, आप Aspose.Words का उपयोग करके क्षैतिज नियमों के संरेखण, चौड़ाई, ऊंचाई, रंग और छायांकन जैसे विभिन्न पहलुओं को अनुकूलित कर सकते हैं।

### क्या Aspose.Words एंटरप्राइज़-स्तरीय दस्तावेज़ प्रसंस्करण के लिए उपयुक्त है?
हां, Aspose.Words का व्यापक रूप से इसकी मजबूत दस्तावेज़ हेरफेर क्षमताओं के लिए एंटरप्राइज़ वातावरण में उपयोग किया जाता है।

### मुझे .NET के लिए Aspose.Words के लिए समर्थन कहाँ से मिल सकता है?
 समर्थन और सामुदायिक सहभागिता के लिए, पर जाएँ[Aspose.शब्द मंच](https://forum.aspose.com/c/words/8).
