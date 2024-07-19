---
title: Jpeg पेज रेंज प्राप्त करें
linktitle: Jpeg पेज रेंज प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: जानें कि .NET के लिए Aspose.Words के साथ JPEG पेजों की एक श्रृंखला कैसे प्राप्त करें। कस्टम इमेज निकालने के लिए पूरा ट्यूटोरियल।
type: docs
weight: 10
url: /hi/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

इस ट्यूटोरियल में, हम .NET के लिए Aspose.Words के साथ "JPEG पेजों की रेंज प्राप्त करें" सुविधा के लिए प्रदान किए गए C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको दस्तावेज़ के पृष्ठों की एक विशिष्ट श्रेणी को JPEG प्रारूप में छवियों में बदलने की अनुमति देती है।

## चरण 1: वातावरण की स्थापना

आरंभ करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.Words के साथ अपना विकास वातावरण सेट अप कर लिया है। सुनिश्चित करें कि आपने आवश्यक संदर्भ जोड़ दिए हैं और उचित नामस्थान आयात कर लिए हैं।

## चरण 2: दस्तावेज़ लोड करना

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 इस चरण में, हम दस्तावेज़ को लोड करते हैं`Document` विधि और लोड करने के लिए DOCX फ़ाइल का पथ पास करना।

## चरण 3: छवि बैकअप विकल्प कॉन्फ़िगर करें

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 इस चरण में, हम छवियों के लिए बैकअप विकल्प कॉन्फ़िगर करते हैं। हम एक नया बनाते हैं`ImageSaveOptions` वांछित सेव फ़ॉर्मेट को निर्दिष्ट करने वाला ऑब्जेक्ट, यहाँ JPEG फ़ॉर्मेट के लिए "Jpeg" है। हम कन्वर्ट करने के लिए पेजों की सीमा भी सेट करते हैं`PageSet`अंत में, हम छवि की चमक और कंट्रास्ट को समायोजित करते हैं`ImageBrightness`और`ImageContrast` गुण, क्रमशः। हम क्षैतिज रिज़ॉल्यूशन को भी बदलते हैं`HorizontalResolution` संपत्ति।

## चरण 4: छवियों का बैकअप लेना

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 इस अंतिम चरण में, हम निर्दिष्ट पृष्ठ श्रेणी की छवियों को JPEG प्रारूप में सहेजते हैं`Save` विधि और आउटपुट फ़ाइल के पथ को निर्दिष्ट सेव विकल्पों के साथ पास करना।

अब आप अपने दस्तावेज़ में पृष्ठों की एक विशिष्ट श्रेणी को JPEG छवियों में बदलने के लिए स्रोत कोड चला सकते हैं। परिणामी फ़ाइल "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg" नाम से निर्दिष्ट निर्देशिका में सहेजी जाएगी।

### Aspose.Words For .NET का उपयोग करके Jpeg पेज रेंज प्राप्त करने के लिए नमूना स्रोत कोड

```csharp 
 // आपके दस्तावेज़ निर्देशिका का पथ
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// किसी दस्तावेज़ के केवल प्रथम पृष्ठ को परिवर्तित करने के लिए "PageSet" को "0" पर सेट करें।
options.PageSet = new PageSet(0);

// छवि की चमक और कंट्रास्ट बदलें.
// दोनों 0-1 स्केल पर हैं और डिफ़ॉल्ट रूप से 0.5 पर हैं।
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// क्षैतिज रिज़ोल्यूशन बदलें.
// इन गुणों के लिए डिफ़ॉल्ट मान 96.0 है, जिसका रिज़ॉल्यूशन 96dpi है।
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Words के साथ JPEG पेज रेंज प्राप्त करने की कार्यक्षमता का पता लगाया। हमने सीखा कि दस्तावेज़ के पृष्ठों की एक विशिष्ट श्रेणी को JPEG प्रारूप में छवियों में कैसे परिवर्तित किया जाए, जबकि सहेजने के विकल्पों को अनुकूलित किया जाए।

यह सुविधा तब उपयोगी होती है जब आप किसी दस्तावेज़ से विशिष्ट पृष्ठों को निकालना चाहते हैं और उन्हें JPEG छवियों के रूप में सहेजना चाहते हैं। आप वैयक्तिकृत परिणाम प्राप्त करने के लिए छवियों की चमक, कंट्रास्ट और क्षैतिज रिज़ॉल्यूशन को भी समायोजित कर सकते हैं।

Aspose.Words for .NET दस्तावेज़ हेरफेर और निर्माण के लिए उन्नत सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है। JPEG पेज रेंज प्राप्त करना आपके निपटान में कई शक्तिशाली उपकरणों में से एक है।

अपने दस्तावेज़ों से उच्च गुणवत्ता वाली JPEG छवियां प्राप्त करने के लिए इस सुविधा को अपने Aspose.Words for .NET प्रोजेक्ट में एकीकृत करने के लिए स्वतंत्र महसूस करें।