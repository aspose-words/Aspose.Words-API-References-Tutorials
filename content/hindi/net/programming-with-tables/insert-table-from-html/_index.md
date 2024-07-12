---
title: HTML से तालिका सम्मिलित करें
linktitle: HTML से तालिका सम्मिलित करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ HTML से Word दस्तावेज़ में तालिका सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/insert-table-from-html/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके HTML से Word दस्तावेज़ में टेबल कैसे डालें। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत तक, आप प्रोग्रामेटिक रूप से अपने Word दस्तावेज़ों में HTML से टेबल डालने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. Visual Studio लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. Aspose.Words for .NET लाइब्रेरी में संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ बनाना और दस्तावेज़ जनरेटर को आरंभ करना
दस्तावेज़ और दस्तावेज़ जनरेटर के साथ वर्ड्स प्रोसेसिंग शुरू करने के लिए, इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ निर्माण
Document doc = new Document();

// दस्तावेज़ जनरेटर आरंभ करें
DocumentBuilder builder = new DocumentBuilder(doc);
```

"आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से प्रतिस्थापित करना सुनिश्चित करें।

## चरण 3: HTML से तालिका सम्मिलित करना
इसके बाद, हम HTML कोड का उपयोग करके दस्तावेज़ में तालिका सम्मिलित करेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 यहाँ हम उपयोग करते हैं`InsertHtml` दस्तावेज़ बिल्डर की विधि तालिका युक्त HTML सम्मिलित करने के लिए। निर्दिष्ट HTML दो पंक्तियों और प्रत्येक पंक्ति में दो कक्षों वाली एक तालिका बनाता है। आप अपनी ज़रूरतों के अनुसार HTML कोड को संशोधित करके तालिका की सामग्री को अनुकूलित कर सकते हैं।

## चरण 4: संशोधित दस्तावेज़ को सहेजना
अंत में, हमें HTML से डाली गई तालिका के साथ संशोधित दस्तावेज़ को सहेजना होगा। निम्नलिखित कोड का उपयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके HTML से तालिका सम्मिलित करने के लिए नमूना स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// ध्यान दें कि AutoFitSettings HTML से डाली गई तालिकाओं पर लागू नहीं होती है।
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके HTML से Word दस्तावेज़ में टेबल कैसे डालें। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप HTML से अपने Word दस्तावेज़ों में प्रोग्रामेटिक रूप से टेबल डाल सकते हैं। यह सुविधा आपको HTML स्रोतों से सारणीबद्ध डेटा को अपने Word दस्तावेज़ों में परिवर्तित और आयात करने की अनुमति देती है।
