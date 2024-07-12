---
title: स्ट्रीम का उपयोग करके पुराने ऑब्जेक्ट को आइकन के रूप में डालें
linktitle: स्ट्रीम का उपयोग करके पुराने ऑब्जेक्ट को आइकन के रूप में डालें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ स्ट्रीम का उपयोग करके एक OLE ऑब्जेक्ट को आइकन के रूप में सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

नीचे C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है, जो यह दर्शाती है कि .NET के लिए Aspose.Words के साथ स्ट्रीम का उपयोग करके OLE ऑब्जेक्ट को आइकन के रूप में कैसे सम्मिलित किया जाए।

## चरण 1: आवश्यक संदर्भ आयात करें
आरंभ करने से पहले, सुनिश्चित करें कि आपने अपने प्रोजेक्ट में .NET के लिए Aspose.Words का उपयोग करने के लिए आवश्यक संदर्भ आयात किए हैं। इसमें Aspose.Words लाइब्रेरी को आयात करना और अपनी स्रोत फ़ाइल में आवश्यक नामस्थान जोड़ना शामिल है।

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## चरण 2: नया दस्तावेज़ और दस्तावेज़ जनरेटर बनाएँ
 इस चरण में, हम इसका उपयोग करके एक नया दस्तावेज़ बनाएंगे।`Document` क्लास और एक दस्तावेज़ बिल्डर का उपयोग कर`DocumentBuilder` कक्षा।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: स्ट्रीम से आइकन के रूप में OLE ऑब्जेक्ट डालें
 दस्तावेज़ बिल्डर का उपयोग करें`InsertOleObjectAsIcon` दस्तावेज़ में स्ट्रीम से आइकन के रूप में OLE ऑब्जेक्ट डालने की विधि। डेटा स्ट्रीम, ऑब्जेक्ट प्रकार, आइकन पथ और एम्बेडेड ऑब्जेक्ट नाम निर्दिष्ट करें।

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## चरण 4: दस्तावेज़ सहेजें
 दस्तावेज़ का उपयोग करें`Save` दस्तावेज़ को फ़ाइल में सहेजने की विधि.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### .NET के लिए Aspose.Words के साथ स्ट्रीम का उपयोग करके एक OLE ऑब्जेक्ट को आइकन के रूप में सम्मिलित करने के लिए उदाहरण स्रोत कोड

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

यह .NET के लिए Aspose.Words के साथ स्ट्रीम का उपयोग करके एक OLE ऑब्जेक्ट को आइकन के रूप में सम्मिलित करने के लिए एक पूर्ण कोड नमूना है। इस कोड को अपने प्रोजेक्ट में एकीकृत करने के लिए आवश्यक संदर्भों को आयात करना सुनिश्चित करें और पहले बताए गए चरणों का पालन करें।

## निष्कर्ष

ऊपर दिए गए चरण-दर-चरण गाइड में बताया गया है कि Aspose.Words for .NET के साथ फ़्लो का उपयोग करके Word दस्तावेज़ में आइकन के रूप में OLE ऑब्जेक्ट कैसे डालें। वर्णित चरणों का पालन करके, आप इस कार्यक्षमता को अपने प्रोजेक्ट में एकीकृत करने में सक्षम होंगे। आवश्यक संदर्भों को आयात करना सुनिश्चित करें, एक नया दस्तावेज़ और दस्तावेज़ जनरेटर बनाएँ, स्ट्रीम से आइकन के रूप में OLE ऑब्जेक्ट डालें, फिर दस्तावेज़ को सहेजें। प्रारंभिक बिंदु के रूप में प्रदान किए गए नमूना कोड का उपयोग करें और इसे अपनी आवश्यकताओं के अनुसार अनुकूलित करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्र. .NET के लिए Aspose.Words का उपयोग करने के लिए आवश्यक संदर्भों को कैसे आयात करें?

A. आवश्यक संदर्भ आयात करने के लिए, आपको इन चरणों का पालन करना होगा:

 निम्नलिखित जोड़ें`using` आपके स्रोत फ़ाइल के शीर्ष पर कथन:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
सुनिश्चित करें कि आपने अपने प्रोजेक्ट में Aspose.Words लाइब्रेरी को जोड़ा है।

#### प्र. .NET के लिए Aspose.Words का उपयोग करके नया दस्तावेज़ और दस्तावेज़ बिल्डर कैसे बनाएं?

A. नया दस्तावेज़ और दस्तावेज़ जनरेटर बनाने के लिए, आप इन चरणों का पालन कर सकते हैं:

 उपयोग`Document` नया दस्तावेज़ बनाने के लिए क्लास:

```csharp
Document doc = new Document();
```
 उपयोग`DocumentBuilder`पहले से बनाए गए दस्तावेज़ से संबद्ध दस्तावेज़ बिल्डर बनाने के लिए क्लास:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### प्र. .NET के लिए Aspose.Words का उपयोग करके स्ट्रीम से आइकन के रूप में OLE ऑब्जेक्ट कैसे सम्मिलित करें?

A. किसी स्ट्रीम से आइकन के रूप में OLE ऑब्जेक्ट सम्मिलित करने के लिए, आप इन चरणों का पालन कर सकते हैं:

 उपयोग`InsertOleObjectAsIcon` OLE ऑब्जेक्ट सम्मिलित करने के लिए दस्तावेज़ जनरेटर की विधि:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### प्रश्न: दस्तावेज़ को फ़ाइल में कैसे सेव करें?

A.  दस्तावेज़ को फ़ाइल में सहेजने के लिए, आप इसका उपयोग कर सकते हैं`Save` गंतव्य पथ निर्दिष्ट करने वाली दस्तावेज़ की विधि:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### प्र. मैं अपने प्रोजेक्ट में स्ट्रीम से आइकन के रूप में OLE ऑब्जेक्ट सम्मिलित करने के लिए कोड कैसे एम्बेड करूं?

A. किसी स्ट्रीम से आइकन के रूप में OLE ऑब्जेक्ट को अपने प्रोजेक्ट में सम्मिलित करने के लिए कोड को एम्बेड करने के लिए, इन चरणों का पालन करें:
-  उपयुक्त जोड़कर आवश्यक संदर्भ आयात करें`using` बयान.
-  का उपयोग करके एक नया दस्तावेज़ और एक दस्तावेज़ बिल्डर बनाएँ`Document`और`DocumentBuilder` कक्षाएं.
- किसी स्ट्रीम से आइकन के रूप में OLE ऑब्जेक्ट सम्मिलित करने के लिए कोड का उपयोग करें।
-  दस्तावेज़ को सहेजें`Save` उचित गंतव्य पथ के साथ विधि।

इन चरणों का पालन करके, आप .NET के लिए Aspose.Words का उपयोग करके स्ट्रीम से आइकन के रूप में OLE ऑब्जेक्ट को सफलतापूर्वक सम्मिलित करने में सक्षम होंगे। निर्देशों का पालन करना सुनिश्चित करें और वांछित परिणाम प्राप्त करने के लिए आवश्यक संदर्भ आयात करें।