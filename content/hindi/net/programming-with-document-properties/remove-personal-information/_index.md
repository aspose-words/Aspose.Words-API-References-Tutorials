---
title: व्यक्तिगत जानकारी हटाएँ
linktitle: व्यक्तिगत जानकारी हटाएँ
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ से व्यक्तिगत जानकारी हटाने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-document-properties/remove-personal-information/
---

इस ट्यूटोरियल में, हम आपको Aspose.Words for .NET के साथ दस्तावेज़ से व्यक्तिगत जानकारी निकालने के लिए C# स्रोत कोड के बारे में बताएँगे। यह सुविधा आपको दस्तावेज़ से संवेदनशील व्यक्तिगत जानकारी, जैसे कि लेखक पहचान डेटा, निकालने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम वह Word दस्तावेज़ अपलोड करेंगे जिससे हम व्यक्तिगत जानकारी हटाना चाहते हैं। दस्तावेज़ लोड करने के लिए निम्न कोड का उपयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहाँ आपका दस्तावेज़ स्थित है।

## चरण 3: व्यक्तिगत जानकारी हटाएं

 अब हम सेटिंग करके व्यक्तिगत जानकारी को हटाने को सक्षम करेंगे`RemovePersonalInformation`संपत्ति को`true`.निम्नलिखित कोड का उपयोग करें:

```csharp
doc.RemovePersonalInformation = true;
```

यह कोड दस्तावेज़ में व्यक्तिगत जानकारी को हटाने को सक्रिय करता है।

## चरण 4: दस्तावेज़ को सहेजना

अंत में, हम दस्तावेज़ को व्यक्तिगत जानकारी हटाकर सहेज लेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

यह कोड व्यक्तिगत जानकारी हटाकर दस्तावेज़ को एक नई फ़ाइल में सहेज देता है।

### .NET के लिए Aspose.Words का उपयोग करके व्यक्तिगत जानकारी हटाने के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 सुनिश्चित करें कि आपने सही दस्तावेज़ पथ निर्दिष्ट किया है.`dataDir` चर।

अब आप सीख चुके हैं कि Aspose.Words for .NET का उपयोग करके किसी दस्तावेज़ से व्यक्तिगत जानकारी कैसे हटाई जाती है। इस ट्यूटोरियल में दिए गए चरण-दर-चरण गाइड का पालन करके, आप आसानी से अपने दस्तावेज़ों से संवेदनशील जानकारी हटा सकते हैं।