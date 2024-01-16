---
title: उपलब्ध फ़ॉन्ट्स की सूची प्राप्त करें
linktitle: उपलब्ध फ़ॉन्ट्स की सूची प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: इस ट्यूटोरियल में, जानें कि .NET के लिए Aspose.Words में उपलब्ध फ़ॉन्ट की सूची कैसे प्राप्त करें।
type: docs
weight: 10
url: /hi/net/working-with-fonts/get-list-of-available-fonts/
---
इस ट्यूटोरियल में, हम बताएंगे कि .NET के लिए Aspose.Words में उपलब्ध फ़ॉन्ट की सूची कैसे प्राप्त करें। उपलब्ध फ़ॉन्ट की सूची आपको यह बताती है कि आप अपने दस्तावेज़ों में कौन से फ़ॉन्ट का उपयोग कर सकते हैं। हम आपके .NET प्रोजेक्ट में कोड को समझने और लागू करने में आपकी सहायता के लिए चरण-दर-चरण कदम उठाएंगे।

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

## चरण 2: फ़ॉन्ट स्रोतों को कॉन्फ़िगर करें
 इसके बाद, हम इसका एक उदाहरण बनाएंगे`FontSettings` और का उपयोग करके मौजूदा फ़ॉन्ट स्रोत प्राप्त करें`GetFontsSources()` तरीका। हम फ़ॉन्ट वाले फ़ोल्डर को निर्दिष्ट करके एक नया फ़ॉन्ट स्रोत भी जोड़ेंगे।

```csharp
// फ़ॉन्ट स्रोत कॉन्फ़िगर करें
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// एक नया फ़ॉन्ट स्रोत जोड़ें
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## चरण 3: उपलब्ध फ़ॉन्ट की सूची प्राप्त करें
 अब हम उपलब्ध फ़ॉन्ट्स का उपयोग करके ब्राउज़ करेंगे`GetAvailableFonts()` पहले अद्यतन फ़ॉन्ट स्रोत पर विधि।

```csharp
// उपलब्ध फ़ॉन्ट की सूची प्राप्त करें
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### .NET के लिए Aspose.Words का उपयोग करके उपलब्ध फ़ॉन्ट्स की सूची प्राप्त करने के लिए नमूना स्रोत कोड 

```csharp

// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// एक नया फ़ोल्डर स्रोत जोड़ें जो Aspose.Words को फ़ॉन्ट के लिए निम्नलिखित फ़ोल्डर खोजने का निर्देश देगा।
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// मौजूदा फ़ॉन्ट स्रोतों की सूची में वह कस्टम फ़ोल्डर जोड़ें जिसमें हमारे फ़ॉन्ट शामिल हैं।
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## निष्कर्ष
इस ट्यूटोरियल में, हमने देखा कि .NET के लिए Aspose.Words में उपलब्ध फ़ॉन्ट की सूची कैसे प्राप्त करें। इससे आपको पता चलता है कि आप अपने दस्तावेज़ों में कौन से फ़ॉन्ट का उपयोग कर सकते हैं। अपनी आवश्यकताओं के लिए उपयुक्त फ़ॉन्ट चुनने के लिए बेझिझक इस सुविधा का उपयोग करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words में उपलब्ध फ़ॉन्ट की सूची कैसे पुनः प्राप्त कर सकता हूं?

 उ: Aspose.Words में उपलब्ध फ़ॉन्ट की सूची पुनः प्राप्त करने के लिए, आप इसका उपयोग कर सकते हैं`FontsProvider` कक्षा और`GetAvailableFonts` तरीका। यह विधि आपके सिस्टम पर स्थापित सभी फ़ॉन्ट की एक सूची लौटा देगी।

#### प्रश्न: क्या मैं Aspose.Words में कुछ मानदंडों के आधार पर उपलब्ध फ़ॉन्ट की सूची को फ़िल्टर कर सकता हूँ?

उ: हां, आप विशिष्ट मानदंडों का उपयोग करके Aspose.Words में उपलब्ध फ़ॉन्ट की सूची को फ़िल्टर कर सकते हैं। उदाहरण के लिए, आप परिवार, शैली या भाषा के आधार पर फ़ॉन्ट फ़िल्टर कर सकते हैं।

#### प्रश्न: मैं अपने वर्ड दस्तावेजों में उपलब्ध फ़ॉन्ट्स की सूची का उपयोग कैसे कर सकता हूं?

 उ: अपने वर्ड दस्तावेज़ों में उपलब्ध फ़ॉन्ट की सूची का उपयोग करने के लिए, आप सूची ब्राउज़ कर सकते हैं और विधियों और गुणों का उपयोग करके उपयुक्त फ़ॉन्ट का चयन कर सकते हैं`FontSettings` Aspose.Words में कक्षा।