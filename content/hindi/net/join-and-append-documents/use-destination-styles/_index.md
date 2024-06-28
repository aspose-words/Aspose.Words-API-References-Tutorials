---
title: गंतव्य शैलियों का प्रयोग करें
linktitle: गंतव्य शैलियों का प्रयोग करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके गंतव्य दस्तावेज़ शैलियों को लागू करते समय Word दस्तावेज़ों को जोड़ना और जोड़ना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/use-destination-styles/
---

यह ट्यूटोरियल आपको .NET के लिए Aspose.Words के उपयोग गंतव्य शैलियाँ सुविधा का उपयोग करने की प्रक्रिया में मार्गदर्शन करेगा। यह सुविधा आपको गंतव्य दस्तावेज़ की शैलियों को लागू करते हुए Word दस्तावेज़ों में शामिल होने और जोड़ने की अनुमति देती है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. .NET के लिए Aspose.Words स्थापित। आप इसे Aspose वेबसाइट से डाउनलोड कर सकते हैं या NuGet के माध्यम से इंस्टॉल कर सकते हैं।
2. विजुअल स्टूडियो या कोई अन्य C# विकास वातावरण।

## चरण 1: दस्तावेज़ निर्देशिकाएँ प्रारंभ करें

 सबसे पहले, आपको अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करना होगा। का मान संशोधित करें`dataDir` उस पथ के लिए परिवर्तनीय जहां आपके दस्तावेज़ स्थित हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: स्रोत और गंतव्य दस्तावेज़ लोड करें

इसके बाद, आपको Aspose.Words का उपयोग करके स्रोत और गंतव्य दस्तावेज़ों को लोड करना होगा।`Document` कक्षा। में फ़ाइल नाम अपडेट करें`Document` आपके दस्तावेज़ के नाम के अनुसार कंस्ट्रक्टर।

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## चरण 3: स्रोत दस्तावेज़ को गंतव्य शैलियों के साथ जोड़ें

 गंतव्य दस्तावेज़ की शैलियों को लागू करते समय स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ने के लिए, आप इसका उपयोग कर सकते हैं`AppendDocument` की विधि`Document` के साथ कक्षा`ImportFormatMode.UseDestinationStyles` पैरामीटर.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## चरण 4: अंतिम दस्तावेज़ सहेजें

 अंत में, मर्ज किए गए दस्तावेज़ को उपयोग गंतव्य शैलियाँ सुविधा सक्षम करके सहेजें`Save` की विधि`Document` कक्षा।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके गंतव्य शैलियों का उपयोग करने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके C# में "गंतव्य शैलियों का उपयोग करें" सुविधा के लिए पूर्ण स्रोत कोड यहां दिया गया है:

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// गंतव्य दस्तावेज़ की शैलियों का उपयोग करके स्रोत दस्तावेज़ जोड़ें।
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके गंतव्य शैलियों का उपयोग करें सुविधा को सफलतापूर्वक कार्यान्वित किया है। अंतिम दस्तावेज़ में लागू गंतव्य दस्तावेज़ की शैलियों के साथ मर्ज की गई सामग्री शामिल होगी।