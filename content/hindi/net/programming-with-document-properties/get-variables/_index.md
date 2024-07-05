---
title: चर प्राप्त करें
linktitle: चर प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ चर पुनर्प्राप्त करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-document-properties/get-variables/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ दस्तावेज़ से चर प्राप्त करने के लिए C# स्रोत कोड के माध्यम से मार्गदर्शन करेंगे। यह सुविधा आपको दस्तावेज़ में परिभाषित चर तक पहुँचने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम उस Word दस्तावेज़ को लोड करेंगे जिससे हम वेरिएबल्स को पुनः प्राप्त करना चाहते हैं। दस्तावेज़ को लोड करने के लिए निम्न कोड का उपयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहाँ आपका दस्तावेज़ स्थित है।

## चरण 3: चर पुनर्प्राप्त करना

अब हम दस्तावेज़ में परिभाषित चरों को पुनः प्राप्त करेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

यह कोड दस्तावेज़ चर में प्रत्येक कुंजी-मान युग्म पर पुनरावृति करता है और प्रत्येक चर का नाम और मान प्राप्त करता है। फिर प्रत्येक चर के लिए जानकारी प्रदर्शित करने के लिए चरों को संयोजित किया जाता है।

### .NET के लिए Aspose.Words का उपयोग करके वेरिएबल्स प्राप्त करने के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

 सुनिश्चित करें कि आपने सही दस्तावेज़ पथ निर्दिष्ट किया है.`dataDir` चर।

अब आप सीख चुके हैं कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ से चर कैसे प्राप्त करें। इस ट्यूटोरियल में दिए गए चरण-दर-चरण गाइड का पालन करके, आप आसानी से अपने दस्तावेज़ों से चर तक पहुँच सकते हैं और उन्हें देख सकते हैं।