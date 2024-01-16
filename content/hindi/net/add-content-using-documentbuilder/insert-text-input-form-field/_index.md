---
title: वर्ड डॉक्यूमेंट में टेक्स्ट इनपुट फॉर्म फील्ड डालें
linktitle: वर्ड डॉक्यूमेंट में टेक्स्ट इनपुट फॉर्म फील्ड डालें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: इस चरण-दर-चरण मार्गदर्शिका से सीखें कि Word दस्तावेज़ों में टेक्स्ट इनपुट फ़ॉर्म फ़ील्ड सम्मिलित करने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें।
type: docs
weight: 10
url: /hi/net/add-content-using-documentbuilder/insert-text-input-form-field/
---
इस चरण-दर-चरण मार्गदर्शिका में, हम यह पता लगाएंगे कि C# स्रोत कोड का उपयोग करके अपने Word दस्तावेज़ों में टेक्स्ट इनपुट फ़ॉर्म फ़ील्ड को जोड़ने और हेरफेर करने के लिए .NET के लिए Aspose.Words में इन्सर्ट टेक्स्ट इनपुट फ़ॉर्म फ़ील्ड सुविधा का उपयोग कैसे करें। टेक्स्ट इनपुट फॉर्म फ़ील्ड उपयोगकर्ताओं को दस्तावेज़ के भीतर कस्टम टेक्स्ट दर्ज करने की अनुमति देते हैं, जो उन्हें इंटरैक्टिव फॉर्म और प्रश्नावली बनाने के लिए आदर्श बनाता है। नीचे दिए गए निर्देशों का पालन करके, आप अपने दस्तावेज़ों में टेक्स्ट इनपुट फॉर्म फ़ील्ड को आसानी से सम्मिलित और अनुकूलित करने में सक्षम होंगे। आएँ शुरू करें!

## .NET के लिए Aspose.Words में टेक्स्ट इनपुट फॉर्म फ़ील्ड सुविधा सम्मिलित करने का परिचय

.NET के लिए Aspose.Words में इन्सर्ट टेक्स्ट इनपुट फॉर्म फ़ील्ड सुविधा आपको अपने वर्ड दस्तावेज़ों में प्रोग्रामेटिक रूप से टेक्स्ट इनपुट फॉर्म फ़ील्ड जोड़ने की अनुमति देती है। ये फॉर्म फ़ील्ड एक इंटरैक्टिव तत्व प्रदान करते हैं जहां उपयोगकर्ता कस्टम टेक्स्ट या डेटा दर्ज कर सकते हैं।

## सुविधा का उपयोग करने के लिए आवश्यकताओं को समझना

कार्यान्वयन के साथ आगे बढ़ने से पहले, सुनिश्चित करें कि आप निम्नलिखित आवश्यकताओं को पूरा करते हैं:

1. आपके प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words इंस्टॉल किया गया है।
2. C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
3. टेक्स्ट इनपुट फॉर्म फ़ील्ड सम्मिलित करने के लिए एक मौजूदा वर्ड दस्तावेज़ या एक नया दस्तावेज़।

सुनिश्चत करें कि सुचारू रूप से आगे बढ़ने के लिए आपके पास ये पूर्वावश्यकताएँ मौजूद हैं।

## C# स्रोत कोड का उपयोग करके इन्सर्ट टेक्स्ट इनपुट फॉर्म फ़ील्ड को लागू करने के लिए चरण-दर-चरण मार्गदर्शिका

दिए गए C# स्रोत कोड का उपयोग करके इन्सर्ट टेक्स्ट इनपुट फॉर्म फ़ील्ड सुविधा को लागू करने के लिए नीचे दिए गए चरणों का पालन करें:

### चरण 1: दस्तावेज़ और दस्तावेज़ निर्माता को आरंभ करना

आरंभ करने के लिए, दस्तावेज़ और दस्तावेज़ निर्माता को प्रारंभ करें। दस्तावेज़ बिल्डर .NET के लिए Aspose.Words द्वारा प्रदान किया गया एक शक्तिशाली उपकरण है जो हमें Word दस्तावेज़ों को प्रोग्रामेटिक रूप से बनाने और हेरफेर करने की अनुमति देता है। निम्नलिखित कोड स्निपेट का उपयोग करें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### चरण 2: टेक्स्ट इनपुट फॉर्म फ़ील्ड सम्मिलित करना

 इसके बाद, हम टेक्स्ट इनपुट फॉर्म फ़ील्ड को दस्तावेज़ में सम्मिलित करेंगे`InsertTextInput` तरीका। यह विधि विभिन्न मापदंडों को स्वीकार करती है, जिसमें फॉर्म फ़ील्ड का नाम, फॉर्म फ़ील्ड का प्रकार (इस मामले में,`TextFormFieldType.Regular`), डिफ़ॉल्ट मान और अधिकतम लंबाई। यहाँ एक उदाहरण है:

```csharp
builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);
```

