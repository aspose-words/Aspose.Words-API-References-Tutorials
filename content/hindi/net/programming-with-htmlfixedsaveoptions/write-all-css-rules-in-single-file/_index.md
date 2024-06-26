---
title: सभी सीएसएस नियमों को एक फ़ाइल में लिखें
linktitle: सभी सीएसएस नियमों को एक फ़ाइल में लिखें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ सभी CSS नियमों को एक ही फ़ाइल में लिखकर किसी Word दस्तावेज़ को निश्चित HTML में परिवर्तित करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

किसी Word दस्तावेज़ को C# एप्लिकेशन में निश्चित HTML में परिवर्तित करते समय, आप बेहतर संगठन और पोर्टेबिलिटी के लिए सभी CSS नियमों को एक फ़ाइल में समेकित करना चाह सकते हैं। .NET के लिए Aspose.Words लाइब्रेरी के साथ, आप HtmlFixedSaveOptions सेव विकल्पों का उपयोग करके इस कार्यक्षमता को आसानी से निर्दिष्ट कर सकते हैं। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको सेव विकल्प HtmlFixedSaveOptions का उपयोग करके एक फ़ाइल में सभी CSS नियमों को लिखकर किसी Word दस्तावेज़ को निश्चित HTML में परिवर्तित करने के लिए .NET C# स्रोत कोड के लिए Aspose.Words का उपयोग करने के तरीके के बारे में बताएंगे।

## Aspose.Words लाइब्रेरी को समझना

कोड में गोता लगाने से पहले, .NET के लिए Aspose.Words लाइब्रेरी को समझना महत्वपूर्ण है। Aspose.Words .NET सहित विभिन्न प्लेटफार्मों में Word दस्तावेज़ों को बनाने, संपादित करने, परिवर्तित करने और सुरक्षित करने के लिए एक शक्तिशाली लाइब्रेरी है। यह दस्तावेज़ों में हेरफेर करने के लिए कई सुविधाएँ प्रदान करता है, जैसे टेक्स्ट सम्मिलित करना, फ़ॉर्मेटिंग बदलना, अनुभाग जोड़ना और बहुत कुछ।

## Word दस्तावेज़ लोड हो रहा है

पहला कदम उस वर्ड दस्तावेज़ को लोड करना है जिसे आप निश्चित HTML में कनवर्ट करना चाहते हैं। दस्तावेज़ को स्रोत फ़ाइल से लोड करने के लिए दस्तावेज़ वर्ग का उपयोग करें। यहाँ एक उदाहरण है :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

इस उदाहरण में, हम दस्तावेज़ निर्देशिका में स्थित दस्तावेज़ "Document.docx" लोड करते हैं।

## बैकअप विकल्प कॉन्फ़िगर करना

अगला कदम निश्चित HTML में कनवर्ट करने के लिए सेव विकल्पों को कॉन्फ़िगर करना है। सभी CSS नियमों को एक फ़ाइल में लिखने के लिए HtmlFixedSaveOptions क्लास का उपयोग करें और SaveFontFaceCssSeparately प्रॉपर्टी को गलत पर सेट करें। यह कैसे करना है यहां बताया गया है:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

हम एक नया HtmlFixedSaveOptions ऑब्जेक्ट बनाते हैं और सभी CSS नियमों को एक फ़ाइल में लिखने के लिए SaveFontFaceCssSeparately प्रॉपर्टी को गलत पर सेट करते हैं।

## HTML दस्तावेज़ रूपांतरण को ठीक किया गया

अब जब हमने सेव विकल्प कॉन्फ़िगर कर लिया है, तो हम दस्तावेज़ को निश्चित HTML में बदलने के लिए आगे बढ़ सकते हैं। सेव विकल्पों को निर्दिष्ट करके परिवर्तित दस्तावेज़ को निश्चित HTML प्रारूप में सहेजने के लिए दस्तावेज़ वर्ग की सेव विधि का उपयोग करें। यहाँ एक उदाहरण है :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

इस उदाहरण में, हम निर्दिष्ट सेव विकल्पों का उपयोग करके परिवर्तित दस्तावेज़ को "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" के रूप में सहेजते हैं।

### .NET के लिए Aspose.Words का उपयोग करके "एक फ़ाइल में सभी CSS नियम लिखें" सुविधा के साथ HtmlFixedSaveOptions के लिए उदाहरण स्रोत कोड

```csharp
// आपकी दस्तावेज़ निर्देशिका तक पहुंच पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Document.docx");

// "सभी सीएसएस नियमों को एक फ़ाइल में लिखें" सुविधा के साथ बैकअप विकल्प कॉन्फ़िगर करें
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// दस्तावेज़ को निश्चित HTML में कनवर्ट करें
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## निष्कर्ष

इस गाइड में, हमने .NET के लिए Aspose.Words लाइब्रेरी के साथ HtmlFixedSaveOptions का उपयोग करके सभी CSS नियमों को एक फ़ाइल में लिखकर किसी Word दस्तावेज़ को निश्चित HTML में परिवर्तित करने का तरीका बताया है। दिए गए चरणों का पालन करके और दिए गए C# स्रोत कोड का उपयोग करके, आप इस कार्यक्षमता को अपने C# एप्लिकेशन में आसानी से लागू कर सकते हैं। सभी सीएसएस नियमों को एक ही फ़ाइल में लिखने से दस्तावेज़ रूपांतरण के दौरान उत्पन्न HTML कोड को व्यवस्थित और प्रबंधित करना आसान हो जाता है।