---
title: फ़ॉन्ट्स की सूचनाएं प्राप्त करें
linktitle: फ़ॉन्ट्स की सूचनाएं प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करते समय लुप्त या प्रतिस्थापित फ़ॉन्ट सूचनाएं प्राप्त करने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/working-with-fonts/receive-notifications-of-fonts/
---

इस ट्यूटोरियल में, हम आपको बताएंगे कि .NET के लिए Aspose.Words का उपयोग करते समय फ़ॉन्ट सूचनाएं कैसे प्राप्त करें। फ़ॉन्ट सूचनाएं आपको अपने दस्तावेज़ों में गुम या प्रतिस्थापित फ़ॉन्ट का पता लगाने और प्रबंधित करने देती हैं। हम आपके .NET प्रोजेक्ट में कोड को समझने और लागू करने में आपकी सहायता के लिए चरण-दर-चरण कदम उठाएंगे।

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

## चरण 2: दस्तावेज़ लोड करें और फ़ॉन्ट सेटिंग्स कॉन्फ़िगर करें
 इसके बाद, हम इसका उपयोग करके दस्तावेज़ लोड करेंगे`Document` क्लास बनाएं और फ़ॉन्ट सेटिंग्स का उपयोग करके कॉन्फ़िगर करें`FontSettings` कक्षा। हम फ़ॉन्ट गुम होने की स्थिति में उपयोग के लिए डिफ़ॉल्ट फ़ॉन्ट सेट करेंगे।

```csharp
// दस्तावेज़ लोड करें और फ़ॉन्ट सेटिंग्स कॉन्फ़िगर करें
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

## चरण 3: अधिसूचना हैंडलर सेट करें
इसके बाद, हम इसे लागू करके एक अधिसूचना हैंडलर को परिभाषित करेंगे`IWarningCallback` इंटरफेस। यह हमें दस्तावेज़ सहेजते समय फ़ॉन्ट चेतावनियाँ एकत्र करने की अनुमति देगा।

```csharp
// अधिसूचना हैंडलर को परिभाषित करें
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc. WarningCallback = callback;
```

## चरण 4: फ़ॉन्ट सेटिंग लागू करें और दस्तावेज़ सहेजें
अंत में, हम दस्तावेज़ में फ़ॉन्ट सेटिंग्स लागू करेंगे और इसे सहेजेंगे। किसी भी फ़ॉन्ट चेतावनी को अधिसूचना हैंडलर द्वारा कैप्चर किया जाएगा जिसे हमने पहले परिभाषित किया था।

```csharp
// फ़ॉन्ट सेटिंग लागू करें और दस्तावेज़ सहेजें
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");
```

### .NET के लिए Aspose.Words का उपयोग करके फ़ॉन्ट्स की सूचनाएं प्राप्त करने के लिए नमूना स्रोत कोड 
```csharp

// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// हम किसी भी गुम फ़ॉन्ट के मामले में उपयोग करने के लिए डिफ़ॉल्ट फ़ॉन्ट चुन सकते हैं।
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
// परीक्षण के लिए हम Aspose.Words को केवल उस फ़ोल्डर में फ़ॉन्ट देखने के लिए सेट करेंगे जो मौजूद नहीं है। चूँकि Aspose.Words नहीं होगा
// निर्दिष्ट निर्देशिका में कोई भी फ़ॉन्ट ढूंढें, फिर रेंडरिंग के दौरान दस्तावेज़ में फ़ॉन्ट को डिफ़ॉल्ट के साथ उप-अनुकूलित किया जाएगा
// फ़ॉन्टSettings.DefaultFontName के अंतर्गत निर्दिष्ट फ़ॉन्ट। हम अपने कॉलबैक का उपयोग करके इस सबसुइट को चुन सकते हैं।
fontSettings.SetFontsFolder(string.Empty, false);
//IWarningCallback को कार्यान्वित करने वाला एक नया वर्ग बनाएं जो दस्तावेज़ सहेजने के दौरान उत्पन्न किसी भी चेतावनी को एकत्रित करता है।
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");

```

## निष्कर्ष
इस ट्यूटोरियल में, हमने देखा कि .NET के लिए Aspose.Words का उपयोग करते समय फ़ॉन्ट सूचनाएं कैसे प्राप्त करें। फ़ॉन्ट सूचनाएं आपको अपने दस्तावेज़ों में गुम या प्रतिस्थापित फ़ॉन्ट का पता लगाने और प्रबंधित करने देती हैं। अपने दस्तावेज़ों में फ़ॉन्ट की एकरूपता सुनिश्चित करने और फ़ॉन्ट गुम होने की स्थिति में उचित कार्रवाई करने के लिए इस सुविधा का उपयोग करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words में गुम फ़ॉन्ट की सूचनाएं कैसे प्राप्त कर सकता हूं?

 उत्तर: Aspose.Words में गुम फ़ॉन्ट की सूचनाएं प्राप्त करने के लिए, आप इसका उपयोग कर सकते हैं`FontSettings` कक्षा और`FontSubstitutionCallback` आयोजन। दस्तावेज़ों को संसाधित करते समय गुम फ़ॉन्ट सामने आने पर सूचित करने के लिए आप कॉलबैक विधि सेट कर सकते हैं।

#### प्रश्न: मैं अपने Word दस्तावेज़ों में गुम फ़ॉन्ट्स से कैसे निपट सकता हूँ?

उ: अपने Word दस्तावेज़ों में गुम फ़ॉन्ट से निपटने के लिए, आप विभिन्न रणनीतियों का उपयोग कर सकते हैं। आप उस सिस्टम पर गायब फ़ॉन्ट इंस्टॉल कर सकते हैं जहां आप अपना Aspose.Words एप्लिकेशन चलाते हैं, या आप उपलब्ध वैकल्पिक फ़ॉन्ट के साथ लापता फ़ॉन्ट को प्रतिस्थापित कर सकते हैं।

#### प्रश्न: क्या Aspose.Words में प्रतिस्थापित फ़ॉन्ट सूचनाएं प्राप्त करना संभव है?

 उ: हां, Aspose.Words में प्रतिस्थापित फ़ॉन्ट सूचनाएं प्राप्त करना संभव है। जब दस्तावेज़ प्रसंस्करण के दौरान फ़ॉन्ट प्रतिस्थापित किए जाते हैं, तो आपको इसका उपयोग करके सूचित किया जा सकता है`FontSubstitutionCallback` घटना और पाठ की उपस्थिति को समायोजित करने के लिए उचित कार्रवाई करें।

#### प्रश्न: जब Aspose.Words में फ़ॉन्ट प्रतिस्थापित किए जाते हैं तो मैं टेक्स्ट की उपस्थिति को एक समान कैसे रख सकता हूं?

उ: जब फ़ॉन्ट प्रतिस्थापित किया जाता है तो पाठ की उपस्थिति में स्थिरता बनाए रखने के लिए, आप पाठ स्वरूपण गुणों, जैसे फ़ॉन्ट आकार, शैली और रंग को समायोजित कर सकते हैं। आप ऐसे स्थानापन्न फ़ॉन्ट का उपयोग करने पर भी विचार कर सकते हैं जो देखने में मूल फ़ॉन्ट के समान हों।