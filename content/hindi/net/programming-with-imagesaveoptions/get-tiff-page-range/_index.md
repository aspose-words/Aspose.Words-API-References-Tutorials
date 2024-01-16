---
title: टिफ पेज रेंज प्राप्त करें
linktitle: टिफ पेज रेंज प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ TIFF पेजों की श्रृंखला निकालने का तरीका जानें। कस्टम TIFF फ़ाइलों के लिए संपूर्ण ट्यूटोरियल।
type: docs
weight: 10
url: /hi/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

इस ट्यूटोरियल में, हम .NET के लिए Aspose.Words के साथ TIFF पृष्ठों की एक श्रृंखला प्राप्त करने के लिए दिए गए C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको किसी दस्तावेज़ से पृष्ठों की एक विशिष्ट श्रेणी निकालने और उन्हें TIFF फ़ाइल के रूप में सहेजने की अनुमति देती है।

## चरण 1: वातावरण स्थापित करना

शुरू करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.Words के साथ अपना विकास वातावरण स्थापित कर लिया है। सुनिश्चित करें कि आपने आवश्यक संदर्भ जोड़ दिए हैं और उचित नामस्थान आयात कर लिए हैं।

## चरण 2: दस्तावेज़ लोड करना

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 इस चरण में, हम का उपयोग करके दस्तावेज़ को लोड करते हैं`Document` विधि और लोड करने के लिए DOCX फ़ाइल का पथ पास करना।

## चरण 3: संपूर्ण दस्तावेज़ को TIFF में सहेजना

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

इस चरण में, हम इसका उपयोग करके संपूर्ण दस्तावेज़ को TIFF प्रारूप में सहेजते हैं`Save` विधि और एक्सटेंशन के साथ आउटपुट फ़ाइल का पथ निर्दिष्ट करना`.tiff`.

## चरण 4: पृष्ठ श्रेणी के लिए बैकअप विकल्प कॉन्फ़िगर करें

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 इस चरण में, हम विशिष्ट पृष्ठ श्रेणी के लिए बैकअप विकल्प कॉन्फ़िगर करते हैं। हम एक नया बनाते हैं`ImageSaveOptions` ऑब्जेक्ट वांछित सेव फॉर्मेट को निर्दिष्ट करता है, यहाँ TIFF फॉर्मेट के लिए "Tiff"। हम उपयोग करते हैं`PageSet` उन पृष्ठों की श्रेणी निर्दिष्ट करने के लिए जिन्हें हम निकालना चाहते हैं, यहां पृष्ठ 0 से पृष्ठ 1 (समावेशी) तक। हमने TIFF कम्प्रेशन को भी इस पर सेट किया है`Ccitt4` और रिज़ॉल्यूशन 160 डीपीआई तक।

## चरण 5: पृष्ठ श्रेणी को TIFF में सहेजना

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 इस अंतिम चरण में, हम निर्दिष्ट पृष्ठ श्रेणी को TIFF प्रारूप में सहेजते हैं`Save` विधि और आउटपुट फ़ाइल के लिए पथ पास करना`.tiff` एक्सटेंशन, निर्दिष्ट सेव विकल्पों के साथ।

अब आप अपने दस्तावेज़ से पृष्ठों की एक विशिष्ट श्रेणी प्राप्त करने के लिए स्रोत कोड चला सकते हैं और उन्हें TIFF फ़ाइल के रूप में सहेज सकते हैं। परिणामी फ़ाइलें निर्दिष्ट निर्देशिका में पूर्ण दस्तावेज़ के लिए "WorkingWithImageSaveOptions.MultipageTiff.tiff" और निर्दिष्ट पृष्ठ श्रेणी के लिए "WorkingWithImageSaveOptions.GetTiffPageRange.tiff" नाम से सहेजी जाएंगी।

### .NET के लिए Aspose.Words का उपयोग करके टिफ़ पेज रेंज प्राप्त करने का नमूना स्रोत कोड

```csharp 

// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Words के साथ TIFF पृष्ठों की एक श्रृंखला प्राप्त करने की कार्यक्षमता का पता लगाया। हमने सीखा कि किसी दस्तावेज़ से पृष्ठों की एक विशिष्ट श्रेणी को कैसे निकाला जाए और उन्हें TIFF फ़ाइल के रूप में कैसे सहेजा जाए।

यह सुविधा तब उपयोगी होती है जब आप किसी दस्तावेज़ से केवल कुछ पेज निकालना चाहते हैं और उन्हें TIFF जैसे मानक छवि प्रारूप में सहेजना चाहते हैं। सर्वोत्तम गुणवत्ता वाली TIFF फ़ाइलें प्राप्त करने के लिए आप संपीड़न और रिज़ॉल्यूशन विकल्पों को भी अनुकूलित कर सकते हैं।

.NET के लिए Aspose.Words दस्तावेज़ हेरफेर और निर्माण के लिए उन्नत सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है। TIFF पृष्ठ श्रेणी प्राप्त करना आपके लिए उपलब्ध कई शक्तिशाली उपकरणों में से एक है।

TIFF प्रारूप में अपने दस्तावेज़ों से पृष्ठों की विशिष्ट श्रेणियों को निकालने और सहेजने के लिए .NET परियोजनाओं के लिए इस कार्यक्षमता को अपने Aspose.Words में एकीकृत करने के लिए स्वतंत्र महसूस करें।