---
title: लक्ष्य मशीन से फ़ॉन्ट का उपयोग करें
linktitle: लक्ष्य मशीन से फ़ॉन्ट का उपयोग करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ लक्ष्य मशीन के फ़ॉन्ट का उपयोग करके किसी Word दस्तावेज़ को निश्चित HTML में परिवर्तित करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

किसी Word दस्तावेज़ को C# एप्लिकेशन में निश्चित HTML में परिवर्तित करते समय, आप यह सुनिश्चित करने के लिए लक्ष्य मशीन के फ़ॉन्ट का उपयोग करना चाह सकते हैं कि प्रस्तुत HTML दस्तावेज़ के मूल स्वरूप और शैली को बरकरार रखता है। .NET के लिए Aspose.Words लाइब्रेरी के साथ, आप HtmlFixedSaveOptions सेव विकल्पों का उपयोग करके इस कार्यक्षमता को आसानी से निर्दिष्ट कर सकते हैं। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको बताएंगे कि HtmlFixedSaveOptions का उपयोग करके लक्ष्य मशीन के फ़ॉन्ट का उपयोग करके किसी Word दस्तावेज़ को निश्चित HTML में परिवर्तित करने के लिए .NET के लिए Aspose.Words के C# स्रोत कोड का उपयोग कैसे करें।

## Aspose.Words लाइब्रेरी को समझना

कोड में गोता लगाने से पहले, .NET के लिए Aspose.Words लाइब्रेरी को समझना महत्वपूर्ण है। Aspose.Words .NET सहित विभिन्न प्लेटफार्मों में Word दस्तावेज़ों को बनाने, संपादित करने, परिवर्तित करने और सुरक्षित करने के लिए एक शक्तिशाली लाइब्रेरी है। यह दस्तावेज़ों में हेरफेर करने के लिए कई सुविधाएँ प्रदान करता है, जैसे टेक्स्ट सम्मिलित करना, फ़ॉर्मेटिंग बदलना, अनुभाग जोड़ना और बहुत कुछ।

## Word दस्तावेज़ लोड हो रहा है

पहला कदम उस वर्ड दस्तावेज़ को लोड करना है जिसे आप निश्चित HTML में कनवर्ट करना चाहते हैं। दस्तावेज़ को स्रोत फ़ाइल से लोड करने के लिए दस्तावेज़ वर्ग का उपयोग करें। यहाँ एक उदाहरण है :

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

इस उदाहरण में, हम दस्तावेज़ निर्देशिका में स्थित दस्तावेज़ "वैकल्पिक फ़ॉन्ट.docx के साथ बुलेट पॉइंट" लोड करते हैं।

## बैकअप विकल्प कॉन्फ़िगर करना

अगला कदम निश्चित HTML में कनवर्ट करने के लिए सेव विकल्पों को कॉन्फ़िगर करना है। लक्ष्य मशीन से फ़ॉन्ट का उपयोग करने के लिए Aspose.Words को बताने के लिए HtmlFixedSaveOptions क्लास का उपयोग करें और UseTargetMachineFonts प्रॉपर्टी को सही पर सेट करें। यह कैसे करना है यहां बताया गया है:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

हम एक नया HtmlFixedSaveOptions ऑब्जेक्ट बनाते हैं और कनवर्ट करते समय लक्ष्य मशीन के फ़ॉन्ट का उपयोग करने के लिए UseTargetMachineFonts प्रॉपर्टी को सही पर सेट करते हैं।

## HTML दस्तावेज़ रूपांतरण को ठीक किया गया

अब जब हमने सेव विकल्प कॉन्फ़िगर कर लिया है, तो हम दस्तावेज़ को निश्चित HTML में बदलने के लिए आगे बढ़ सकते हैं। सेव विकल्पों को निर्दिष्ट करके परिवर्तित दस्तावेज़ को निश्चित HTML प्रारूप में सहेजने के लिए दस्तावेज़ वर्ग की सेव विधि का उपयोग करें। यहाँ एक उदाहरण है :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

इस उदाहरण में, हम निर्दिष्ट सेव विकल्पों का उपयोग करके परिवर्तित दस्तावेज़ को "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" के रूप में सहेजते हैं।

### .NET के लिए Aspose.Words का उपयोग करके "लक्ष्य मशीन से फ़ॉन्ट का उपयोग करें" सुविधा के साथ HtmlFixedSaveOptions के लिए उदाहरण स्रोत कोड

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

//"लक्ष्य मशीन से फ़ॉन्ट का उपयोग करें" सुविधा के साथ बैकअप विकल्प कॉन्फ़िगर करें
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// दस्तावेज़ को निश्चित HTML में कनवर्ट करें
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## निष्कर्ष

इस गाइड में, हमने बताया है कि .NET के लिए Aspose.Words लाइब्रेरी के साथ लक्ष्य मशीन के फ़ॉन्ट का उपयोग करके किसी Word दस्तावेज़ को निश्चित HTML में कैसे परिवर्तित किया जाए। दिए गए चरणों का पालन करके और दिए गए C# स्रोत कोड का उपयोग करके, आप इस कार्यक्षमता को अपने C# एप्लिकेशन में आसानी से लागू कर सकते हैं। लक्ष्य मशीन के फ़ॉन्ट के साथ निश्चित HTML में रूपांतरण HTML प्रारूप में दस्तावेज़ के विश्वसनीय और सुसंगत प्रतिपादन की गारंटी देता है।
