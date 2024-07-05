---
title: प्रारूप 1Bpp अनुक्रमित
linktitle: प्रारूप 1Bpp अनुक्रमित
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ अनुक्रमित 1 bpp में छवियों को प्रारूपित करना सीखें। कम रंग गहराई वाली छवियों के लिए पूरा ट्यूटोरियल।
type: docs
weight: 10
url: /hi/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
इस ट्यूटोरियल में, हम .NET के लिए Aspose.Words के साथ "1Bpp इंडेक्स्ड फ़ॉर्मेट करें" कार्यक्षमता के लिए प्रदान किए गए C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको 1 बिट प्रति पिक्सेल (1 bpp) की रंग गहराई और एक अनुक्रमित रंग मोड के साथ PNG प्रारूप में दस्तावेज़ में छवियों को फ़ॉर्मेट करने की अनुमति देती है।

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 इस चरण में, हम छवियों के लिए बैकअप विकल्प कॉन्फ़िगर करते हैं। हम एक नया बनाते हैं`ImageSaveOptions`वांछित सेव फ़ॉर्मेट को निर्दिष्ट करने वाला ऑब्जेक्ट, यहाँ PNG फ़ॉर्मेट के लिए "Png"। हम छवि में शामिल करने के लिए पेज, काले और सफ़ेद रंग मोड और अनुक्रमित 1 bpp पिक्सेल फ़ॉर्मेट को भी परिभाषित करते हैं।

## चरण 4: छवियों का बैकअप लेना

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 इस अंतिम चरण में, हम दस्तावेज़ छवियों को PNG प्रारूप में सहेजते हैं`Save` विधि और आउटपुट फ़ाइल के पथ को निर्दिष्ट सेव विकल्पों के साथ पास करना।

अब आप स्रोत कोड चलाकर दस्तावेज़ छवियों को PNG प्रारूप में 1 bpp अनुक्रमित रंग गहराई के साथ स्वरूपित कर सकते हैं। परिणामी फ़ाइल निर्दिष्ट निर्देशिका में "WorkingWithImageSaveOptions.Format1BppIndexed.Png" नाम से सहेजी जाएगी।

### .NET के लिए Aspose.Words का उपयोग करके फ़ॉर्मेट 1Bpp इंडेक्स्ड के लिए नमूना स्रोत कोड

```csharp 
 
			 // आपके दस्तावेज़ निर्देशिका का पथ
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

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Words के साथ 1Bpp इंडेक्स्ड फ़ॉर्मेट सुविधा का पता लगाया। हमने सीखा कि PNG फ़ॉर्मेट में 1 बिट प्रति पिक्सेल (1 bpp) की रंग गहराई और इंडेक्स्ड कलर मोड के साथ दस्तावेज़ में छवियों को कैसे फ़ॉर्मेट किया जाए।

यह सुविधा तब उपयोगी होती है जब आप कम रंग गहराई और छोटे फ़ाइल आकार वाली छवियाँ प्राप्त करना चाहते हैं। 1Bpp अनुक्रमित प्रारूप छवियों को अनुक्रमित रंग पैलेट का उपयोग करके प्रदर्शित करने की अनुमति देता है, जो कुछ विशिष्ट अनुप्रयोगों के लिए फायदेमंद हो सकता है।

Aspose.Words for .NET दस्तावेज़ हेरफेर और निर्माण के लिए उन्नत सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है। 1Bpp इंडेक्स्ड प्रारूप आपके निपटान में कई शक्तिशाली उपकरणों में से एक है।