---
title: सभी CSS नियम एकल फ़ाइल में लिखें
linktitle: सभी CSS नियम एकल फ़ाइल में लिखें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ एक ही फ़ाइल में सभी CSS नियमों को लिखकर Word दस्तावेज़ को निश्चित HTML में परिवर्तित करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

C# एप्लीकेशन में Word डॉक्यूमेंट को फिक्स्ड HTML में कन्वर्ट करते समय, आप बेहतर संगठन और पोर्टेबिलिटी के लिए सभी CSS नियमों को एक ही फाइल में समेकित करना चाह सकते हैं। .NET के लिए Aspose.Words लाइब्रेरी के साथ, आप HtmlFixedSaveOptions सेव ऑप्शन का उपयोग करके आसानी से इस कार्यक्षमता को निर्दिष्ट कर सकते हैं। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको बताएंगे कि HtmlFixedSaveOptions सेव ऑप्शन का उपयोग करके सभी CSS नियमों को एक ही फाइल में लिखकर Word डॉक्यूमेंट को फिक्स्ड HTML में कन्वर्ट करने के लिए Aspose.Words for .NET C# सोर्स कोड का उपयोग कैसे करें।

## Aspose.Words लाइब्रेरी को समझना

कोड में गोता लगाने से पहले, .NET के लिए Aspose.Words लाइब्रेरी को समझना महत्वपूर्ण है। Aspose.Words .NET सहित विभिन्न प्लेटफ़ॉर्म में Word दस्तावेज़ बनाने, संपादित करने, परिवर्तित करने और सुरक्षित करने के लिए एक शक्तिशाली लाइब्रेरी है। यह दस्तावेज़ों में हेरफेर करने के लिए कई सुविधाएँ प्रदान करता है, जैसे कि टेक्स्ट डालना, फ़ॉर्मेटिंग बदलना, अनुभाग जोड़ना और बहुत कुछ।

## Word दस्तावेज़ लोड करना

पहला चरण उस वर्ड दस्तावेज़ को लोड करना है जिसे आप निश्चित HTML में बदलना चाहते हैं। स्रोत फ़ाइल से दस्तावेज़ लोड करने के लिए Document क्लास का उपयोग करें। यहाँ एक उदाहरण दिया गया है:

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

इस उदाहरण में, हम दस्तावेज़ निर्देशिका में स्थित दस्तावेज़ "Document.docx" को लोड करते हैं।

## बैकअप विकल्प कॉन्फ़िगर करना

अगला चरण निश्चित HTML में कनवर्ट करने के लिए सेव ऑप्शन को कॉन्फ़िगर करना है। HtmlFixedSaveOptions क्लास का उपयोग करें और सभी CSS नियमों को एक ही फ़ाइल में लिखने के लिए SaveFontFaceCssSeparately प्रॉपर्टी को false पर सेट करें। इसे करने का तरीका यहां बताया गया है:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

हम एक नया HtmlFixedSaveOptions ऑब्जेक्ट बनाते हैं और सभी CSS नियमों को एक ही फ़ाइल में लिखने के लिए SaveFontFaceCssSeparately प्रॉपर्टी को false पर सेट करते हैं।

## HTML दस्तावेज़ रूपांतरण को ठीक किया गया

अब जब हमने सेव ऑप्शन कॉन्फ़िगर कर लिया है, तो हम डॉक्यूमेंट को फिक्स्ड HTML में बदलने के लिए आगे बढ़ सकते हैं। सेव ऑप्शन निर्दिष्ट करके कन्वर्ट किए गए डॉक्यूमेंट को फिक्स्ड HTML फॉर्मेट में सेव करने के लिए डॉक्यूमेंट क्लास की सेव विधि का उपयोग करें। यहाँ एक उदाहरण दिया गया है :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

इस उदाहरण में, हम निर्दिष्ट सहेजने के विकल्पों का उपयोग करके परिवर्तित दस्तावेज़ को "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" के रूप में सहेजते हैं।

### .NET के लिए Aspose.Words का उपयोग करके "सभी CSS नियमों को एक फ़ाइल में लिखें" सुविधा के साथ HtmlFixedSaveOptions के लिए उदाहरण स्रोत कोड

```csharp
// आपके दस्तावेज़ निर्देशिका तक पहुँच पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Document.docx");

// "सभी CSS नियमों को एक फ़ाइल में लिखें" सुविधा के साथ बैकअप विकल्प कॉन्फ़िगर करें
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// दस्तावेज़ को निश्चित HTML में बदलें
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## निष्कर्ष

इस गाइड में, हमने बताया है कि .NET के लिए Aspose.Words लाइब्रेरी के साथ HtmlFixedSaveOptions का उपयोग करके एक ही फ़ाइल में सभी CSS नियम लिखकर Word दस्तावेज़ को निश्चित HTML में कैसे परिवर्तित किया जाए। दिए गए चरणों का पालन करके और दिए गए C# स्रोत कोड का उपयोग करके, आप आसानी से अपने C# एप्लिकेशन में इस कार्यक्षमता को लागू कर सकते हैं। सभी CSS नियमों को एक ही फ़ाइल में लिखने से दस्तावेज़ रूपांतरण के दौरान उत्पन्न HTML कोड को व्यवस्थित और प्रबंधित करना आसान हो जाता है।