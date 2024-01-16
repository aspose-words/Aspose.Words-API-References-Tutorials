---
title: रेंडर करते समय डिफ़ॉल्ट फ़ॉन्ट निर्दिष्ट करें
linktitle: रेंडर करते समय डिफ़ॉल्ट फ़ॉन्ट निर्दिष्ट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को प्रस्तुत करते समय डिफ़ॉल्ट फ़ॉन्ट निर्दिष्ट करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/working-with-fonts/specify-default-font-when-rendering/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ प्रस्तुत करते समय डिफ़ॉल्ट फ़ॉन्ट निर्दिष्ट करने की चरण-दर-चरण प्रक्रिया के बारे में बताएंगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को समझने और अपनी परियोजनाओं में लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत तक, आप जानेंगे कि .NET के लिए Aspose.Words का उपयोग करके अपने दस्तावेज़ों को प्रस्तुत करते समय उपयोग करने के लिए एक डिफ़ॉल्ट फ़ॉन्ट कैसे निर्दिष्ट किया जाए।

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें
सबसे पहले, आपको अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करना होगा। यह वह स्थान है जहां आप अपने संपादित प्रस्तुत दस्तावेज़ को सहेजना चाहते हैं। "आपकी दस्तावेज़ निर्देशिका" को उचित पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: रेंडर करने के लिए दस्तावेज़ लोड करें
 इसके बाद, आपको इसका उपयोग करके रेंडर करने के लिए दस्तावेज़ को लोड करना होगा`Document` कक्षा। सही दस्तावेज़ पथ निर्दिष्ट करना सुनिश्चित करें।

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## चरण 3: डिफ़ॉल्ट फ़ॉन्ट सेट करें
 अब आप इसका एक उदाहरण बनाकर रेंडर करते समय उपयोग करने के लिए डिफ़ॉल्ट फ़ॉन्ट निर्दिष्ट कर सकते हैं`FontSettings` क्लास और सेटिंग`DefaultFontName` की संपत्ति`DefaultFontSubstitution` पर आपत्ति है`DefaultFontSubstitution` वस्तु`SubstitutionSettings` का`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## चरण 4: प्रस्तुत दस्तावेज़ को सहेजें
 अंत में, आप रेंडर किए गए दस्तावेज़ को इसका उपयोग करके एक फ़ाइल में सहेज सकते हैं`Save()` की विधि`Document` कक्षा। सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### .NET के लिए Aspose.Words का उपयोग करके रेंडर करते समय डिफ़ॉल्ट फ़ॉन्ट निर्दिष्ट करने के लिए नमूना स्रोत कोड 

```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// यदि यहां परिभाषित डिफ़ॉल्ट फ़ॉन्ट रेंडरिंग के दौरान नहीं मिल पाता है
// इसके स्थान पर मशीन पर निकटतम फ़ॉन्ट का उपयोग किया जाता है।
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को प्रस्तुत करते समय डिफ़ॉल्ट फ़ॉन्ट को कैसे निर्दिष्ट किया जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने दस्तावेज़ों को प्रस्तुत करते समय उपयोग करने के लिए आसानी से एक डिफ़ॉल्ट फ़ॉन्ट सेट कर सकते हैं। Aspose.Words आपके दस्तावेज़ों में फ़ॉन्ट के साथ वर्ड प्रोसेसिंग के लिए एक शक्तिशाली और लचीली एपीआई प्रदान करता है। इस ज्ञान के साथ, आप अपने दस्तावेज़ों के प्रतिपादन को अपनी विशिष्ट आवश्यकताओं के अनुसार नियंत्रित और अनुकूलित कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: Aspose.Words में PDF में कनवर्ट करते समय मैं एक डिफ़ॉल्ट फ़ॉन्ट कैसे निर्दिष्ट कर सकता हूं?

 उत्तर: Aspose.Words में PDF में कनवर्ट करते समय एक डिफ़ॉल्ट फ़ॉन्ट निर्दिष्ट करने के लिए, आप इसका उपयोग कर सकते हैं`PdfOptions` कक्षा और सेट करें`DefaultFontName` वांछित फ़ॉन्ट के नाम की संपत्ति।

#### प्रश्न: यदि पीडीएफ में कनवर्ट करते समय डिफ़ॉल्ट फ़ॉन्ट उपलब्ध नहीं है तो क्या होगा?

उ: यदि पीडीएफ में परिवर्तित करते समय निर्दिष्ट डिफ़ॉल्ट फ़ॉन्ट उपलब्ध नहीं है, तो Aspose.Words परिवर्तित दस्तावेज़ में पाठ को प्रदर्शित करने के लिए एक प्रतिस्थापन फ़ॉन्ट का उपयोग करेगा। इससे मूल फ़ॉन्ट से दिखने में थोड़ा अंतर हो सकता है।

#### प्रश्न: क्या मैं अन्य आउटपुट स्वरूपों, जैसे DOCX या HTML के लिए एक डिफ़ॉल्ट फ़ॉन्ट निर्दिष्ट कर सकता हूँ?

उत्तर: हाँ, आप उपयुक्त रूपांतरण विकल्पों का उपयोग करके और प्रत्येक प्रारूप के लिए संबंधित संपत्ति सेट करके अन्य आउटपुट प्रारूपों जैसे DOCX या HTML के लिए एक डिफ़ॉल्ट फ़ॉन्ट निर्दिष्ट कर सकते हैं।

#### प्रश्न: मैं Aspose.Words में निर्दिष्ट डिफ़ॉल्ट फ़ॉन्ट की जांच कैसे कर सकता हूं?

 उ: Aspose.Words में निर्दिष्ट डिफ़ॉल्ट फ़ॉन्ट की जांच करने के लिए, आप इसका उपयोग कर सकते हैं`DefaultFontName` की संपत्ति`PdfOptions` क्लास बनाएं और कॉन्फ़िगर किए गए फ़ॉन्ट का नाम पुनः प्राप्त करें।

#### प्रश्न: क्या दस्तावेज़ के प्रत्येक अनुभाग के लिए एक अलग डिफ़ॉल्ट फ़ॉन्ट निर्दिष्ट करना संभव है?

उ: हाँ, प्रत्येक अनुभाग के लिए विशिष्ट स्वरूपण विकल्पों का उपयोग करके दस्तावेज़ के प्रत्येक अनुभाग के लिए एक अलग डिफ़ॉल्ट फ़ॉन्ट निर्दिष्ट करना संभव है। हालाँकि, इसके लिए Aspose.Words सुविधाओं का उपयोग करके दस्तावेज़ में अधिक उन्नत हेरफेर की आवश्यकता होगी।