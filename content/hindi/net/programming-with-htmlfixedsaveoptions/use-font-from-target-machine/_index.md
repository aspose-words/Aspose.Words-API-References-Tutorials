---
title: लक्ष्य मशीन से फ़ॉन्ट का उपयोग करें
linktitle: लक्ष्य मशीन से फ़ॉन्ट का उपयोग करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: जानें कि .NET के लिए Aspose.Words के साथ लक्ष्य मशीन के फ़ॉन्ट का उपयोग करके Word दस्तावेज़ को निश्चित HTML में कैसे परिवर्तित किया जाए।
type: docs
weight: 10
url: /hi/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

C# एप्लीकेशन में Word डॉक्यूमेंट को फिक्स्ड HTML में कन्वर्ट करते समय, आप टारगेट मशीन के फॉन्ट का उपयोग करना चाह सकते हैं ताकि यह सुनिश्चित हो सके कि रेंडर किया गया HTML डॉक्यूमेंट के मूल रूप और स्टाइल को बनाए रखे। .NET के लिए Aspose.Words लाइब्रेरी के साथ, आप HtmlFixedSaveOptions सेव ऑप्शन का उपयोग करके आसानी से इस कार्यक्षमता को निर्दिष्ट कर सकते हैं। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको HtmlFixedSaveOptions का उपयोग करके टारगेट मशीन के फॉन्ट का उपयोग करके Word डॉक्यूमेंट को फिक्स्ड HTML में कन्वर्ट करने के लिए .NET के लिए Aspose.Words के C# सोर्स कोड का उपयोग करने का तरीका बताएंगे।

## Aspose.Words लाइब्रेरी को समझना

कोड में गोता लगाने से पहले, .NET के लिए Aspose.Words लाइब्रेरी को समझना महत्वपूर्ण है। Aspose.Words .NET सहित विभिन्न प्लेटफ़ॉर्म में Word दस्तावेज़ बनाने, संपादित करने, परिवर्तित करने और सुरक्षित करने के लिए एक शक्तिशाली लाइब्रेरी है। यह दस्तावेज़ों में हेरफेर करने के लिए कई सुविधाएँ प्रदान करता है, जैसे कि टेक्स्ट डालना, फ़ॉर्मेटिंग बदलना, अनुभाग जोड़ना और बहुत कुछ।

## Word दस्तावेज़ लोड करना

पहला चरण उस वर्ड दस्तावेज़ को लोड करना है जिसे आप निश्चित HTML में बदलना चाहते हैं। स्रोत फ़ाइल से दस्तावेज़ लोड करने के लिए Document क्लास का उपयोग करें। यहाँ एक उदाहरण दिया गया है:

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

इस उदाहरण में, हम दस्तावेज़ निर्देशिका में स्थित दस्तावेज़ "बुलेट पॉइंट्स विद अल्टरनेटिव फ़ॉन्ट.docx" को लोड करते हैं।

## बैकअप विकल्प कॉन्फ़िगर करना

अगला चरण फिक्स्ड HTML में कनवर्ट करने के लिए सेव ऑप्शन को कॉन्फ़िगर करना है। HtmlFixedSaveOptions क्लास का उपयोग करें और Aspose.Words को लक्ष्य मशीन से फ़ॉन्ट का उपयोग करने के लिए कहने के लिए UseTargetMachineFonts प्रॉपर्टी को true पर सेट करें। इसे करने का तरीका यहां बताया गया है:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

हम एक नया HtmlFixedSaveOptions ऑब्जेक्ट बनाते हैं और रूपांतरण करते समय लक्ष्य मशीन के फ़ॉन्ट्स का उपयोग करने के लिए UseTargetMachineFonts गुण को true पर सेट करते हैं।

## HTML दस्तावेज़ रूपांतरण को ठीक किया गया

अब जब हमने सेव ऑप्शन कॉन्फ़िगर कर लिया है, तो हम डॉक्यूमेंट को फिक्स्ड HTML में बदलने के लिए आगे बढ़ सकते हैं। सेव ऑप्शन निर्दिष्ट करके कन्वर्ट किए गए डॉक्यूमेंट को फिक्स्ड HTML फॉर्मेट में सेव करने के लिए डॉक्यूमेंट क्लास की सेव विधि का उपयोग करें। यहाँ एक उदाहरण दिया गया है :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

इस उदाहरण में, हम निर्दिष्ट सहेजने के विकल्पों का उपयोग करके परिवर्तित दस्तावेज़ को "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" के रूप में सहेजते हैं।

### .NET के लिए Aspose.Words का उपयोग करते हुए "लक्ष्य मशीन से फ़ॉन्ट का उपयोग करें" सुविधा के साथ HtmlFixedSaveOptions के लिए उदाहरण स्रोत कोड

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

// "लक्ष्य मशीन से फ़ॉन्ट का उपयोग करें" सुविधा के साथ बैकअप विकल्प कॉन्फ़िगर करें
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// दस्तावेज़ को निश्चित HTML में बदलें
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## निष्कर्ष

इस गाइड में, हमने बताया है कि .NET के लिए Aspose.Words लाइब्रेरी के साथ लक्ष्य मशीन के फ़ॉन्ट का उपयोग करके Word दस्तावेज़ को फिक्स्ड HTML में कैसे परिवर्तित किया जाए। दिए गए चरणों का पालन करके और दिए गए C# स्रोत कोड का उपयोग करके, आप आसानी से अपने C# एप्लिकेशन में इस कार्यक्षमता को लागू कर सकते हैं। लक्ष्य मशीन के फ़ॉन्ट के साथ फिक्स्ड HTML में रूपांतरण HTML प्रारूप में दस्तावेज़ के विश्वसनीय और सुसंगत रेंडरिंग की गारंटी देता है।
