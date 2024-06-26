---
title: फ़ॉन्ट फ़ोल्डर डिफ़ॉल्ट इंस्टेंस सेट करें
linktitle: फ़ॉन्ट फ़ोल्डर डिफ़ॉल्ट इंस्टेंस सेट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को प्रस्तुत करते समय डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डर सेट करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/working-with-fonts/set-fonts-folders-default-instance/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ प्रस्तुत करते समय डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डर सेट करने की चरण-दर-चरण प्रक्रिया के बारे में बताएंगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को समझने और अपनी परियोजनाओं में लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि .NET के लिए Aspose.Words का उपयोग करके अपने दस्तावेज़ों को प्रस्तुत करते समय उपयोग करने के लिए डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डर कैसे सेट करें।

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें
सबसे पहले, आपको अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करना होगा। यह वह स्थान है जहां आप अपने संपादित प्रस्तुत दस्तावेज़ को सहेजना चाहते हैं। "आपकी दस्तावेज़ निर्देशिका" को उचित पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डर सेट करें
 फिर आप इसका उपयोग करके डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डर सेट कर सकते हैं`FontSettings.DefaultInstance` कक्षा और`SetFontsFolder()`तरीका। उस फ़ॉन्ट फ़ोल्डर का पथ निर्दिष्ट करें जिसे आप डिफ़ॉल्ट फ़ोल्डर के रूप में उपयोग करना चाहते हैं।

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## चरण 3: रेंडर करने के लिए दस्तावेज़ लोड करें
 अब आप इसका उपयोग करके रेंडर करने के लिए दस्तावेज़ को लोड कर सकते हैं`Document` कक्षा। सही दस्तावेज़ पथ निर्दिष्ट करना सुनिश्चित करें।

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## चरण 4: प्रस्तुत दस्तावेज़ को सहेजें
 अंत में, आप रेंडर किए गए दस्तावेज़ को इसका उपयोग करके एक फ़ाइल में सहेज सकते हैं`Save()` की विधि`Document` कक्षा। सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### .NET के लिए Aspose.Words का उपयोग करके फ़ॉन्ट फ़ोल्डर डिफ़ॉल्ट इंस्टेंस सेट करने के लिए नमूना स्रोत कोड 

```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को प्रस्तुत करते समय डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डर कैसे सेट किया जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप आसानी से निर्दिष्ट कर सकते हैं कि आपके दस्तावेज़ों को प्रस्तुत करते समय फ़ॉन्ट के किस फ़ोल्डर को डिफ़ॉल्ट फ़ोल्डर के रूप में उपयोग करना है। Aspose.Words आपके दस्तावेज़ों में फ़ॉन्ट के साथ वर्ड प्रोसेसिंग के लिए एक शक्तिशाली और लचीली एपीआई प्रदान करता है। इस ज्ञान के साथ, आप अपने दस्तावेज़ों को अपनी विशिष्ट आवश्यकताओं के अनुसार प्रस्तुत करते समय उपयोग किए जाने वाले फ़ॉन्ट स्रोतों को नियंत्रित और अनुकूलित कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words में डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डर कैसे सेट कर सकता हूं?

 उ: Aspose.Words में डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डर सेट करने के लिए, आपको इसका उपयोग करना होगा`Fonts` कक्षा और`SetFontsFolders` कस्टम फ़ॉन्ट फ़ोल्डर स्थान निर्दिष्ट करने की विधि।

#### प्रश्न: क्या डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डर सेट करने से Aspose.Words के साथ संसाधित सभी Word दस्तावेज़ प्रभावित होते हैं?

उ: हाँ, डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डर सेट करने से Aspose.Words के साथ संसाधित सभी Word दस्तावेज़ प्रभावित होते हैं। एक बार जब आप डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डर सेट कर लेते हैं, तो Aspose.Words सभी दस्तावेज़ों में फ़ॉन्ट खोजने के लिए इन स्थानों का उपयोग करेगा।

#### प्रश्न: क्या मैं Aspose.Words में एकाधिक डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डर सेट कर सकता हूँ?

 उ: हाँ, आप Aspose.Words में एकाधिक डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डर सेट कर सकते हैं। आपको बस इसका उपयोग करके कस्टम फ़ॉन्ट फ़ोल्डरों के स्थान निर्दिष्ट करने की आवश्यकता है`SetFontsFolders` की विधि`Fonts` कक्षा।

#### प्रश्न: मैं वर्तमान में Aspose.Words में सेट किए गए डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डरों की जांच कैसे कर सकता हूं?

 उ: Aspose.Words में वर्तमान में परिभाषित डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डरों की जांच करने के लिए, आप इसका उपयोग कर सकते हैं`GetFolders` की विधि`Fonts` कॉन्फ़िगर किए गए फ़ॉन्ट फ़ोल्डरों के स्थान प्राप्त करने के लिए क्लास।

#### प्रश्न: क्या डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डर सेट करने से मुझे अपने वर्ड दस्तावेज़ों में कस्टम फ़ॉन्ट का उपयोग करने की अनुमति मिलती है?

उ: हां, डिफ़ॉल्ट फ़ॉन्ट फ़ोल्डर सेट करके, आप अपने वर्ड दस्तावेज़ों में कस्टम फ़ॉन्ट का उपयोग कर सकते हैं। आपको बस फ़ॉन्ट को निर्दिष्ट फ़ोल्डरों में रखना होगा और Aspose.Words दस्तावेज़ बनाते या उनमें हेरफेर करते समय उनका उपयोग करेगा।