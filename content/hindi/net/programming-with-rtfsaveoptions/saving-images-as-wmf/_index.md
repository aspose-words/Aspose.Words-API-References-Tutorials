---
title: छवियों को Wmf के रूप में सहेजना
linktitle: छवियों को Wmf के रूप में सहेजना
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ RTF में कनवर्ट करते समय छवियों को WMF के रूप में सहेजना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-rtfsaveoptions/saving-images-as-wmf/
---

इस ट्यूटोरियल में, हम .NET के लिए Aspose.Words के साथ "RTF सेव विकल्पों के साथ WMF के रूप में छवियों को सहेजना" सुविधा के लिए प्रदान किए गए C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको आरटीएफ प्रारूप में कनवर्ट करते समय दस्तावेज़ छवियों को विंडोज मेटाफ़ाइल (डब्ल्यूएमएफ) प्रारूप में सहेजने की अनुमति देती है।

## चरण 1: वातावरण स्थापित करना

शुरू करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.Words के साथ अपना विकास वातावरण स्थापित कर लिया है। सुनिश्चित करें कि आपने आवश्यक संदर्भ जोड़ दिए हैं और उचित नामस्थान आयात कर लिए हैं।

## चरण 2: दस्तावेज़ लोड करना

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 इस चरण में, हम का उपयोग करके दस्तावेज़ को लोड करते हैं`Document` विधि और लोड करने के लिए DOCX फ़ाइल का पथ पास करना।

## चरण 3: बैकअप विकल्पों को कॉन्फ़िगर करना

```csharp
RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };
```

 इस चरण में, हम आरटीएफ बैकअप विकल्पों को कॉन्फ़िगर करते हैं। हम एक नया बनाते हैं`RtfSaveOptions` ऑब्जेक्ट करें और सेट करें`SaveImagesAsWmf`संपत्ति को`true`. यह Aspose.Words को RTF में कनवर्ट करते समय दस्तावेज़ छवियों को WMF के रूप में सहेजने के लिए कहता है।

## चरण 4: दस्तावेज़ सहेजना

```csharp
doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
```

 इस अंतिम चरण में, हम परिणामी दस्तावेज़ को आरटीएफ प्रारूप में सहेजते हैं`Save` निर्दिष्ट सेव विकल्पों के साथ, विधि और आउटपुट फ़ाइल के लिए पथ पास करना।

अब आप RTF प्रारूप में कनवर्ट करते समय दस्तावेज़ छवियों को WMF प्रारूप में सहेजने के लिए स्रोत कोड चला सकते हैं। परिणामी दस्तावेज़ निर्दिष्ट निर्देशिका में "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf" नाम से सहेजा जाएगा।

### .NET के लिए Aspose.Words के साथ RTF सेव विकल्पों के साथ WMF छवियों को सहेजने की कार्यक्षमता के लिए नमूना स्रोत कोड।

```csharp

            
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");

RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };

doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
            
        
```
## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Words में RTF सेव विकल्पों के साथ छवियों को WMF के रूप में सहेजने की कार्यक्षमता का पता लगाया। हमने सीखा कि RTF प्रारूप में कनवर्ट करते समय किसी दस्तावेज़ से छवियों को WMF प्रारूप में कैसे सहेजा जाए।

यह सुविधा तब उपयोगी होती है जब आप अपने आरटीएफ दस्तावेज़ों में छवियों की गुणवत्ता और रिज़ॉल्यूशन बनाए रखना चाहते हैं। छवियों को WMF प्रारूप में सहेजकर, आप यह सुनिश्चित कर सकते हैं कि उनकी उपस्थिति और तीक्ष्णता बरकरार रहे।

.NET के लिए Aspose.Words दस्तावेज़ हेरफेर और निर्माण के लिए कई उन्नत सुविधाएँ प्रदान करता है। आरटीएफ प्रारूप में कनवर्ट करते समय छवियों को डब्लूएमएफ प्रारूप में सहेजना इसके द्वारा आपको दिए जाने वाले कई शक्तिशाली उपकरणों में से एक है।

### अक्सर पूछे जाने वाले प्रश्नों