उपरोक्त कोड "टेक्स्टइनपुट" नाम के साथ एक टेक्स्ट इनपुट फॉर्म फ़ील्ड सम्मिलित करेगा, जो "हैलो" का एक डिफ़ॉल्ट मान होगा, और कोई अधिकतम लंबाई प्रतिबंध नहीं होगा।

### चरण 3: दस्तावेज़ सहेजना

 टेक्स्ट इनपुट फॉर्म फ़ील्ड डालने के बाद, दस्तावेज़ को वांछित स्थान पर सहेजें`Save` तरीका। उचित फ़ाइल पथ प्रदान करना सुनिश्चित करें:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```

यह कोड दस्तावेज़ को निर्दिष्ट स्थान पर सम्मिलित टेक्स्ट इनपुट फॉर्म फ़ील्ड के साथ सहेजेगा।

### .NET के लिए Aspose.Words का उपयोग करके टेक्स्ट इनपुट फॉर्म फ़ील्ड सम्मिलित करने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में टेक्स्ट इनपुट फॉर्म फ़ील्ड को सम्मिलित और अनुकूलित करना सफलतापूर्वक सीख लिया है। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# स्रोत कोड का उपयोग करके, अब आप अपने दस्तावेज़ों में इंटरैक्टिव तत्व जोड़ सकते हैं, जिससे उपयोगकर्ता कस्टम टेक्स्ट या डेटा दर्ज कर सकते हैं।

### वर्ड दस्तावेज़ में टेक्स्ट इनपुट फॉर्म फ़ील्ड सम्मिलित करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में इन्सर्ट टेक्स्ट इनपुट फॉर्म फ़ील्ड सुविधा का उद्देश्य क्या है?

उ: .NET के लिए Aspose.Words में इन्सर्ट टेक्स्ट इनपुट फॉर्म फ़ील्ड सुविधा आपको अपने वर्ड दस्तावेज़ों में प्रोग्रामेटिक रूप से टेक्स्ट इनपुट फॉर्म फ़ील्ड जोड़ने की अनुमति देती है। ये फॉर्म फ़ील्ड उपयोगकर्ताओं को सीधे दस्तावेज़ के भीतर कस्टम टेक्स्ट या डेटा दर्ज करने में सक्षम बनाते हैं, जो उन्हें इंटरैक्टिव फॉर्म, सर्वेक्षण या प्रश्नावली बनाने के लिए आदर्श बनाते हैं।

#### प्रश्न: इन्सर्ट टेक्स्ट इनपुट फॉर्म फ़ील्ड सुविधा का उपयोग करने के लिए पूर्वापेक्षाएँ क्या हैं?

उ: इन्सर्ट टेक्स्ट इनपुट फॉर्म फ़ील्ड सुविधा को लागू करने से पहले, आपको निम्नलिखित पूर्वापेक्षाएँ सुनिश्चित करनी होंगी:
1. आपके प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words इंस्टॉल किया गया है।
2. C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
3. एक मौजूदा वर्ड दस्तावेज़ या एक नया दस्तावेज़ जहां आप टेक्स्ट इनपुट फॉर्म फ़ील्ड सम्मिलित करना चाहते हैं।

#### प्रश्न: मैं टेक्स्ट इनपुट फॉर्म फ़ील्ड को कैसे अनुकूलित करूं?

 उ: आप कॉल करते समय विशिष्ट पैरामीटर प्रदान करके टेक्स्ट इनपुट फॉर्म फ़ील्ड को कस्टमाइज़ कर सकते हैं`InsertTextInput`तरीका। उदाहरण के लिए, आप आवश्यकतानुसार प्रपत्र फ़ील्ड के लिए नाम, डिफ़ॉल्ट मान और अधिकतम लंबाई निर्धारित कर सकते हैं।

#### प्रश्न: क्या मैं एक ही दस्तावेज़ में एकाधिक टेक्स्ट इनपुट फ़ॉर्म फ़ील्ड सम्मिलित कर सकता हूँ?

 उ: हाँ, आप एक ही दस्तावेज़ में एकाधिक टेक्स्ट इनपुट फ़ॉर्म फ़ील्ड सम्मिलित कर सकते हैं। बस कॉल करें`InsertTextInput` एकाधिक प्रपत्र फ़ील्ड जोड़ने के लिए विभिन्न नामों और कॉन्फ़िगरेशन वाली विधि।

#### प्रश्न: उपयोगकर्ता दस्तावेज़ में टेक्स्ट इनपुट फॉर्म फ़ील्ड के साथ कैसे इंटरैक्ट कर सकते हैं?

उ: एक बार टेक्स्ट इनपुट फॉर्म फ़ील्ड दस्तावेज़ में डालने के बाद, उपयोगकर्ता फॉर्म फ़ील्ड पर क्लिक कर सकते हैं और कस्टम टेक्स्ट इनपुट करने के लिए टाइप करना शुरू कर सकते हैं। प्रपत्र फ़ील्ड उन्हें सीधे दस्तावेज़ के भीतर सामग्री को संपादित करने की अनुमति देता है।