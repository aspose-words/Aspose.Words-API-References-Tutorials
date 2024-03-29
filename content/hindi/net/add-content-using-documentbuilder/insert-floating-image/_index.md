---
title: वर्ड डॉक्यूमेंट में फ्लोटिंग इमेज डालें
linktitle: वर्ड डॉक्यूमेंट में फ्लोटिंग इमेज डालें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में फ़्लोटिंग छवियां सम्मिलित करना सीखें। चरण-दर-चरण मार्गदर्शिका.
type: docs
weight: 10
url: /hi/net/add-content-using-documentbuilder/insert-floating-image/
---
इस व्यापक उदाहरण में, आप सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में एक फ़्लोटिंग छवि कैसे सम्मिलित करें। हम प्रक्रिया में आपका मार्गदर्शन करेंगे और आपको आवश्यक C# कोड स्निपेट प्रदान करेंगे। इस गाइड के अंत तक, आप अपने दस्तावेज़ों में अनुकूलन योग्य स्थिति और रैपिंग विकल्पों के साथ छवियां जोड़ने में सक्षम होंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- आपके सिस्टम पर .NET लाइब्रेरी के लिए Aspose.Words इंस्टॉल किया गया है।

## चरण 1: एक नया दस्तावेज़ और दस्तावेज़बिल्डर बनाएँ
आरंभ करने के लिए, दस्तावेज़ वर्ग का उपयोग करके एक नया दस्तावेज़ बनाएं और एक दस्तावेज़बिल्डर ऑब्जेक्ट प्रारंभ करें:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: एक फ़्लोटिंग छवि डालें
इसके बाद, फ्लोटिंग इमेज डालने के लिए DocumentBuilder क्लास की InsertImage विधि का उपयोग करें। पैरामीटर के रूप में छवि फ़ाइल पथ, सापेक्ष क्षैतिज और ऊर्ध्वाधर स्थिति, चौड़ाई, ऊंचाई और रैपिंग विकल्प प्रदान करें:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## चरण 3: दस्तावेज़ सहेजें
फ़्लोटिंग छवि डालने के बाद, दस्तावेज़ वर्ग की सेव विधि का उपयोग करके दस्तावेज़ को फ़ाइल में सहेजें:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## .NET के लिए Aspose.Words का उपयोग करके फ़्लोटिंग छवि डालने के लिए उदाहरण स्रोत कोड
.NET के लिए Aspose.Words का उपयोग करके एक फ़्लोटिंग छवि डालने के लिए संपूर्ण स्रोत कोड यहां दिया गया है:
फ़्लोटिंग छवियां विभिन्न परिदृश्यों के लिए उपयोगी होती हैं, जैसे लोगो, चित्र, या सजावटी तत्व जोड़ना जिन्हें दस्तावेज़ के पाठ से स्वतंत्र रूप से रखा जा सकता है।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

छवि फ़ाइल पथ और वांछित स्थिति और रैपिंग विकल्पों सहित अपनी विशिष्ट आवश्यकताओं के अनुसार कोड को समायोजित करना याद रखें।

## निष्कर्ष
बधाई हो! आपने .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में एक फ़्लोटिंग छवि सम्मिलित करना सफलतापूर्वक सीख लिया है। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए स्रोत कोड का उपयोग करके, अब आप अपने दस्तावेज़ों को आकर्षक और अनुकूलन योग्य फ़्लोटिंग छवियों के साथ बढ़ा सकते हैं।

### वर्ड डॉक्यूमेंट में फ्लोटिंग इमेज डालने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं एक ही दस्तावेज़ में एकाधिक फ़्लोटिंग छवियां सम्मिलित कर सकता हूं?

उत्तर: निश्चित रूप से! आप .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में जितनी आवश्यकता हो उतनी फ़्लोटिंग छवियां सम्मिलित कर सकते हैं। कई आकर्षक छवियां जोड़ने के लिए बस प्रविष्टि प्रक्रिया को दोहराएं।

#### प्रश्न: फ़्लोटिंग छवि के लिए कौन से रैपिंग विकल्प उपलब्ध हैं?

उत्तर: .NET के लिए Aspose.Words फ्लोटिंग छवियों के लिए विभिन्न रैपिंग विकल्प प्रदान करता है, जिसमें स्क्वायर, टाइट, थ्रू, टॉपबॉटम और कोई नहीं शामिल हैं। ये विकल्प निर्धारित करते हैं कि टेक्स्ट फ़्लोटिंग छवि के साथ कैसे इंटरैक्ट करता है।

#### प्रश्न: क्या मैं फ़्लोटिंग छवि का आकार समायोजित कर सकता हूँ?

उत्तर: बिल्कुल! आप InsertImage विधि में संबंधित पैरामीटर का उपयोग करके फ़्लोटिंग छवि की चौड़ाई और ऊंचाई निर्दिष्ट कर सकते हैं। यह आपको अपनी डिज़ाइन प्राथमिकताओं के अनुसार छवि के आयामों को नियंत्रित करने की अनुमति देता है।

#### प्रश्न: क्या मैं दस्तावेज़ में किसी विशिष्ट तत्व के सापेक्ष फ़्लोटिंग छवि को रख सकता हूँ?

उ: हाँ, .NET के लिए Aspose.Words आपको फ़्लोटिंग छवि को विशिष्ट तत्वों, जैसे मार्जिन, पृष्ठ, पैराग्राफ या तालिका के सापेक्ष स्थिति में लाने की अनुमति देता है। आप वांछित स्थान प्राप्त करने के लिए उचित सापेक्ष क्षैतिज और ऊर्ध्वाधर स्थिति पैरामीटर चुन सकते हैं।

#### प्रश्न: क्या Aspose.Words for .NET डेस्कटॉप और वेब एप्लिकेशन दोनों के लिए उपयुक्त है?

उत्तर: हाँ, .NET के लिए Aspose.Words एक बहुमुखी लाइब्रेरी है जो डेस्कटॉप और वेब अनुप्रयोगों दोनों के लिए उपयुक्त है। चाहे आप विंडोज़ एप्लिकेशन बना रहे हों या वेब-आधारित सिस्टम, आप लाइब्रेरी को आसानी से एकीकृत कर सकते हैं।
