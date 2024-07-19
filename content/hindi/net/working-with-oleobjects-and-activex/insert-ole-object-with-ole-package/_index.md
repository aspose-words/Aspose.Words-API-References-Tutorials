---
title: OLE पैकेज के साथ Word में OLE ऑब्जेक्ट डालें
linktitle: OLE पैकेज के साथ Word में OLE ऑब्जेक्ट डालें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में OLE पैकेज के साथ OLE ऑब्जेक्ट सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

नीचे C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है, जो यह दर्शाती है कि .NET के लिए Aspose.Words का उपयोग करके OLE पैकेज के साथ Word में OLE ऑब्जेक्ट कैसे सम्मिलित किया जाए।

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

## चरण 3: OLE पैकेज के साथ OLE ऑब्जेक्ट डालें
 दस्तावेज़ जनरेटर का उपयोग करें`InsertOleObject`दस्तावेज़ में OLE पैकेज के साथ OLE ऑब्जेक्ट डालने की विधि। डेटा स्ट्रीम, ऑब्जेक्ट प्रकार, प्रदर्शन विकल्प और अन्य आवश्यक सेटिंग्स निर्दिष्ट करें।

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## चरण 4: दस्तावेज़ सहेजें
 दस्तावेज़ का उपयोग करें`Save` दस्तावेज़ को फ़ाइल में सहेजने की विधि.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### .NET के लिए Aspose.Words के साथ OLE पैकेज के साथ OLE ऑब्जेक्ट सम्मिलित करने के लिए नमूना स्रोत कोड

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

यह .NET के लिए Aspose.Words के साथ OLE पैकेज के साथ OLE ऑब्जेक्ट डालने के लिए एक पूर्ण कोड नमूना है। इस कोड को अपने प्रोजेक्ट में एकीकृत करने के लिए आवश्यक संदर्भों को आयात करना सुनिश्चित करें और पहले बताए गए चरणों का पालन करें।

## निष्कर्ष

अंत में, हमने .NET के लिए Aspose.Words का उपयोग करके OLE पैकेज वाले Word दस्तावेज़ में OLE ऑब्जेक्ट सम्मिलित करने के लिए चरण-दर-चरण मार्गदर्शिका का अध्ययन किया है।

इन चरणों का पालन करके, आप .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ों में OLE पैकेज के साथ OLE ऑब्जेक्ट को सफलतापूर्वक सम्मिलित करने में सक्षम होंगे। वांछित परिणाम प्राप्त करने के लिए आवश्यक संदर्भों को आयात करना सुनिश्चित करें और निर्देशों का सावधानीपूर्वक पालन करें।

### OLE पैकेज के साथ वर्ड में OLE ऑब्जेक्ट सम्मिलित करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करने के लिए मुझे कौन से क्रेडेंशियल आयात करने की आवश्यकता है?

उत्तर: .NET के लिए Aspose.Words का उपयोग करने के लिए, आपको निम्नलिखित संदर्भ आयात करने होंगे:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### प्रश्न: नया दस्तावेज़ और दस्तावेज़ जनरेटर कैसे बनाएं?

 उत्तर: आप इसका उपयोग करके एक नया दस्तावेज़ बना सकते हैं`Document` क्लास और एक दस्तावेज़ बिल्डर का उपयोग कर`DocumentBuilder` वर्ग, जैसा कि नीचे दिखाया गया है:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### प्रश्न: दस्तावेज़ में OLE पैकेज के साथ OLE ऑब्जेक्ट कैसे सम्मिलित करें?

 उत्तर: का प्रयोग करें`InsertOleObject` दस्तावेज़ निर्माता की विधि (`DocumentBuilder`) दस्तावेज़ में OLE पैकेज के साथ OLE ऑब्जेक्ट डालने के लिए। डेटा स्ट्रीम, ऑब्जेक्ट प्रकार, प्रदर्शन विकल्प और अन्य आवश्यक सेटिंग्स निर्दिष्ट करें। यहाँ एक उदाहरण दिया गया है :

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### प्रश्न: दस्तावेज़ को कैसे सुरक्षित करें?

 उत्तर: दस्तावेज़ का उपयोग करें`Save`दस्तावेज़ को फ़ाइल में सहेजने की विधि। यहाँ एक उदाहरण दिया गया है:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### प्रश्न: क्या आप .NET के लिए Aspose.Words के साथ OLE पैकेज के साथ OLE ऑब्जेक्ट सम्मिलित करने का पूर्ण उदाहरण प्रदान कर सकते हैं?

उत्तर: यहाँ .NET के लिए Aspose.Words का उपयोग करके OLE पैकेज के साथ OLE ऑब्जेक्ट सम्मिलित करने के लिए एक पूर्ण नमूना कोड है। इस कोड को अपने प्रोजेक्ट में एकीकृत करने के लिए आवश्यक संदर्भों को आयात करना सुनिश्चित करें और पहले बताए गए चरणों का पालन करें:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

यह Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में OLE पैकेज के साथ OLE ऑब्जेक्ट डालने पर हमारा ट्यूटोरियल समाप्त करता है। आवश्यक संदर्भों को आयात करने और इस कोड को अपने प्रोजेक्ट में एकीकृत करने के लिए वर्णित चरणों का पालन करने के लिए स्वतंत्र महसूस करें। यदि आपके पास कोई और प्रश्न है, तो कृपया हमसे संपर्क करने में संकोच न करें।