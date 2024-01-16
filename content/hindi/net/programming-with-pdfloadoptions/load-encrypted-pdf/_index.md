---
title: एन्क्रिप्टेड पीडीएफ लोड करें
linktitle: एन्क्रिप्टेड पीडीएफ लोड करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके एन्क्रिप्टेड पीडीएफ लोड करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

जब आपके .NET एप्लिकेशन में पीडीएफ दस्तावेजों के साथ वर्ड प्रोसेसिंग होती है, तो पासवर्ड से सुरक्षित पीडीएफ फाइलों को लोड करना आवश्यक हो सकता है। .NET के लिए Aspose.Words एक शक्तिशाली लाइब्रेरी है जो एन्क्रिप्टेड पीडीएफ दस्तावेजों को लोड करने के लिए कार्यक्षमता प्रदान करती है। इस लेख में, हम आपको इस सुविधा को समझने और उपयोग करने के लिए चरण दर चरण मार्गदर्शन करेंगे।

## लोड एन्क्रिप्टेड पीडीएफ फ़ीचर को समझना

.NET के लिए Aspose.Words की लोड एन्क्रिप्टेड पीडीएफ सुविधा आपको पासवर्ड से सुरक्षित पीडीएफ फाइलों को लोड करने की अनुमति देती है। दस्तावेज़ लोड करते समय आप पासवर्ड निर्दिष्ट कर सकते हैं ताकि आप इसकी सामग्री तक पहुंच सकें और आवश्यकतानुसार इसमें हेरफेर कर सकें।

## चरण 1: एन्क्रिप्टेड पीडीएफ दस्तावेज़ लोड करना

पहला कदम एन्क्रिप्टेड पीडीएफ दस्तावेज़ को अपने एप्लिकेशन में लोड करना है। इसे करने का तरीका यहां बताया गया है:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

 एन्क्रिप्टेड पीडीएफ फ़ाइल के लिए सही पथ निर्दिष्ट करना सुनिश्चित करें`dataDir` चर।

## चरण 2: पीडीएफ दस्तावेज़ को एन्क्रिप्ट करना

 यदि आप भी अपने पीडीएफ दस्तावेज़ को एन्क्रिप्ट करना चाहते हैं, तो आप इसका उपयोग करके ऐसा कर सकते हैं`PdfSaveOptions` वर्ग और एन्क्रिप्शन विवरण निर्दिष्ट करना:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

यह निर्दिष्ट निर्देशिका में पीडीएफ दस्तावेज़ का एक एन्क्रिप्टेड संस्करण बनाएगा।

## चरण 3: एन्क्रिप्टेड पीडीएफ दस्तावेज़ को सहेजना

पीडीएफ दस्तावेज़ को अपलोड करने और वैकल्पिक रूप से एन्क्रिप्ट करने के बाद, आप इसे किसी अन्य प्रारूप में सहेज सकते हैं या अपनी विशिष्ट आवश्यकताओं के अनुसार इसे आगे संसाधित कर सकते हैं।

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## चरण 5: एन्क्रिप्टेड पीडीएफ दस्तावेज़ को पासवर्ड के साथ लोड करना

मेनट

हालाँकि, यदि आप एन्क्रिप्टेड पीडीएफ दस्तावेज़ को पासवर्ड के साथ लोड करना चाहते हैं, तो आपको इसका उपयोग करना होगा`PdfLoadOptions` दस्तावेज़ लोड करते समय क्लास बनाएं और पासवर्ड निर्दिष्ट करें:

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

 में सही पासवर्ड प्रदान करना सुनिश्चित करें`Password` चर।

### .NET के लिए Aspose.Words का उपयोग करके लोड एन्क्रिप्टेड पीडीएफ के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Pdf Document.pdf");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
	};

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);

	PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

	doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
        
```

## निष्कर्ष

इस लेख में, हमने पता लगाया कि .NET के लिए Aspose.Words की लोड एन्क्रिप्टेड पीडीएफ सुविधा का उपयोग कैसे करें। आपने सीखा कि एन्क्रिप्टेड पीडीएफ फाइलों को कैसे अपलोड किया जाए, पीडीएफ दस्तावेज़ को कैसे एन्क्रिप्ट किया जाए, पासवर्ड के साथ एन्क्रिप्टेड पीडीएफ को कैसे अपलोड किया जाए और मार्कडाउन प्रारूप में आउटपुट कैसे उत्पन्न किया जाए। सुरक्षित पीडीएफ दस्तावेज़ों के साथ वर्ड प्रोसेसिंग करते समय यह सुविधा बेहद उपयोगी है।


