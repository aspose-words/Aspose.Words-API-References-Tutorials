---
title: वर्ड डॉक्यूमेंट में वीबीए प्रोजेक्ट बनाएं
linktitle: वर्ड डॉक्यूमेंट में वीबीए प्रोजेक्ट बनाएं
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: इस ट्यूटोरियल में, सीखें कि .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में VBA प्रोजेक्ट कैसे बनाएं।
type: docs
weight: 10
url: /hi/net/working-with-vba-macros/create-vba-project/
---

इस ट्यूटोरियल में, हम आपको बताने जा रहे हैं कि .NET के लिए Aspose.Words लाइब्रेरी का उपयोग करके किसी Word दस्तावेज़ में VBA प्रोजेक्ट कैसे बनाया जाए। VBA प्रोजेक्ट बनाने से आप अपने Word दस्तावेज़ में कस्टम VBA कोड जोड़ सकते हैं। हम आपके .NET प्रोजेक्ट में कोड को समझने और लागू करने में आपकी सहायता के लिए चरण-दर-चरण कदम उठाएंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित चीज़ें हैं:
- C# प्रोग्रामिंग भाषा का कार्यसाधक ज्ञान
- आपके प्रोजेक्ट में .NET के लिए Aspose.Words लाइब्रेरी स्थापित है

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें
 सबसे पहले, आपको अपने Word दस्तावेज़ के स्थान पर निर्देशिका पथ सेट करना होगा। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उचित पथ के साथ कोड में।

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: एक नया VBA दस्तावेज़ और प्रोजेक्ट बनाएं
 इसके बाद, हम इंस्टेंटियेट करके एक नया दस्तावेज़ बनाएंगे`Document` क्लास और एक खाली वीबीए प्रोजेक्ट को इंस्टेंटिअट करके`VbaProject` कक्षा।

```csharp
// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();

//एक नया VBA प्रोजेक्ट बनाएं
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
```

## चरण 3: एक नया मॉड्यूल बनाएं और मैक्रो स्रोत कोड निर्दिष्ट करें।
 हम इंस्टेंटियेट करके एक नया मॉड्यूल बनाएंगे`VbaModule` वर्ग और मैक्रो नाम, प्रकार (प्रक्रियात्मक मॉड्यूल) और स्रोत कोड निर्दिष्ट करना।

```csharp
// एक नया मॉड्यूल बनाएं
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New Source Code";

// मॉड्यूल को VBA प्रोजेक्ट में जोड़ें
doc.VbaProject.Modules.Add(module);
```

## चरण 4: दस्तावेज़ सहेजें
अंत में, हम दस्तावेज़ को एक फ़ाइल में बनाए गए VBA प्रोजेक्ट के साथ सहेजेंगे।

```csharp
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");
```

### .NET के लिए Aspose.Words का उपयोग करके Vba प्रोजेक्ट बनाने के लिए नमूना स्रोत कोड 

```csharp

// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
// एक नया मॉड्यूल बनाएं और एक मैक्रो स्रोत कोड निर्दिष्ट करें।
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";
// VBA प्रोजेक्ट में मॉड्यूल जोड़ें।
doc.VbaProject.Modules.Add(module);
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");

```

## निष्कर्ष
इस ट्यूटोरियल में, हमने देखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में VBA प्रोजेक्ट कैसे बनाया जाता है। VBA प्रोजेक्ट बनाने से आप अपने Word दस्तावेज़ में VBA कोड जोड़ और अनुकूलित कर सकते हैं। कार्यों को स्वचालित करने या अपने Word दस्तावेज़ों में कस्टम कार्यक्षमता जोड़ने के लिए इस सुविधा का बेझिझक उपयोग करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: वर्ड दस्तावेज़ में वीबीए प्रोजेक्ट क्या है?

ए: वर्ड दस्तावेज़ में एक वीबीए प्रोजेक्ट कोड युक्त वीबीए मॉड्यूल का एक संग्रह है जिसका उपयोग कार्यों को स्वचालित करने, कस्टम कार्यक्षमता जोड़ने या वर्ड दस्तावेज़ में विशिष्ट संचालन करने के लिए किया जा सकता है।

#### प्रश्न: वर्ड दस्तावेज़ में वीबीए प्रोजेक्ट बनाने के लिए पूर्वापेक्षाएँ क्या हैं?

उ: इससे पहले कि आप किसी Word दस्तावेज़ में VBA प्रोजेक्ट बना सकें, आपको C# प्रोग्रामिंग भाषा का कार्यसाधक ज्ञान होना चाहिए। आपको अपने प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी को भी इंस्टॉल करना होगा।

#### प्रश्न: कोड में दस्तावेज़ निर्देशिका कैसे सेट करें?

 उत्तर: दिए गए कोड में, आपको प्रतिस्थापित करना होगा।`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका के लिए उपयुक्त पथ के साथ जहां आप अपने वर्ड दस्तावेज़ को वीबीए प्रोजेक्ट के साथ सहेजना चाहते हैं।

#### प्रश्न: वीबीए मॉड्यूल में मैक्रो सोर्स कोड कैसे निर्दिष्ट करें?

 ए: वीबीए मॉड्यूल में मैक्रो के स्रोत कोड को निर्दिष्ट करने के लिए, आप इसका उपयोग कर सकते हैं`SourceCode` की संपत्ति`VbaModule` क्लास को वीबीए कोड युक्त एक कैरेक्टर स्ट्रिंग निर्दिष्ट करके।

#### प्रश्न: क्या मैं किसी Word दस्तावेज़ में VBA प्रोजेक्ट में एकाधिक VBA मॉड्यूल जोड़ सकता हूँ?

उत्तर: हाँ, आप किसी Word दस्तावेज़ में किसी VBA प्रोजेक्ट में मल्टीपल इंस्टेंटियेट करके अनेक VBA मॉड्यूल जोड़ सकते हैं`VbaModule` ऑब्जेक्ट और उन्हें इसमें जोड़ना`Modules` का संग्रह`VbaProject` वस्तु। यह आपको बेहतर प्रबंधन और पुन: उपयोग के लिए अपने वीबीए कोड को विभिन्न मॉड्यूल में व्यवस्थित करने की अनुमति देता है।