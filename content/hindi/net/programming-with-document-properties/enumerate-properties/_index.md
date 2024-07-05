---
title: गुण गिनाएँ
linktitle: गुण गिनाएँ
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ गुणों की गणना करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-document-properties/enumerate-properties/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ दस्तावेज़ गुणों को सूचीबद्ध करने के लिए C# स्रोत कोड के माध्यम से चलेंगे। यह सुविधा आपको दस्तावेज़ के अंतर्निहित और कस्टम गुणों तक पहुँचने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम उस Word दस्तावेज़ को लोड करेंगे जिसके गुण हम सूचीबद्ध करना चाहते हैं। दस्तावेज़ को लोड करने के लिए निम्न कोड का उपयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहाँ आपका दस्तावेज़ स्थित है।

## चरण 3: गुणों की गणना करना

अब आइए दस्तावेज़ गुणों को सूचीबद्ध करें, दोनों अंतर्निहित और कस्टम गुण। निम्नलिखित कोड का उपयोग करें:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

यह कोड दस्तावेज़ का नाम प्रदर्शित करता है और फिर अंतर्निहित और कस्टम गुणों को उनके नाम और मान प्रदर्शित करते हुए सूचीबद्ध करता है।

### .NET के लिए Aspose.Words का उपयोग करके गुण गणना हेतु उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 सुनिश्चित करें कि आपने सही दस्तावेज़ पथ निर्दिष्ट किया है.`dataDir` चर।

अब आप सीख चुके हैं कि .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ गुणों की गणना कैसे करें। इस ट्यूटोरियल में दिए गए चरण-दर-चरण गाइड का पालन करके, आप आसानी से अपने दस्तावेज़ों के गुणों तक पहुँच सकते हैं और उन्हें देख सकते हैं।

