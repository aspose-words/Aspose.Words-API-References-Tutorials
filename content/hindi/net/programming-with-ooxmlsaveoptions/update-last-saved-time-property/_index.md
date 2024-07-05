---
title: अंतिम सहेजे गए समय की संपत्ति अपडेट करें
linktitle: अंतिम सहेजे गए समय की संपत्ति अपडेट करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: जानें कि Aspose.Words for .NET के साथ दस्तावेज़ सहेजते समय अंतिम सहेजे गए समय गुण को स्वचालित रूप से कैसे अपडेट किया जाए।
type: docs
weight: 10
url: /hi/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
इस ट्यूटोरियल में, हम Aspose.Words for .NET का उपयोग करके दस्तावेज़ सहेजते समय अंतिम सहेजे गए समय गुण को अपडेट करने के लिए प्रदान किए गए C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको जेनरेट किए गए दस्तावेज़ के अंतिम सहेजे गए समय गुण को स्वचालित रूप से अपडेट करने की अनुमति देती है।

## चरण 1: वातावरण की स्थापना

आरंभ करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.Words के साथ अपना विकास वातावरण सेट अप कर लिया है। सुनिश्चित करें कि आपने आवश्यक संदर्भ जोड़ दिए हैं और उचित नामस्थान आयात कर लिए हैं।

## चरण 2: दस्तावेज़ लोड करना

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 इस चरण में, हम दस्तावेज़ को लोड करते हैं`Document` विधि और लोड करने के लिए DOCX फ़ाइल का पथ पास करना।

## चरण 3: OOXML बैकअप विकल्प कॉन्फ़िगर करना

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 इस चरण में, हम OOXML सेव विकल्पों को कॉन्फ़िगर करते हैं`OoxmlSaveOptions` वर्ग। हम सेटिंग करके अंतिम सहेजे गए समय गुण के स्वचालित अद्यतन को सक्षम करते हैं`UpdateLastSavedTimeProperty` को`true`.

## चरण 4: अपडेट की गई प्रॉपर्टी के साथ दस्तावेज़ सहेजें

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 इस अंतिम चरण में, हम दस्तावेज़ को सहेजते हैं`Save` विधि और आउटपुट फ़ाइल के पथ को पास करना`.docx` एक्सटेंशन, निर्दिष्ट सहेजें विकल्पों के साथ।

अब आप स्रोत कोड चलाकर दस्तावेज़ सहेजते समय अंतिम सहेजे गए समय गुण को स्वचालित रूप से अपडेट कर सकते हैं। परिणामी फ़ाइल निर्दिष्ट निर्देशिका में "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx" नाम से सहेजी जाएगी।

### .NET के लिए Aspose.Words का उपयोग करके अंतिम सहेजे गए समय गुण को अपडेट करने के लिए नमूना स्रोत कोड 

```csharp

// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने Aspose.Words for .NET का उपयोग करके दस्तावेज़ सहेजते समय अंतिम सहेजे गए समय गुण को स्वचालित रूप से अपडेट करने की सुविधा का पता लगाया। OOXML सहेजे गए विकल्पों के साथ इस सुविधा को सक्षम करके, आप यह सुनिश्चित कर सकते हैं कि जेनरेट किए गए दस्तावेज़ में अंतिम सहेजे गए समय गुण को स्वचालित रूप से अपडेट किया जाता है।

अंतिम सहेजे गए समय गुण को अपडेट करना दस्तावेज़ के परिवर्तनों और संस्करणों को ट्रैक करने के लिए उपयोगी हो सकता है। यह इस बात का भी ट्रैक रखता है कि दस्तावेज़ को आखिरी बार कब सहेजा गया था, जो विभिन्न परिदृश्यों में उपयोगी हो सकता है।

Aspose.Words for .NET लचीले और शक्तिशाली बैकअप विकल्प प्रदान करके अंतिम बैकअप समय प्रॉपर्टी को स्वचालित रूप से अपडेट करना आसान बनाता है। आप यह सुनिश्चित करने के लिए अपनी परियोजनाओं में इस सुविधा को एकीकृत कर सकते हैं कि उत्पन्न दस्तावेज़ों में सटीक बैकअप जानकारी हो।