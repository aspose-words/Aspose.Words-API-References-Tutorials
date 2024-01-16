---
title: विकल्प देखें
linktitle: विकल्प देखें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ प्रदर्शन विकल्पों को कॉन्फ़िगर करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-document-options-and-settings/view-options/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ डिस्प्ले विकल्पों को कॉन्फ़िगर करने के लिए C# स्रोत कोड के बारे में बताएंगे। यह सुविधा आपको दस्तावेज़ में व्यू मोड और ज़ूम स्तर को अनुकूलित करने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएं। सुनिश्चित करें कि आपके प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम Word दस्तावेज़ को लोड करेंगे जिसके लिए हम डिस्प्ले विकल्पों को कॉन्फ़िगर करना चाहते हैं। दस्तावेज़ लोड करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आपका दस्तावेज़ स्थित है।

## चरण 3: प्रदर्शन विकल्पों को कॉन्फ़िगर करना

अब हम दस्तावेज़ प्रदर्शन विकल्पों को कॉन्फ़िगर करेंगे। डिस्प्ले मोड और ज़ूम स्तर सेट करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

यह कोड व्यू मोड को "पेजलेआउट" और ज़ूम स्तर को 50% पर सेट करता है।

### .NET के लिए Aspose.Words का उपयोग करके दृश्य विकल्प के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 में सही दस्तावेज़ पथ निर्दिष्ट करना सुनिश्चित करें`dataDir` चर।

अब आपने सीख लिया है कि .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ प्रदर्शन विकल्पों को कैसे कॉन्फ़िगर किया जाए। इस ट्यूटोरियल में दिए गए चरण-दर-चरण मार्गदर्शिका का पालन करके, आप आसानी से अपने दस्तावेज़ों के प्रदर्शन को अनुकूलित कर सकते हैं।