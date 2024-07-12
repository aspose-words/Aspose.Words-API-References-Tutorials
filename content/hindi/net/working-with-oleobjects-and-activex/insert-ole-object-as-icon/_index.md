---
title: वर्ड डॉक्यूमेंट में पुराने ऑब्जेक्ट को आइकन के रूप में डालें
linktitle: वर्ड डॉक्यूमेंट में पुराने ऑब्जेक्ट को आइकन के रूप में डालें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ वर्ड दस्तावेज़ में आइकन के रूप में OLE ऑब्जेक्ट सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

नीचे C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है, जो यह दर्शाती है कि .NET के लिए Aspose.Words का उपयोग करके वर्ड दस्तावेज़ में आइकन के रूप में OLE ऑब्जेक्ट कैसे सम्मिलित किया जाए।

## चरण 1: आवश्यक संदर्भ आयात करें
आरंभ करने से पहले, सुनिश्चित करें कि आपने अपने प्रोजेक्ट में .NET के लिए Aspose.Words का उपयोग करने के लिए आवश्यक संदर्भ आयात किए हैं। इसमें Aspose.Words लाइब्रेरी को आयात करना और अपनी स्रोत फ़ाइल में आवश्यक नामस्थान जोड़ना शामिल है।

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## चरण 2: नया दस्तावेज़ और दस्तावेज़ जनरेटर बनाएँ
 इस चरण में, हम इसका उपयोग करके एक नया दस्तावेज़ बनाएंगे।`Document` क्लास और एक दस्तावेज़ बिल्डर का उपयोग कर`DocumentBuilder` कक्षा।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: एक OLE ऑब्जेक्ट को आइकन के रूप में सम्मिलित करें
 दस्तावेज़ बिल्डर का उपयोग करें`InsertOleObjectAsIcon`दस्तावेज़ में एक आइकन के रूप में OLE ऑब्जेक्ट सम्मिलित करने की विधि। OLE फ़ाइल पथ, डिस्प्ले फ़्लैग, आइकन पथ और एम्बेडेड ऑब्जेक्ट नाम निर्दिष्ट करें।

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## चरण 4: दस्तावेज़ सहेजें
 दस्तावेज़ का उपयोग करें`Save` दस्तावेज़ को फ़ाइल में सहेजने की विधि.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### .NET के लिए Aspose.Words के साथ एक OLE ऑब्जेक्ट को आइकन के रूप में सम्मिलित करने के लिए उदाहरण स्रोत कोड

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

यह .NET के लिए Aspose.Words के साथ एक OLE ऑब्जेक्ट को आइकन के रूप में सम्मिलित करने के लिए एक पूर्ण कोड नमूना है। इस कोड को अपने प्रोजेक्ट में एकीकृत करने के लिए आवश्यक संदर्भों को आयात करना सुनिश्चित करें और पहले बताए गए चरणों का पालन करें।

## निष्कर्ष

अंत में, हमने .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में एक आइकन के रूप में OLE ऑब्जेक्ट सम्मिलित करने के लिए चरण-दर-चरण मार्गदर्शिका का पता लगाया।

इन चरणों का पालन करके, आप Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ों में एक आइकन के रूप में OLE ऑब्जेक्ट को सफलतापूर्वक सम्मिलित करने में सक्षम होंगे। वांछित परिणाम प्राप्त करने के लिए आवश्यक संदर्भों को आयात करना सुनिश्चित करें और निर्देशों का सावधानीपूर्वक पालन करें।

### वर्ड डॉक्यूमेंट में OLE ऑब्जेक्ट को आइकॉन के रूप में सम्मिलित करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्र. .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में एक आइकन के रूप में OLE ऑब्जेक्ट सम्मिलित करने के लिए किन संदर्भों की आवश्यकता होती है?

उत्तर: .NET के लिए Aspose.Words का उपयोग करने के लिए आपको अपने प्रोजेक्ट में निम्नलिखित संदर्भों को आयात करना होगा:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### प्र. .NET के लिए Aspose.Words में नया दस्तावेज़ और दस्तावेज़ जनरेटर कैसे बनाएं?

 उत्तर: आप इसका उपयोग करके एक नया दस्तावेज़ बना सकते हैं`Document` क्लास और एक दस्तावेज़ बिल्डर का उपयोग कर`DocumentBuilder` क्लास. यहाँ एक उदाहरण है:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### प्रश्न: दस्तावेज़ में आइकन के रूप में OLE ऑब्जेक्ट कैसे सम्मिलित करें?

 उत्तर: डॉक्यूमेंट बिल्डर का उपयोग करें`InsertOleObjectAsIcon` OLE ऑब्जेक्ट को आइकन के रूप में सम्मिलित करने की विधि। OLE फ़ाइल पथ, डिस्प्ले फ़्लैग, आइकन पथ और एम्बेडेड ऑब्जेक्ट नाम निर्दिष्ट करें। यहाँ एक उदाहरण दिया गया है:

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### प्रश्न: OLE ऑब्जेक्ट को आइकन के रूप में सम्मिलित करके दस्तावेज़ को कैसे सेव करें?

 उत्तर: दस्तावेज़ का उपयोग करें`Save` दस्तावेज़ को फ़ाइल में सहेजने की विधि। यहाँ एक उदाहरण दिया गया है:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```