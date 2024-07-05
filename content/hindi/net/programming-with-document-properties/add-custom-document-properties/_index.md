---
title: कस्टम दस्तावेज़ गुण जोड़ें
linktitle: कस्टम दस्तावेज़ गुण जोड़ें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ में कस्टम गुण जोड़ने के लिए चरण दर चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-document-properties/add-custom-document-properties/
---

इस ट्यूटोरियल में, हम आपको Aspose.Words for .NET के साथ दस्तावेज़ में कस्टम गुण जोड़ने के लिए C# स्रोत कोड के माध्यम से चलेंगे। यह सुविधा आपको दस्तावेज़ में कस्टम जानकारी जोड़ने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम उस Word दस्तावेज़ को लोड करेंगे जिसमें हम कस्टम गुण जोड़ना चाहते हैं। दस्तावेज़ को लोड करने के लिए निम्न कोड का उपयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहाँ आपका दस्तावेज़ स्थित है।

## चरण 3: कस्टम गुण जोड़ें

अब चलिए दस्तावेज़ में कस्टम गुण जोड़ते हैं। गुण जोड़ने के लिए निम्न कोड का उपयोग करें:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

यह कोड सबसे पहले जाँचता है कि क्या "अधिकृत" प्रॉपर्टी पहले से ही कस्टम प्रॉपर्टी में मौजूद है। अगर यह मौजूद है, तो प्रक्रिया बाधित हो जाती है। अन्यथा, कस्टम प्रॉपर्टी को दस्तावेज़ में जोड़ दिया जाता है।

### .NET के लिए Aspose.Words का उपयोग करके कस्टम दस्तावेज़ गुण जोड़ने के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 सुनिश्चित करें कि आपने सही दस्तावेज़ पथ निर्दिष्ट किया है.`dataDir` चर।

अब आप सीख चुके हैं कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में कस्टम गुण कैसे जोड़ें। इस ट्यूटोरियल में दिए गए चरण-दर-चरण गाइड का पालन करके, आप आसानी से अपने दस्तावेज़ों में अपने स्वयं के कस्टम गुण जोड़ सकते हैं।