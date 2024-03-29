---
title: वर्ड डॉक्यूमेंट में ओले ऑब्जेक्ट डालें
linktitle: वर्ड डॉक्यूमेंट में ओले ऑब्जेक्ट डालें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके वर्ड दस्तावेज़ में OLE ऑब्जेक्ट सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-oleobjects-and-activex/insert-ole-object/
---

नीचे दिए गए C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है, जो बताती है कि .NET के लिए Aspose.Words का उपयोग करके वर्ड दस्तावेज़ में OLE ऑब्जेक्ट कैसे सम्मिलित किया जाए।

## चरण 1: आवश्यक संदर्भ आयात करें
शुरू करने से पहले, सुनिश्चित करें कि आपने अपने प्रोजेक्ट में .NET के लिए Aspose.Words का उपयोग करने के लिए आवश्यक संदर्भ आयात कर लिए हैं। इसमें Aspose.Words लाइब्रेरी को आयात करना और आपकी स्रोत फ़ाइल में आवश्यक नामस्थान जोड़ना शामिल है।

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## चरण 2: एक नया दस्तावेज़ और दस्तावेज़ जनरेटर बनाएं
 इस चरण में, हम इसका उपयोग करके एक नया दस्तावेज़ बनाएंगे`Document` क्लास और एक दस्तावेज़ निर्माता का उपयोग कर रहा हूँ`DocumentBuilder` कक्षा।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: एक OLE ऑब्जेक्ट डालें
 दस्तावेज़ निर्माता का उपयोग करें`InsertOleObject` दस्तावेज़ में OLE ऑब्जेक्ट सम्मिलित करने की विधि। OLE ऑब्जेक्ट URL, ऑब्जेक्ट प्रकार, प्रदर्शन विकल्प और अन्य आवश्यक सेटिंग्स निर्दिष्ट करें।

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", सत्य, सत्य, शून्य);
```

## चरण 4: दस्तावेज़ सहेजें
 दस्तावेज़ का उपयोग करें`Save` दस्तावेज़ को फ़ाइल में सहेजने की विधि।

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### .NET के लिए Aspose.Words के साथ OLE ऑब्जेक्ट डालने के लिए उदाहरण स्रोत कोड

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", सत्य, सत्य, शून्य);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

यह .NET के लिए Aspose.Words के साथ OLE ऑब्जेक्ट डालने के लिए एक संपूर्ण कोड नमूना है। आवश्यक संदर्भ आयात करना सुनिश्चित करें और इस कोड को अपने प्रोजेक्ट में एकीकृत करने के लिए पहले बताए गए चरणों का पालन करें।

## निष्कर्ष

निष्कर्षतः, किसी Word दस्तावेज़ में OLE ऑब्जेक्ट सम्मिलित करना .NET के लिए Aspose.Words द्वारा प्रस्तुत एक शक्तिशाली सुविधा है। इस लाइब्रेरी का उपयोग करके, आप आसानी से OLE ऑब्जेक्ट्स जैसे HTML फ़ाइलें, एक्सेल स्प्रेडशीट, पावरपॉइंट प्रेजेंटेशन इत्यादि को अपने वर्ड दस्तावेज़ों में एम्बेड कर सकते हैं।

इस आलेख में, हमने C# में स्रोत कोड को समझाने के लिए एक चरण-दर-चरण मार्गदर्शिका देखी है जो बताती है कि किसी Word दस्तावेज़ में OLE ऑब्जेक्ट कैसे सम्मिलित किया जाए। हमने आवश्यक संदर्भों को कवर किया, एक नया दस्तावेज़ और एक दस्तावेज़ जनरेटर बनाना, और एक OLE ऑब्जेक्ट सम्मिलित करने और दस्तावेज़ को सहेजने के चरण।

### किसी Word दस्तावेज़ में OLE ऑब्जेक्ट सम्मिलित करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करने के लिए मुझे किन क्रेडेंशियल्स को आयात करने की आवश्यकता है?

उ: .NET के लिए Aspose.Words का उपयोग करने के लिए, आपको निम्नलिखित संदर्भ आयात करने होंगे:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### प्रश्न: नया दस्तावेज़ और दस्तावेज़ जनरेटर कैसे बनाएं?

 उ: आप इसका उपयोग करके एक नया दस्तावेज़ बना सकते हैं`Document` क्लास और एक दस्तावेज़ निर्माता का उपयोग कर रहा हूँ`DocumentBuilder` कक्षा, जैसा कि नीचे दिखाया गया है:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### प्रश्न: दस्तावेज़ में OLE ऑब्जेक्ट कैसे डालें?

 ए: का प्रयोग करें`InsertOleObject`दस्तावेज़ निर्माता की विधि (`DocumentBuilder`) दस्तावेज़ में OLE ऑब्जेक्ट डालने के लिए। OLE ऑब्जेक्ट URL, ऑब्जेक्ट प्रकार, प्रदर्शन विकल्प और अन्य आवश्यक सेटिंग्स निर्दिष्ट करें। यहाँ एक उदाहरण है :

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", सत्य, सत्य, शून्य);
```

#### प्रश्न: दस्तावेज़ को कैसे सहेजें?

 उत्तर: दस्तावेज़ का उपयोग करें`Save` दस्तावेज़ को फ़ाइल में सहेजने की विधि। यहाँ एक उदाहरण है :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### प्रश्न: क्या आप .NET के लिए Aspose.Words के साथ OLE ऑब्जेक्ट डालने का एक पूरा उदाहरण प्रदान कर सकते हैं?

उ: यहां .NET के लिए Aspose.Words के साथ OLE ऑब्जेक्ट सम्मिलित करने के लिए एक संपूर्ण नमूना कोड है। आवश्यक संदर्भ आयात करना सुनिश्चित करें और इस कोड को अपने प्रोजेक्ट में एकीकृत करने के लिए पहले वर्णित चरणों का पालन करें:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", सत्य, सत्य, शून्य);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
