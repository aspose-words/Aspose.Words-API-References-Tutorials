---
title: प्रत्यय के बिना प्रतिस्थापन प्राप्त करें
linktitle: प्रत्यय के बिना प्रतिस्थापन प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: इस ट्यूटोरियल में, सीखें कि .NET के लिए Aspose.Words के साथ किसी Word दस्तावेज़ में प्रत्यय रहित ओवरराइड कैसे प्राप्त करें।
type: docs
weight: 10
url: /hi/net/working-with-fonts/get-substitution-without-suffixes/
---

इस ट्यूटोरियल में, हम आपको दिखाने जा रहे हैं कि .NET के लिए Aspose.Words लाइब्रेरी का उपयोग करके किसी Word दस्तावेज़ में प्रत्यय के बिना ओवरराइड कैसे प्राप्त करें। दस्तावेज़ों को प्रदर्शित या मुद्रित करते समय फ़ॉन्ट प्रतिस्थापन समस्याओं को हल करने के लिए प्रत्यय के बिना प्रतिस्थापन का उपयोग किया जाता है। हम आपके .NET प्रोजेक्ट में कोड को समझने और लागू करने में आपकी सहायता के लिए चरण-दर-चरण कदम उठाएंगे।

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

## चरण 2: दस्तावेज़ लोड करें और प्रत्यय के बिना प्रतिस्थापन कॉन्फ़िगर करें
 इसके बाद, हम इसका उपयोग करके दस्तावेज़ लोड करेंगे`Document` का उपयोग करके वर्ग बनाएं और प्रत्यय रहित प्रतिस्थापनों को कॉन्फ़िगर करें`DocumentSubstitutionWarnings` कक्षा। हम फ़ॉन्ट वाले फ़ोल्डर को निर्दिष्ट करके एक फ़ॉन्ट स्रोत भी जोड़ेंगे।

```csharp
// दस्तावेज़ लोड करें और प्रत्ययों के बिना प्रतिस्थापन कॉन्फ़िगर करें
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## चरण 3: दस्तावेज़ सहेजें
अंत में, हम दस्तावेज़ को नो-प्रत्यय ओवरराइड लागू करके सहेजेंगे।

```csharp
// दस्तावेज़ सहेजें
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### .NET के लिए Aspose.Words का उपयोग करके प्रत्यय के बिना प्रतिस्थापन प्राप्त करने के लिए नमूना स्रोत कोड 
```csharp

// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## निष्कर्ष
इस ट्यूटोरियल में, हमने देखा कि .NET के लिए Aspose.Words के साथ किसी Word दस्तावेज़ में प्रत्यय के बिना ओवरराइड कैसे प्राप्त करें। फ़ॉन्ट प्रतिस्थापन समस्याओं को हल करने के लिए प्रत्यय के बिना प्रतिस्थापन उपयोगी होते हैं। अपने दस्तावेज़ों के प्रदर्शन और मुद्रण को बेहतर बनाने के लिए बेझिझक इस सुविधा का उपयोग करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: Aspose.Words फ़ॉन्ट प्रतिस्थापन में प्रत्यय क्यों जोड़ता है?

उत्तर: Aspose.Words मूल फ़ॉन्ट और प्रतिस्थापित फ़ॉन्ट के बीच टकराव से बचने के लिए फ़ॉन्ट प्रतिस्थापन में प्रत्यय जोड़ता है। यह दस्तावेज़ों को परिवर्तित और हेरफेर करते समय अधिकतम अनुकूलता सुनिश्चित करने में मदद करता है।

#### प्रश्न: मैं Aspose.Words में प्रत्यय के बिना फ़ॉन्ट प्रतिस्थापन कैसे प्राप्त कर सकता हूं?

 उ: Aspose.Words में प्रत्यय के बिना फ़ॉन्ट प्रतिस्थापन को पुनः प्राप्त करने के लिए, आप इसका उपयोग कर सकते हैं`FontSubstitutionSettings` कक्षा और`RemoveSuffixes` संपत्ति। इस प्रॉपर्टी को यहां सेट कर रहा हूं`true` अतिरिक्त प्रत्यय के बिना फ़ॉन्ट प्रतिस्थापन मिलेगा।

#### प्रश्न: क्या Aspose.Words में फ़ॉन्ट प्रतिस्थापन में प्रत्यय जोड़ना अक्षम करना संभव है?

उत्तर: नहीं, Aspose.Words में फ़ॉन्ट प्रतिस्थापन में प्रत्यय जोड़ना अक्षम करना संभव नहीं है। दस्तावेज़ अनुकूलता और एकरूपता सुनिश्चित करने के लिए प्रत्यय डिफ़ॉल्ट रूप से जोड़े जाते हैं।

#### प्रश्न: मैं Aspose.Words में फ़ॉन्ट प्रतिस्थापनों में अवांछित प्रत्ययों को कैसे फ़िल्टर कर सकता हूँ?

 उत्तर: Aspose.Words में फ़ॉन्ट प्रतिस्थापनों में अवांछित प्रत्ययों को फ़िल्टर करने के लिए, आप स्ट्रिंग प्रोसेसिंग तकनीकों का उपयोग कर सकते हैं, जैसे कि`Replace` या`Substring` उन विशिष्ट प्रत्ययों को हटाने की विधियाँ जिन्हें आप शामिल नहीं करना चाहते हैं।