#### प्रश्न: .NET के लिए Aspose.Words के साथ "RTF सेव विकल्पों के साथ छवियों को WMF के रूप में सहेजें" सुविधा क्या है?
उत्तर: .NET के लिए Aspose.Words के साथ "RTF सेव विकल्पों के साथ WMF के रूप में छवियों को सहेजें" सुविधा RTF में कनवर्ट करते समय दस्तावेज़ छवियों को Windows मेटाफ़ाइल (WMF) प्रारूप में सहेजने की अनुमति देती है। यह आरटीएफ दस्तावेज़ों में छवि गुणवत्ता और रिज़ॉल्यूशन बनाए रखने की क्षमता प्रदान करता है।

#### प्रश्न: मैं .NET के लिए Aspose.Words के साथ इस सुविधा का उपयोग कैसे कर सकता हूं?
उ: .NET के लिए Aspose.Words के साथ इस सुविधा का उपयोग करने के लिए, आप इन चरणों का पालन कर सकते हैं:

आवश्यक संदर्भ जोड़कर और उचित नामस्थान आयात करके अपना विकास वातावरण स्थापित करें।

 का उपयोग करके दस्तावेज़ लोड करें`Document` विधि और लोड करने के लिए DOCX फ़ाइल का पथ निर्दिष्ट करना।

 बनाकर आरटीएफ सेव विकल्प कॉन्फ़िगर करें`RtfSaveOptions` ऑब्जेक्ट और सेटिंग`SaveImagesAsWmf`संपत्ति को`true`. यह Aspose.Words को दस्तावेज़ छवियों को इस रूप में सहेजने के लिए कहता है 
RTF में कनवर्ट करते समय WMF।

 का उपयोग करके परिणामी दस्तावेज़ को आरटीएफ प्रारूप में सहेजें`Save` विधि और निर्दिष्ट सेव विकल्पों के साथ आउटपुट फ़ाइल का पूरा पथ निर्दिष्ट करना।

#### प्रश्न: क्या आरटीएफ सेव विकल्पों के साथ सेविंग के लिए एक अलग छवि प्रारूप चुनना संभव है?
उ: नहीं, यह विशिष्ट सुविधा आरटीएफ में कनवर्ट करते समय छवियों को डब्लूएमएफ प्रारूप में सहेजती है। अन्य छवि प्रारूप इस सुविधा द्वारा सीधे समर्थित नहीं हैं। हालाँकि, Aspose.Words छवि हेरफेर और रूपांतरण के लिए अन्य सुविधाएँ प्रदान करता है, जिससे आप RTF में परिवर्तित होने से पहले या बाद में छवियों को अन्य प्रारूपों में परिवर्तित कर सकते हैं।

#### प्रश्न: क्या आरटीएफ .NET के लिए Aspose.Words के साथ विकल्पों को सहेजता है जो अन्य कार्यक्षमता प्रदान करता है?
उत्तर: हाँ, .NET के लिए Aspose.Words RTF सेव विकल्पों के साथ कई और सुविधाएँ प्रदान करता है। आप आरटीएफ रूपांतरण के विभिन्न पहलुओं को अनुकूलित कर सकते हैं, जैसे फ़ॉन्ट प्रबंधन, लेआउट, छवियां, टेबल, हाइपरलिंक इत्यादि। ये विकल्प आपको आरटीएफ रूपांतरण के अंतिम परिणाम पर सटीक नियंत्रण प्रदान करते हैं।

#### प्रश्न: मैं .NET के लिए Aspose.Words के साथ दस्तावेज़ में छवियों में हेरफेर कैसे कर सकता हूं?
उ: .NET के लिए Aspose.Words किसी दस्तावेज़ में छवियों में हेरफेर करने के लिए कार्यक्षमता की एक पूरी श्रृंखला प्रदान करता है। आप निकाल सकते हैं, सम्मिलित कर सकते हैं, आकार बदल सकते हैं, क्रॉप कर सकते हैं, फ़िल्टर और प्रभाव लागू कर सकते हैं, गुणवत्ता समायोजित कर सकते हैं, विभिन्न छवि प्रारूपों के बीच कनवर्ट कर सकते हैं और बहुत कुछ कर सकते हैं। छवि हेरफेर पर अधिक विवरण के लिए Aspose.Words दस्तावेज़ देखें।