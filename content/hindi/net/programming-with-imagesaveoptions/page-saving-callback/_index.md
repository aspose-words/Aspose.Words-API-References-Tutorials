---
title: पेज सेविंग कॉलबैक
linktitle: पेज सेविंग कॉलबैक
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ पृष्ठों को छवियों में सहेजना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-imagesaveoptions/page-saving-callback/
---

इस ट्यूटोरियल में, हम .NET के लिए Aspose.Words इमेज सेव विकल्पों के साथ पेज सेव कॉलबैक का उपयोग करने के लिए प्रदान किए गए C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको दस्तावेज़ के प्रत्येक पृष्ठ को छवि के रूप में सहेजते समय कस्टम क्रियाएँ करने की अनुमति देती है।

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 इस चरण में, हम एक नया बनाकर छवि सहेजने के विकल्पों को कॉन्फ़िगर करते हैं`ImageSaveOptions` ऑब्जेक्ट। हम वांछित बैकअप प्रारूप निर्दिष्ट करते हैं, यहाँ PNG प्रारूप के लिए "Png"। हम उपयोग करते हैं`PageSet` सहेजे जाने वाले पृष्ठों की सीमा निर्दिष्ट करने के लिए, यहाँ दस्तावेज़ के पहले पृष्ठ से अंतिम पृष्ठ तक (`doc.PageCount - 1` हमने यह भी निर्धारित किया है`PageSavingCallback` एक उदाहरण के लिए`HandlePageSavingCallback`, जो पेज सेविंग कॉलबैक को संभालने के लिए एक कस्टम क्लास है।

## चरण 4: सेव पेज कॉलबैक को क्रियान्वित करना

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // अपनी कस्टम क्रियाएँ यहाँ क्रियान्वित करें
         // आप "args.PageIndex" प्रॉपर्टी के माध्यम से पेज की जानकारी तक पहुँच सकते हैं
         // आप प्रत्येक पृष्ठ के लिए अलग से सेव विकल्प भी बदल सकते हैं
     }
}
```

 इस चरण में, हम कार्यान्वयन करते हैं`HandlePageSavingCallback` वह वर्ग जो कार्यान्वित करता है`IPageSavingCallback` इंटरफ़ेस। आप अपने विशिष्ट कार्यों को जोड़कर इस वर्ग को अनुकूलित कर सकते हैं`PageSaving` विधि। आप पृष्ठ जानकारी तक पहुँच सकते हैं`args.PageIndex` की संपत्ति`PageSavingArgs` ऑब्जेक्ट को एक तर्क के रूप में पारित किया गया.

## चरण 5: पृष्ठों को छवियों के रूप में सहेजना

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 इस अंतिम चरण में, हम दस्तावेज़ के प्रत्येक पृष्ठ को छवि के रूप में सहेजते हैं`Save` विधि और आउटपुट फ़ाइल के पथ को पास करना`.png` एक्सटेंशन, साथ ही निर्दिष्ट सहेजने के विकल्प।

अब आप दस्तावेज़ के प्रत्येक पृष्ठ को छवि के रूप में सहेजते समय कस्टम क्रियाएँ करने के लिए स्रोत कोड चला सकते हैं। परिणामी फ़ाइल "WorkingWithImageSaveOptions.PageSavingCallback.png" नाम से निर्दिष्ट निर्देशिका में सहेजी जाएगी।

### .NET के लिए Aspose.Words का उपयोग करके पेज सेविंग कॉलबैक के लिए नमूना स्रोत कोड


```csharp 
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Words इमेज सेव विकल्पों के साथ पेज सेव कॉलबैक कार्यक्षमता का पता लगाया। हमने सीखा कि दस्तावेज़ के प्रत्येक पृष्ठ को इमेज के रूप में सहेजते समय कस्टम क्रियाएँ कैसे करें।

यह सुविधा तब उपयोगी होती है जब आप छवियों में कनवर्ट करते समय प्रत्येक पृष्ठ पर विशिष्ट संचालन करना चाहते हैं। आप पृष्ठ जानकारी तक पहुँच सकते हैं और बैकअप विकल्पों को अनुकूलित करने या अन्य पृष्ठ-विशिष्ट प्रसंस्करण करने के लिए इसका उपयोग कर सकते हैं।

Aspose.Words for .NET दस्तावेज़ हेरफेर और निर्माण के लिए उन्नत सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है। सेव पेज रिमाइंडर कई शक्तिशाली उपकरणों में से एक है जो आपको छवियों में पृष्ठों को सहेजने की प्रक्रिया को अनुकूलित करने के लिए देता है।