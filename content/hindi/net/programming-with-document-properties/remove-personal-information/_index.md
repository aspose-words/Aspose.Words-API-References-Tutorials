---
title: व्यक्तिगत जानकारी हटाएँ
linktitle: व्यक्तिगत जानकारी हटाएँ
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ से व्यक्तिगत जानकारी हटाने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-document-properties/remove-personal-information/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words वाले दस्तावेज़ से व्यक्तिगत जानकारी हटाने के लिए C# स्रोत कोड के बारे में बताएंगे। यह सुविधा आपको दस्तावेज़ से संवेदनशील व्यक्तिगत जानकारी, जैसे लेखक पहचान डेटा, को हटाने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएं। सुनिश्चित करें कि आपके प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम उस Word दस्तावेज़ को अपलोड करेंगे जिससे हम व्यक्तिगत जानकारी हटाना चाहते हैं। दस्तावेज़ लोड करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आपका दस्तावेज़ स्थित है।

## चरण 3: व्यक्तिगत जानकारी हटाएँ

 अब हम सेटिंग करके व्यक्तिगत जानकारी को हटाने में सक्षम करेंगे`RemovePersonalInformation`संपत्ति को`true`. निम्नलिखित कोड का प्रयोग करें:

```csharp
doc.RemovePersonalInformation = true;
```

यह कोड दस्तावेज़ में व्यक्तिगत जानकारी को हटाने को सक्रिय करता है।

## चरण 4: दस्तावेज़ सहेजना

अंत में, हम व्यक्तिगत जानकारी हटाकर दस्तावेज़ को सहेज लेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

यह कोड दस्तावेज़ को हटाई गई व्यक्तिगत जानकारी के साथ एक नई फ़ाइल में सहेजता है।

### .NET के लिए Aspose.Words का उपयोग करके व्यक्तिगत जानकारी हटाने के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 में सही दस्तावेज़ पथ निर्दिष्ट करना सुनिश्चित करें`dataDir` चर।

अब आपने सीख लिया है कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ से व्यक्तिगत जानकारी कैसे हटाई जाती है। इस ट्यूटोरियल में दिए गए चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने दस्तावेज़ों से संवेदनशील जानकारी आसानी से हटा सकते हैं।