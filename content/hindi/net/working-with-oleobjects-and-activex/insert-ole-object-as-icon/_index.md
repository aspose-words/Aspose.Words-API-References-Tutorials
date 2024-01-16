---
title: वर्ड दस्तावेज़ में आइकन के रूप में ओले ऑब्जेक्ट डालें
linktitle: वर्ड दस्तावेज़ में आइकन के रूप में ओले ऑब्जेक्ट डालें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ आइकन के रूप में वर्ड दस्तावेज़ में OLE ऑब्जेक्ट सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

नीचे दिए गए C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है, जो दर्शाती है कि .NET के लिए Aspose.Words का उपयोग करके वर्ड दस्तावेज़ में OLE ऑब्जेक्ट को आइकन के रूप में कैसे सम्मिलित किया जाए।

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

## चरण 3: एक OLE ऑब्जेक्ट को एक आइकन के रूप में डालें
 दस्तावेज़ निर्माता का उपयोग करें`InsertOleObjectAsIcon`दस्तावेज़ में एक आइकन के रूप में OLE ऑब्जेक्ट सम्मिलित करने की विधि। OLE फ़ाइल पथ, प्रदर्शन ध्वज, आइकन पथ और एम्बेडेड ऑब्जेक्ट नाम निर्दिष्ट करें।

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## चरण 4: दस्तावेज़ सहेजें
 दस्तावेज़ का उपयोग करें`Save` दस्तावेज़ को फ़ाइल में सहेजने की विधि।

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### .NET के लिए Aspose.Words के साथ एक आइकन के रूप में OLE ऑब्जेक्ट डालने के लिए उदाहरण स्रोत कोड

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

यह .NET के लिए Aspose.Words के साथ एक आइकन के रूप में OLE ऑब्जेक्ट डालने के लिए एक संपूर्ण कोड नमूना है। आवश्यक संदर्भ आयात करना सुनिश्चित करें और इस कोड को अपने प्रोजेक्ट में एकीकृत करने के लिए पहले बताए गए चरणों का पालन करें।

## निष्कर्ष

अंत में, हमने .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में एक OLE ऑब्जेक्ट को एक आइकन के रूप में सम्मिलित करने के लिए चरण-दर-चरण मार्गदर्शिका का पता लगाया।

इन चरणों का पालन करके, आप .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ों में एक OLE ऑब्जेक्ट को एक आइकन के रूप में सफलतापूर्वक सम्मिलित करने में सक्षम होंगे। वांछित परिणाम प्राप्त करने के लिए आवश्यक संदर्भ आयात करना और निर्देशों का सावधानीपूर्वक पालन करना सुनिश्चित करें।

### वर्ड दस्तावेज़ में आइकन के रूप में ओले ऑब्जेक्ट डालने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्र. .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में एक OLE ऑब्जेक्ट को एक आइकन के रूप में सम्मिलित करने के लिए किन संदर्भों की आवश्यकता है?

उ: .NET के लिए Aspose.Words का उपयोग करने के लिए आपको अपने प्रोजेक्ट में निम्नलिखित संदर्भ आयात करने की आवश्यकता है:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### प्र. .NET के लिए Aspose.Words में एक नया दस्तावेज़ और दस्तावेज़ जनरेटर कैसे बनाएं?

 उ: आप इसका उपयोग करके एक नया दस्तावेज़ बना सकते हैं`Document` क्लास और एक दस्तावेज़ निर्माता का उपयोग कर रहा हूँ`DocumentBuilder` कक्षा। यहाँ एक उदाहरण है :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### प्र. दस्तावेज़ में एक आइकन के रूप में OLE ऑब्जेक्ट कैसे सम्मिलित करें?

 उ: दस्तावेज़ निर्माता का उपयोग करें`InsertOleObjectAsIcon` एक OLE ऑब्जेक्ट को एक आइकन के रूप में सम्मिलित करने की विधि। OLE फ़ाइल पथ, प्रदर्शन ध्वज, आइकन पथ और एम्बेडेड ऑब्जेक्ट नाम निर्दिष्ट करें। यहाँ एक उदाहरण है :

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### प्र. आइकन के रूप में डाले गए OLE ऑब्जेक्ट के साथ दस्तावेज़ को कैसे सहेजें?

 उत्तर: दस्तावेज़ का उपयोग करें`Save` दस्तावेज़ को फ़ाइल में सहेजने की विधि। यहाँ एक उदाहरण है :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```