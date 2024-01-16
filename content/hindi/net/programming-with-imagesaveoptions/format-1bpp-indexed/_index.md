---
title: प्रारूप 1बीपीपी अनुक्रमित
linktitle: प्रारूप 1बीपीपी अनुक्रमित
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ अनुक्रमित 1 बीपीपी में छवियों को प्रारूपित करना सीखें। कम रंग की गहराई वाली छवियों के लिए संपूर्ण ट्यूटोरियल।
type: docs
weight: 10
url: /hi/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
इस ट्यूटोरियल में, हम .NET के लिए Aspose.Words के साथ "फॉर्मेट 1Bpp इंडेक्स्ड" कार्यक्षमता के लिए प्रदान किए गए C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको 1 बिट प्रति पिक्सेल (1 बीपीपी) की रंग गहराई और एक अनुक्रमित रंग मोड के साथ पीएनजी प्रारूप में किसी दस्तावेज़ में छवियों को प्रारूपित करने की अनुमति देती है।

## चरण 1: वातावरण स्थापित करना

शुरू करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.Words के साथ अपना विकास वातावरण स्थापित कर लिया है। सुनिश्चित करें कि आपने आवश्यक संदर्भ जोड़ दिए हैं और उचित नामस्थान आयात कर लिए हैं।

## चरण 2: दस्तावेज़ लोड करना

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 इस चरण में, हम का उपयोग करके दस्तावेज़ को लोड करते हैं`Document` विधि और लोड करने के लिए DOCX फ़ाइल का पथ पास करना।

## चरण 3: छवि बैकअप विकल्प कॉन्फ़िगर करें

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 इस चरण में, हम छवियों के लिए बैकअप विकल्प कॉन्फ़िगर करते हैं। हम एक नया बनाते हैं`ImageSaveOptions`वांछित सेव फॉर्मेट निर्दिष्ट करने वाली वस्तु, यहां पीएनजी फॉर्मेट के लिए "पीएनजी"। हम छवि में शामिल करने के लिए पृष्ठ को काले और सफेद रंग मोड और अनुक्रमित 1 बीपीपी पिक्सेल प्रारूप भी परिभाषित करते हैं।

## चरण 4: छवियों का बैकअप लेना

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 इस अंतिम चरण में, हम दस्तावेज़ छवियों को पीएनजी प्रारूप में सहेजते हैं`Save` निर्दिष्ट सेव विकल्पों के साथ, विधि और आउटपुट फ़ाइल के लिए पथ पास करना।

अब आप 1 बीपीपी अनुक्रमित रंग की गहराई के साथ पीएनजी प्रारूप में दस्तावेज़ छवियों को प्रारूपित करने के लिए स्रोत कोड चला सकते हैं। परिणामी फ़ाइल निर्दिष्ट निर्देशिका में "WorkingWithImageSaveOptions.Format1BppIndexed.Png" नाम से सहेजी जाएगी।

### .NET के लिए Aspose.Words का उपयोग करके अनुक्रमित प्रारूप 1Bpp के लिए नमूना स्रोत कोड

```csharp 
 
			 // आपकी दस्तावेज़ निर्देशिका का पथ
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Words के साथ 1Bpp अनुक्रमित प्रारूप सुविधा का पता लगाया। हमने सीखा कि 1 बिट प्रति पिक्सेल (1 बीपीपी) की रंग गहराई और एक अनुक्रमित रंग मोड के साथ पीएनजी प्रारूप में किसी दस्तावेज़ में छवियों को कैसे प्रारूपित किया जाए।

यह सुविधा तब उपयोगी होती है जब आप कम रंग गहराई और छोटे फ़ाइल आकार वाली छवियां प्राप्त करना चाहते हैं। 1बीपीपी अनुक्रमित प्रारूप छवियों को अनुक्रमित रंग पैलेट का उपयोग करके प्रस्तुत करने की अनुमति देता है, जो कुछ विशिष्ट अनुप्रयोगों के लिए फायदेमंद हो सकता है।

.NET के लिए Aspose.Words दस्तावेज़ हेरफेर और निर्माण के लिए उन्नत सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है। 1बीपीपी अनुक्रमित प्रारूप आपके लिए उपलब्ध कई शक्तिशाली उपकरणों में से एक है।