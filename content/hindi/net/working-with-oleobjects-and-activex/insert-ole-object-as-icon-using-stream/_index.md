---
title: स्ट्रीम का उपयोग करके ओले ऑब्जेक्ट को आइकन के रूप में डालें
linktitle: स्ट्रीम का उपयोग करके ओले ऑब्जेक्ट को आइकन के रूप में डालें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ एक स्ट्रीम का उपयोग करके एक OLE ऑब्जेक्ट को एक आइकन के रूप में सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

नीचे C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है, जो दर्शाती है कि .NET के लिए Aspose.Words के साथ एक स्ट्रीम का उपयोग करके एक OLE ऑब्जेक्ट को एक आइकन के रूप में कैसे सम्मिलित किया जाए।

## चरण 1: आवश्यक संदर्भ आयात करें
शुरू करने से पहले, सुनिश्चित करें कि आपने अपने प्रोजेक्ट में .NET के लिए Aspose.Words का उपयोग करने के लिए आवश्यक संदर्भ आयात कर लिए हैं। इसमें Aspose.Words लाइब्रेरी को आयात करना और आपकी स्रोत फ़ाइल में आवश्यक नामस्थान जोड़ना शामिल है।

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## चरण 2: एक नया दस्तावेज़ और दस्तावेज़ जनरेटर बनाएं
 इस चरण में, हम इसका उपयोग करके एक नया दस्तावेज़ बनाएंगे`Document` क्लास और एक दस्तावेज़ निर्माता का उपयोग कर रहा हूँ`DocumentBuilder` कक्षा।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: एक स्ट्रीम से एक आइकन के रूप में एक OLE ऑब्जेक्ट डालें
 दस्तावेज़ निर्माता का उपयोग करें`InsertOleObjectAsIcon` दस्तावेज़ में एक स्ट्रीम से एक आइकन के रूप में एक OLE ऑब्जेक्ट सम्मिलित करने की विधि। डेटा स्ट्रीम, ऑब्जेक्ट प्रकार, आइकन पथ और एम्बेडेड ऑब्जेक्ट नाम निर्दिष्ट करें।

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## चरण 4: दस्तावेज़ सहेजें
 दस्तावेज़ का उपयोग करें`Save` दस्तावेज़ को फ़ाइल में सहेजने की विधि।

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### .NET के लिए Aspose.Words के साथ एक स्ट्रीम का उपयोग करके एक OLE ऑब्जेक्ट को एक आइकन के रूप में सम्मिलित करने के लिए उदाहरण स्रोत कोड

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

यह .NET के लिए Aspose.Words के साथ एक स्ट्रीम का उपयोग करके एक OLE ऑब्जेक्ट को एक आइकन के रूप में सम्मिलित करने के लिए एक संपूर्ण कोड नमूना है। आवश्यक संदर्भ आयात करना सुनिश्चित करें और इस कोड को अपने प्रोजेक्ट में एकीकृत करने के लिए पहले बताए गए चरणों का पालन करें।

## निष्कर्ष

उपरोक्त चरण-दर-चरण मार्गदर्शिका बताती है कि .NET के लिए Aspose.Words के साथ प्रवाह का उपयोग करके किसी Word दस्तावेज़ में एक OLE ऑब्जेक्ट को एक आइकन के रूप में कैसे सम्मिलित किया जाए। वर्णित चरणों का पालन करके, आप इस कार्यक्षमता को अपने प्रोजेक्ट में एकीकृत करने में सक्षम होंगे। आवश्यक संदर्भ आयात करना सुनिश्चित करें, एक नया दस्तावेज़ और दस्तावेज़ जनरेटर बनाएं, स्ट्रीम से एक आइकन के रूप में OLE ऑब्जेक्ट डालें, फिर दस्तावेज़ को सहेजें। प्रारंभिक बिंदु के रूप में दिए गए नमूना कोड का उपयोग करें और इसे अपनी आवश्यकताओं के अनुसार अनुकूलित करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्र. .NET के लिए Aspose.Words का उपयोग करने के लिए आवश्यक संदर्भ कैसे आयात करें?

A. आवश्यक संदर्भ आयात करने के लिए, आपको इन चरणों का पालन करना होगा:

 निम्नलिखित जोड़ें`using` आपकी स्रोत फ़ाइल के शीर्ष पर कथन:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
सुनिश्चित करें कि आपने Aspose.Words लाइब्रेरी को अपने प्रोजेक्ट में जोड़ा है।

#### प्र. .NET के लिए Aspose.Words का उपयोग करके एक नया दस्तावेज़ और दस्तावेज़ निर्माता कैसे बनाएं?

A. एक नया दस्तावेज़ और दस्तावेज़ जनरेटर बनाने के लिए, आप इन चरणों का पालन कर सकते हैं:

 उपयोग`Document` नया दस्तावेज़ बनाने के लिए कक्षा:

```csharp
Document doc = new Document();
```
 उपयोग`DocumentBuilder`पहले बनाए गए दस्तावेज़ से संबद्ध दस्तावेज़ बिल्डर बनाने के लिए क्लास:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### प्र. .NET के लिए Aspose.Words का उपयोग करके किसी स्ट्रीम से एक OLE ऑब्जेक्ट को एक आइकन के रूप में कैसे सम्मिलित करें?

A. किसी स्ट्रीम से किसी OLE ऑब्जेक्ट को आइकन के रूप में सम्मिलित करने के लिए, आप इन चरणों का पालन कर सकते हैं:

 उपयोग`InsertOleObjectAsIcon` OLE ऑब्जेक्ट सम्मिलित करने के लिए दस्तावेज़ जनरेटर की विधि:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### प्र. दस्तावेज़ को फ़ाइल में कैसे सहेजें?

A.  दस्तावेज़ को फ़ाइल में सहेजने के लिए, आप इसका उपयोग कर सकते हैं`Save` गंतव्य पथ निर्दिष्ट करने वाले दस्तावेज़ की विधि:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### प्र. मैं अपने प्रोजेक्ट में एक स्ट्रीम से एक आइकन के रूप में एक OLE ऑब्जेक्ट डालने के लिए कोड कैसे एम्बेड करूं?

A. अपने प्रोजेक्ट में एक स्ट्रीम से एक आइकन के रूप में OLE ऑब्जेक्ट डालने के लिए कोड एम्बेड करने के लिए, इन चरणों का पालन करें:
-  उपयुक्त जोड़कर आवश्यक संदर्भ आयात करें`using` बयान.
-  का उपयोग करके एक नया दस्तावेज़ और एक दस्तावेज़ निर्माता बनाएं`Document` और`DocumentBuilder` कक्षाएं.
- किसी स्ट्रीम से आइकन के रूप में OLE ऑब्जेक्ट सम्मिलित करने के लिए कोड का उपयोग करें।
-  का उपयोग करके दस्तावेज़ को सहेजें`Save` उचित गंतव्य पथ के साथ विधि.

इन चरणों का पालन करके, आप .NET के लिए Aspose.Words का उपयोग करके एक स्ट्रीम से एक आइकन के रूप में एक OLE ऑब्जेक्ट को सफलतापूर्वक सम्मिलित करने में सक्षम होंगे। वांछित परिणाम प्राप्त करने के लिए निर्देशों का पालन करना और आवश्यक संदर्भ आयात करना सुनिश्चित करें।