---
title: फ़ॉन्ट फ़ोल्डरों को प्राथमिकता के साथ सेट करें
linktitle: फ़ॉन्ट फ़ोल्डरों को प्राथमिकता के साथ सेट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को प्रस्तुत करते समय प्राथमिकता के साथ फ़ॉन्ट फ़ोल्डर सेट करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/working-with-fonts/set-fonts-folders-with-priority/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को प्रस्तुत करते समय फ़ॉन्ट फ़ोल्डरों को प्राथमिकता के साथ सेट करने की चरण-दर-चरण प्रक्रिया के बारे में बताएंगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को समझने और अपनी परियोजनाओं में लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि .NET के लिए Aspose.Words का उपयोग करके अपने दस्तावेज़ प्रस्तुत करते समय कस्टम खोज प्राथमिकता के साथ एकाधिक फ़ॉन्ट फ़ोल्डर कैसे निर्दिष्ट करें।

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें
सबसे पहले, आपको अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करना होगा। यह वह स्थान है जहां आप अपने संपादित प्रस्तुत दस्तावेज़ को सहेजना चाहते हैं। "आपकी दस्तावेज़ निर्देशिका" को उचित पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: फ़ॉन्ट फ़ोल्डरों को प्राथमिकता के साथ सेट करें
 फिर आप फ़ॉन्ट फ़ोल्डरों को प्राथमिकता के साथ सेट कर सकते हैं`FontSettings` कक्षा और`SetFontsSources()`तरीका। आप उदाहरणों का उपयोग करके एकाधिक फ़ॉन्ट स्रोत निर्दिष्ट कर सकते हैं`SystemFontSource` और`FolderFontSource`. इस उदाहरण में, हमने दो फ़ॉन्ट स्रोतों को परिभाषित किया है: डिफ़ॉल्ट सिस्टम फ़ॉन्ट स्रोत और 1 की प्राथमिकता वाला एक कस्टम फ़ॉन्ट फ़ोल्डर।

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## चरण 3: रेंडर करने के लिए दस्तावेज़ लोड करें
 अब आप इसका उपयोग करके रेंडर करने के लिए दस्तावेज़ को लोड कर सकते हैं`Document` कक्षा। सही दस्तावेज़ पथ निर्दिष्ट करना सुनिश्चित करें।

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## चरण 4: प्रस्तुत दस्तावेज़ को सहेजें
 अंत में, आप रेंडर किए गए दस्तावेज़ को इसका उपयोग करके एक फ़ाइल में सहेज सकते हैं`Save()` की विधि`Document` कक्षा। सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### .NET के लिए Aspose.Words का उपयोग करके प्राथमिकता वाले फ़ॉन्ट फ़ोल्डर सेट करने के लिए नमूना स्रोत कोड 
```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को प्रस्तुत करते समय फ़ॉन्ट फ़ोल्डरों को प्राथमिकता के साथ कैसे सेट किया जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने दस्तावेज़ों को प्रस्तुत करते समय कस्टम खोज प्राथमिकता के साथ आसानी से कई फ़ॉन्ट फ़ोल्डर निर्दिष्ट कर सकते हैं। Aspose.Words आपके दस्तावेज़ों में फ़ॉन्ट के साथ वर्ड प्रोसेसिंग के लिए एक शक्तिशाली और लचीली एपीआई प्रदान करता है। इस ज्ञान के साथ, आप अपने दस्तावेज़ों को अपनी विशिष्ट आवश्यकताओं के अनुसार प्रस्तुत करते समय उपयोग किए जाने वाले फ़ॉन्ट स्रोतों को नियंत्रित और अनुकूलित कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words में फ़ॉन्ट फ़ोल्डरों को प्राथमिकता के साथ कैसे सेट कर सकता हूं?

 उत्तर: Aspose.Words में फ़ॉन्ट फ़ोल्डरों को प्राथमिकता के साथ सेट करने के लिए, आप इसका उपयोग कर सकते हैं`SetFontsFoldersWithPriority` की विधि`Fonts` फ़ॉन्ट फ़ोल्डर स्थानों और उनकी प्राथमिकता के क्रम को निर्दिष्ट करके वर्ग।

#### प्रश्न: यदि एक फ़ॉन्ट विभिन्न प्राथमिकता वाले कई फ़ोल्डरों में मौजूद है तो क्या होगा?

उ: यदि कोई फ़ॉन्ट अलग-अलग प्राथमिकता वाले कई फ़ोल्डरों में मौजूद है, तो दस्तावेज़ों को संसाधित करते समय Aspose.Words सर्वोच्च प्राथमिकता वाले फ़ोल्डर से संस्करण का उपयोग करेगा।

#### प्रश्न: क्या मैं Aspose.Words में समान प्राथमिकता वाले एकाधिक फ़ॉन्ट फ़ोल्डर निर्दिष्ट कर सकता हूं?

उ: हाँ, आप Aspose.Words में समान प्राथमिकता वाले एकाधिक फ़ॉन्ट फ़ोल्डर निर्दिष्ट कर सकते हैं। आपके दस्तावेज़ों में फ़ॉन्ट खोजते समय Aspose.Words उन सभी पर समान प्राथमिकता के साथ विचार करेगा।

#### प्रश्न: मैं Aspose.Words में प्राथमिकता के साथ परिभाषित फ़ॉन्ट फ़ोल्डरों की जांच कैसे कर सकता हूं?

 उत्तर: Aspose.Words में प्राथमिकता के साथ परिभाषित फ़ॉन्ट फ़ोल्डरों की जांच करने के लिए, आप इसका उपयोग कर सकते हैं`GetFolders` की विधि`Fonts` प्राथमिकता क्रम सहित कॉन्फ़िगर किए गए फ़ॉन्ट फ़ोल्डरों की सूची प्राप्त करने के लिए क्लास।

#### प्रश्न: Aspose.Words में फ़ॉन्ट फ़ोल्डरों को प्राथमिकता के साथ सेट करने का क्या उपयोग है?

उत्तर: Aspose.Words में प्राथमिकता के साथ फ़ॉन्ट फ़ोल्डर सेट करने से आप अपने Word दस्तावेज़ों में फ़ॉन्ट के खोज क्रम को नियंत्रित कर सकते हैं। इससे आपको यह सुनिश्चित करने में मदद मिलती है कि आपके इच्छित फ़ॉन्ट का उपयोग किया जाता है और अवांछित फ़ॉन्ट प्रतिस्थापन समस्याओं से बचा जाता है।