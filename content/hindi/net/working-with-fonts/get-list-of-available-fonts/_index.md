---
title: उपलब्ध फ़ॉन्ट्स की सूची प्राप्त करें
linktitle: उपलब्ध फ़ॉन्ट्स की सूची प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: इस ट्यूटोरियल में, .NET के लिए Aspose.Words में उपलब्ध फ़ॉन्ट्स की सूची प्राप्त करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-fonts/get-list-of-available-fonts/
---
इस ट्यूटोरियल में, हम बताएंगे कि .NET के लिए Aspose.Words में उपलब्ध फ़ॉन्ट की सूची कैसे प्राप्त करें। उपलब्ध फ़ॉन्ट की सूची आपको बताती है कि आप अपने दस्तावेज़ों में कौन से फ़ॉन्ट का उपयोग कर सकते हैं। हम आपको अपने .NET प्रोजेक्ट में कोड को समझने और लागू करने में मदद करने के लिए चरण-दर-चरण मार्गदर्शन करेंगे।

## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित वस्तुएं हैं:
- C# प्रोग्रामिंग भाषा का कार्यसाधक ज्ञान
- आपके प्रोजेक्ट में .NET के लिए Aspose.Words लाइब्रेरी स्थापित है

## चरण 1: दस्तावेज़ निर्देशिका निर्धारित करें
 सबसे पहले, आपको अपने वर्ड डॉक्यूमेंट के स्थान पर डायरेक्टरी पथ सेट करना होगा।`"YOUR DOCUMENT DIRECTORY"` कोड में उचित पथ के साथ.

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: फ़ॉन्ट स्रोत कॉन्फ़िगर करें
 इसके बाद, हम इसका एक उदाहरण बनाएंगे`FontSettings` और मौजूदा फ़ॉन्ट स्रोतों का उपयोग कर प्राप्त करें`GetFontsSources()` विधि। हम फ़ॉन्ट्स वाले फ़ोल्डर को निर्दिष्ट करके एक नया फ़ॉन्ट स्रोत भी जोड़ेंगे।

```csharp
// फ़ॉन्ट स्रोत कॉन्फ़िगर करें
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// नया फ़ॉन्ट स्रोत जोड़ें
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## चरण 3: उपलब्ध फ़ॉन्ट्स की सूची प्राप्त करें
 अब हम उपलब्ध फ़ॉन्ट्स को ब्राउज़ करेंगे`GetAvailableFonts()` पहले अद्यतन फ़ॉन्ट स्रोत पर विधि।

```csharp
// उपलब्ध फ़ॉन्ट्स की सूची प्राप्त करें
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

// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// एक नया फ़ोल्डर स्रोत जोड़ें जो Aspose.Words को फ़ॉन्ट्स के लिए निम्नलिखित फ़ोल्डर को खोजने का निर्देश देगा।
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// हमारे फ़ॉन्ट वाले कस्टम फ़ोल्डर को मौजूदा फ़ॉन्ट स्रोतों की सूची में जोड़ें।
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
इस ट्यूटोरियल में, हमने देखा कि .NET के लिए Aspose.Words में उपलब्ध फ़ॉन्ट की सूची कैसे प्राप्त करें। इससे आपको पता चलता है कि आप अपने दस्तावेज़ों में कौन से फ़ॉन्ट का उपयोग कर सकते हैं। अपनी ज़रूरतों के हिसाब से उपयुक्त फ़ॉन्ट चुनने के लिए इस सुविधा का इस्तेमाल करने में संकोच न करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words में उपलब्ध फ़ॉन्ट्स की सूची कैसे प्राप्त कर सकता हूं?

 उत्तर: Aspose.Words में उपलब्ध फ़ॉन्ट्स की सूची प्राप्त करने के लिए, आप इसका उपयोग कर सकते हैं`FontsProvider` वर्ग और`GetAvailableFonts` विधि। यह विधि आपके सिस्टम पर स्थापित सभी फ़ॉन्ट्स की सूची लौटाएगी।

#### प्रश्न: क्या मैं Aspose.Words में उपलब्ध फ़ॉन्ट्स की सूची को कुछ मानदंडों के आधार पर फ़िल्टर कर सकता हूँ?

उत्तर: हाँ, आप विशिष्ट मानदंडों का उपयोग करके Aspose.Words में उपलब्ध फ़ॉन्ट की सूची को फ़िल्टर कर सकते हैं। उदाहरण के लिए, आप फ़ॉन्ट को परिवार, शैली या भाषा के अनुसार फ़िल्टर कर सकते हैं।

#### प्रश्न: मैं अपने वर्ड दस्तावेज़ों में उपलब्ध फ़ॉन्ट्स की सूची का उपयोग कैसे कर सकता हूँ?

 उत्तर: अपने वर्ड दस्तावेज़ों में उपलब्ध फ़ॉन्ट्स की सूची का उपयोग करने के लिए, आप सूची ब्राउज़ कर सकते हैं और फ़ॉन्ट्स के तरीकों और गुणों का उपयोग करके उपयुक्त फ़ॉन्ट्स का चयन कर सकते हैं।`FontSettings` Aspose.Words में वर्ग.