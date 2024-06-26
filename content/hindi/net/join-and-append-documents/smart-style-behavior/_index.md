---
title: स्मार्ट स्टाइल व्यवहार
linktitle: स्मार्ट स्टाइल व्यवहार
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों को जोड़ते और जोड़ते समय स्मार्ट स्टाइल व्यवहार कैसे बनाए रखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/smart-style-behavior/
---

यह ट्यूटोरियल आपको .NET के लिए Aspose.Words की स्मार्ट स्टाइल बिहेवियर सुविधा का उपयोग करने की प्रक्रिया में मार्गदर्शन करेगा। यह सुविधा आपको स्मार्ट स्टाइल व्यवहार को बनाए रखते हुए Word दस्तावेज़ों में शामिल होने और जोड़ने की अनुमति देती है।

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

## चरण 3: गंतव्य दस्तावेज़ में एक पेज ब्रेक डालें

 यह सुनिश्चित करने के लिए कि संलग्न सामग्री गंतव्य दस्तावेज़ में एक नए पृष्ठ पर दिखाई देती है, आप इसका उपयोग करके एक पृष्ठ विराम सम्मिलित कर सकते हैं`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## चरण 4: स्मार्ट स्टाइल व्यवहार विकल्प सेट करें

एपेंड ऑपरेशन के दौरान स्मार्ट स्टाइल व्यवहार को सक्षम करने के लिए, आपको इसका एक उदाहरण बनाना होगा`ImportFormatOptions` और सेट करें`SmartStyleBehavior`संपत्ति को`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## चरण 5: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 अब, आप इसका उपयोग करके स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ सकते हैं`InsertDocument` की विधि`DocumentBuilder` कक्षा। उपयोग`ImportFormatMode.UseDestinationStyles` पैरामीटर और पास करें`ImportFormatOptions` स्मार्ट स्टाइल व्यवहार को बनाए रखने के लिए ऑब्जेक्ट।

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## चरण 6: अंतिम दस्तावेज़ सहेजें

 अंत में, स्मार्ट स्टाइल बिहेवियर सुविधा का उपयोग करके मर्ज किए गए दस्तावेज़ को सहेजें`Save` की विधि`Document` कक्षा।

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके स्मार्ट स्टाइल व्यवहार के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके C# में "स्मार्ट स्टाइल बिहेवियर" सुविधा के लिए पूर्ण स्रोत कोड यहां दिया गया है:
 
```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
	builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके स्मार्ट स्टाइल बिहेवियर सुविधा को सफलतापूर्वक कार्यान्वित किया है। अंतिम दस्तावेज़ में स्मार्ट स्टाइल व्यवहार को बनाए रखते हुए मर्ज की गई सामग्री शामिल होगी।