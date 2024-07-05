---
title: रूपांतरित तत्वों को रास्टराइज़ करें
linktitle: रूपांतरित तत्वों को रास्टराइज़ करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: जानें कि .NET के लिए Aspose.Words के साथ PCL प्रारूप में कनवर्ट करते समय परिवर्तित तत्वों के रास्टराइजेशन को अक्षम कैसे करें।
type: docs
weight: 10
url: /hi/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words for .NET एक शक्तिशाली लाइब्रेरी है जो C# एप्लीकेशन में Word दस्तावेज़ों को बनाने, उनमें हेरफेर करने और उन्हें परिवर्तित करने के लिए है। Aspose.Words द्वारा प्रदान की जाने वाली सुविधाओं में से एक है दस्तावेज़ों को विभिन्न प्रारूपों में परिवर्तित करते समय परिवर्तित तत्वों को रास्टराइज़ करने की क्षमता। इस गाइड में, हम आपको दिखाएंगे कि दस्तावेज़ को PCL प्रारूप में परिवर्तित करते समय परिवर्तित तत्वों के रास्टराइज़ेशन को अक्षम करने के लिए Aspose.Words for .NET के C# स्रोत कोड का उपयोग कैसे करें।

## Aspose.Words लाइब्रेरी को समझना

कोड में गोता लगाने से पहले, .NET के लिए Aspose.Words लाइब्रेरी को समझना महत्वपूर्ण है। Aspose.Words एक लोकप्रिय लाइब्रेरी है जो Word दस्तावेज़ों के साथ Word प्रोसेसिंग को आसान और कुशल बनाती है। यह Word दस्तावेज़ों को बनाने, संपादित करने और परिवर्तित करने के लिए कई प्रकार की सुविधाएँ प्रदान करता है, जिसमें रूपांतरण के दौरान रूपांतरित तत्वों को रास्टराइज़ करने का समर्थन भी शामिल है।

## Word दस्तावेज़ लोड करना

पहला चरण उस Word दस्तावेज़ को लोड करना है जिसे आप PCL प्रारूप में बदलना चाहते हैं। स्रोत फ़ाइल से दस्तावेज़ लोड करने के लिए Document वर्ग का उपयोग करें। यहाँ एक उदाहरण दिया गया है:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

इस उदाहरण में, हम दस्तावेज़ निर्देशिका में स्थित "Rendering.docx" दस्तावेज़ लोड कर रहे हैं।

## बैकअप विकल्प कॉन्फ़िगर करना

अगला चरण PCL प्रारूप में कनवर्ट करने के लिए सेव विकल्पों को कॉन्फ़िगर करना है। PclSaveOptions क्लास का उपयोग करें और RasterizeTransformedElements प्रॉपर्टी को false पर सेट करें। इसे करने का तरीका यहां बताया गया है:

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

हम एक नया PclSaveOptions ऑब्जेक्ट बनाते हैं और SaveFormat प्रॉपर्टी को SaveFormat.Pcl पर सेट करते हैं ताकि यह निर्दिष्ट किया जा सके कि हम दस्तावेज़ को PCL फ़ॉर्मेट में सहेजना चाहते हैं। इसके बाद, हम रूपांतरित तत्वों के रास्टराइज़ेशन को अक्षम करने के लिए RasterizeTransformedElements प्रॉपर्टी को false पर सेट करते हैं।

## दस्तावेज़ को PCL प्रारूप में परिवर्तित करना

अब जब हमने सेव ऑप्शन कॉन्फ़िगर कर लिया है, तो हम डॉक्यूमेंट को PCL फॉर्मेट में बदलने के लिए आगे बढ़ सकते हैं। सेव ऑप्शन निर्दिष्ट करके कन्वर्ट किए गए डॉक्यूमेंट को PCL फॉर्मेट में सेव करने के लिए डॉक्यूमेंट क्लास की सेव विधि का उपयोग करें। यहाँ एक उदाहरण दिया गया है :

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

इस उदाहरण में, हम निर्दिष्ट सहेजने के विकल्पों का उपयोग करके परिवर्तित दस्तावेज़ को "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl" के रूप में सहेजते हैं।

### .NET के लिए Aspose.Words के साथ "Rasterize Transformed Elements" सुविधा के लिए उदाहरण स्रोत कोड

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word दस्तावेज़ लोड करें


Document doc = new Document(dataDir + "Rendering.docx");

// PCL प्रारूप में रूपांतरण के लिए बैकअप विकल्प कॉन्फ़िगर करें
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// दस्तावेज़ को PCL प्रारूप में परिवर्तित करें
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## निष्कर्ष

इस गाइड में, हमने बताया कि दिए गए C# सोर्स कोड का उपयोग करके दस्तावेज़ को PCL फ़ॉर्मेट में परिवर्तित करते समय परिवर्तित तत्वों के रास्टराइज़ेशन को अक्षम करने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें। दिए गए चरणों का पालन करके, आप अपने Word दस्तावेज़ों को विभिन्न फ़ॉर्मेट में परिवर्तित करते समय परिवर्तित तत्वों के रास्टराइज़ेशन व्यवहार को आसानी से नियंत्रित कर सकते हैं। Aspose.Words परिवर्तित तत्वों के साथ काम करने के लिए जबरदस्त लचीलापन और शक्ति प्रदान करता है, जिससे आप अपनी विशिष्ट आवश्यकताओं के अनुसार परिवर्तित दस्तावेज़ बना सकते हैं।