---
title: सामग्री से लिंक कॉन्फ़िगर करना
linktitle: सामग्री से लिंक कॉन्फ़िगर करना
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ में सामग्री से लिंकिंग स्थापित करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-document-properties/configuring-link-to-content/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ सामग्री को लिंक करने के लिए C# स्रोत कोड के बारे में बताएंगे। यह सुविधा आपको किसी दस्तावेज़ में विशिष्ट सामग्री से लिंक करने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएं। सुनिश्चित करें कि आपके प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ और कंस्ट्रक्टर बनाना

इस चरण में हम एक नया दस्तावेज़ बनाएंगे और कंस्ट्रक्टर को इनिशियलाइज़ करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: एक बुकमार्क बनाएं

अब हम दस्तावेज़ में एक बुकमार्क बनाएंगे। अंदर टेक्स्ट वाला बुकमार्क बनाने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

यह कोड "MyBookmark" नामक एक बुकमार्क बनाता है और उसके अंदर कुछ टेक्स्ट जोड़ता है।

## चरण 4: सामग्री लिंक सेट करना

अब हम दस्तावेज़ गुणों का उपयोग करके सामग्री के लिंक को कॉन्फ़िगर करेंगे। सामग्री में लिंक जोड़ने और पुनः प्राप्त करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
// दस्तावेज़ में सभी कस्टम संपत्तियों की सूची प्राप्त करें।
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// एक सामग्री-बद्ध संपत्ति जोड़ें।
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

यह कोड बुकमार्क "MyBookmark" के साथ "बुकमार्क" नामक एक सामग्री-संबंधित संपत्ति जोड़ता है। फिर, यह सामग्री से संबंधित संपत्ति की जानकारी जैसे लिंक स्थिति, लिंक स्रोत और संपत्ति मूल्य पुनर्प्राप्त करता है।

### .NET के लिए Aspose.Words का उपयोग करके सामग्री से लिंक को कॉन्फ़िगर करने के लिए उदाहरण स्रोत कोड

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// फ़ाइल से सभी कस्टम दस्तावेज़ गुणों की सूची पुनर्प्राप्त करें।
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// सामग्री संपत्ति से लिंक जोड़ें.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

अब आपने सीख लिया है कि .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में सामग्री के लिंक को कैसे कॉन्फ़िगर किया जाए। इस ट्यूटोरियल में दिए गए चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने दस्तावेज़ों में विशिष्ट सामग्री के लिंक आसानी से बना और कॉन्फ़िगर कर सकते हैं।