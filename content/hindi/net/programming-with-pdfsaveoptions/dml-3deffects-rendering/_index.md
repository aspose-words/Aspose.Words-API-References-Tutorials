---
title: 3D DML 3DEffects को PDF दस्तावेज़ में प्रस्तुत करें
linktitle: 3D DML 3DEffects को PDF दस्तावेज़ में प्रस्तुत करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: जानें कि .NET के लिए Aspose.Words के साथ PDF में कनवर्ट करते समय 3D DML प्रभावों के रेंडरिंग को कैसे सक्षम किया जाए।
type: docs
weight: 10
url: /hi/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

इस ट्यूटोरियल में, हम आपको Aspose.Words for .NET के साथ PDF में कनवर्ट करते समय 3D DML इफ़ेक्ट रेंडरिंग सक्षम करने के चरणों के बारे में बताएँगे। यह जेनरेट किए गए PDF दस्तावेज़ में 3D इफ़ेक्ट को बनाए रखता है। नीचे दिए गए चरणों का पालन करें:

## चरण 1: दस्तावेज़ लोड करना

उस दस्तावेज़ को अपलोड करके शुरू करें जिसे आप पीडीएफ में बदलना चाहते हैं:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

अपने दस्तावेज़ का सही पथ निर्दिष्ट करना सुनिश्चित करें.

## चरण 2: PDF सेव विकल्प कॉन्फ़िगर करें

PdfSaveOptions वर्ग का एक उदाहरण बनाएं और 3D DML प्रभावों का उन्नत रेंडरिंग सक्षम करें:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

यह विकल्प उत्पन्न पीडीएफ दस्तावेज़ में 3D प्रभाव बनाए रखता है।

## चरण 3: दस्तावेज़ को पीडीएफ में बदलें

 उपयोग`Save` दस्तावेज़ को पीडीएफ में परिवर्तित करने की विधि जिसमें सहेजने के विकल्प निर्दिष्ट किए गए हैं:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

परिवर्तित पीडीएफ को सहेजने के लिए सही पथ निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके Dml 3DEffects रेंडरिंग के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

इन चरणों का पालन करके, आप आसानी से Aspose.Words for .NET के साथ PDF में कनवर्ट करते समय 3D DML प्रभावों का प्रतिपादन सक्षम कर सकते हैं।

## निष्कर्ष

इस ट्यूटोरियल में, हमने बताया कि Aspose.Words for .NET के साथ PDF में कनवर्ट करते समय 3D DML इफ़ेक्ट की रेंडरिंग कैसे सक्षम करें। वर्णित चरणों का पालन करके, आप जेनरेट किए गए PDF दस्तावेज़ में 3D इफ़ेक्ट आसानी से रख सकते हैं। अपने मूल दस्तावेज़ के महत्वपूर्ण विज़ुअल इफ़ेक्ट को संरक्षित करने के लिए इस सुविधा का उपयोग करें।


### अक्सर पूछे जाने वाले प्रश्नों

#### प्रश्न: PDF दस्तावेज़ में 3D DML प्रभाव प्रस्तुत करना क्या है?
उत्तर: PDF दस्तावेज़ में 3D DML प्रभाव प्रस्तुत करना, दस्तावेज़ को PDF प्रारूप में परिवर्तित करते समय 3D प्रभाव बनाए रखने की क्षमता को संदर्भित करता है। यह दृश्य प्रभावों को संरक्षित करता है और यह सुनिश्चित करता है कि उत्पन्न PDF दस्तावेज़ मूल दस्तावेज़ जैसा दिखता है।

#### प्रश्न: मैं Aspose.Words for .NET के साथ PDF में कनवर्ट करते समय 3D DML प्रभाव की रेंडरिंग कैसे सक्षम कर सकता हूं?
उत्तर: Aspose.Words for .NET के साथ PDF में कनवर्ट करते समय 3D DML प्रभाव के रेंडरिंग को सक्षम करने के लिए, इन चरणों का पालन करें:

 इसका एक उदाहरण बनाएं`Document` वर्ड दस्तावेज़ का पथ निर्दिष्ट करने वाला क्लास.

 इसका एक उदाहरण बनाएं`PdfSaveOptions` वर्ग और सेट`Dml3DEffectsRenderingMode`संपत्ति को`Dml3DEffectsRenderingMode.Advanced` 3D DML प्रभावों के उन्नत रेंडरिंग को सक्षम करने के लिए।

 उपयोग`Save` की विधि`Document`सहेजें विकल्प निर्दिष्ट करके दस्तावेज़ को पीडीएफ प्रारूप में सहेजने के लिए क्लास का उपयोग करें।

#### प्रश्न: मैं कैसे जांच सकता हूं कि उत्पन्न पीडीएफ दस्तावेज़ में 3D डीएमएल प्रभाव प्रस्तुत किया गया है या नहीं?
उत्तर: यह जाँचने के लिए कि क्या जेनरेट किए गए PDF दस्तावेज़ में 3D DML प्रभाव रेंडर किए गए हैं, PDF फ़ाइल को Adobe Acrobat Reader जैसे संगत PDF व्यूअर के साथ खोलें और दस्तावेज़ की जाँच करें। आपको 3D प्रभाव वैसे ही दिखाई देने चाहिए जैसे वे मूल दस्तावेज़ में दिखाई देते हैं।



