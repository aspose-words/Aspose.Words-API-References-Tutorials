---
title: पीडीएफ की पेज रेंज लोड करें
linktitle: पीडीएफ की पेज रेंज लोड करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ एक विशिष्ट पीडीएफ पेज रेंज को लोड करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

इस ट्यूटोरियल में, हम आपको बताएंगे कि .NET के लिए Aspose.Words का उपयोग करके एक पीडीएफ दस्तावेज़ से एक विशिष्ट पृष्ठ श्रेणी को कैसे लोड किया जाए। नीचे दिए गए चरणों का पालन करें:

## चरण 1: पीडीएफ पेजों की एक श्रृंखला लोड हो रही है

पीडीएफ दस्तावेज़ से एक विशिष्ट पृष्ठ श्रेणी लोड करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 इस उदाहरण में, हम पीडीएफ दस्तावेज़ का पहला पृष्ठ लोड कर रहे हैं। आप के मान बदल सकते हैं`PageIndex` और`PageCount` वांछित पृष्ठ श्रेणी तक.

## चरण 2: दस्तावेज़ सहेजना

 अंत में, आप इसका उपयोग करके विशिष्ट पृष्ठ श्रेणी वाले दस्तावेज़ को सहेज सकते हैं`Save` तरीका:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

संपादित दस्तावेज़ को सहेजने के लिए सही पथ निर्दिष्ट करना सुनिश्चित करें।

बस इतना ही ! अब आपने .NET के लिए Aspose.Words का उपयोग करके एक PDF दस्तावेज़ से एक विशिष्ट पृष्ठ श्रेणी लोड कर ली है।

### .NET के लिए Aspose.Words का उपयोग करके पीडीएफ की लोड पेज रेंज के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
अपने पीडीएफ दस्तावेज़ों की निर्देशिका के लिए सही पथ निर्दिष्ट करना याद रखें।



