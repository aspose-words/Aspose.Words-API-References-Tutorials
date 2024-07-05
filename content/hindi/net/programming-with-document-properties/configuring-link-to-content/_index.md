---
title: सामग्री से लिंक कॉन्फ़िगर करना
linktitle: सामग्री से लिंक कॉन्फ़िगर करना
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ में सामग्री को लिंक करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-document-properties/configuring-link-to-content/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ कंटेंट से लिंक करने के लिए C# सोर्स कोड के बारे में बताएँगे। यह सुविधा आपको किसी दस्तावेज़ में विशिष्ट कंटेंट से लिंक करने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ और कंस्ट्रक्टर बनाना

इस चरण में हम एक नया दस्तावेज़ बनाएंगे और कन्स्ट्रक्टर को आरंभ करेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: बुकमार्क बनाएं

अब हम दस्तावेज़ में एक बुकमार्क बनाएंगे। अंदर टेक्स्ट के साथ बुकमार्क बनाने के लिए निम्न कोड का उपयोग करें:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

यह कोड "MyBookmark" नामक एक बुकमार्क बनाता है और उसके अन्दर कुछ पाठ जोड़ता है।

## चरण 4: सामग्री लिंक सेट करना

अब हम डॉक्यूमेंट प्रॉपर्टी का उपयोग करके कंटेंट के लिए लिंक कॉन्फ़िगर करेंगे। कंटेंट के लिए लिंक जोड़ने और प्राप्त करने के लिए निम्न कोड का उपयोग करें:

```csharp
// दस्तावेज़ में सभी कस्टम गुणों की सूची प्राप्त करें.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// सामग्री-बद्ध गुण जोड़ें.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

यह कोड "बुकमार्क" नामक सामग्री-संबंधित प्रॉपर्टी को "MyBookmark" बुकमार्क के साथ जोड़ता है। फिर, यह सामग्री-संबंधित प्रॉपर्टी जानकारी जैसे लिंक स्थिति, लिंक स्रोत और प्रॉपर्टी मान को पुनः प्राप्त करता है।

### .NET के लिए Aspose.Words का उपयोग करके सामग्री से लिंक कॉन्फ़िगर करने के लिए उदाहरण स्रोत कोड

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// फ़ाइल से सभी कस्टम दस्तावेज़ गुणों की सूची प्राप्त करें.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// सामग्री संपत्ति से जुड़े जोड़ें.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

अब आपने सीखा है कि .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में सामग्री के लिए लिंक को कैसे कॉन्फ़िगर किया जाए। इस ट्यूटोरियल में दिए गए चरण-दर-चरण गाइड का पालन करके, आप आसानी से अपने दस्तावेज़ों में विशिष्ट सामग्री के लिए लिंक बना और कॉन्फ़िगर कर सकते हैं।