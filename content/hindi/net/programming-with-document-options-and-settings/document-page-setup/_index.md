---
title: दस्तावेज़ पृष्ठ सेटअप
linktitle: दस्तावेज़ पृष्ठ सेटअप
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ लेआउट सेट अप करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-document-options-and-settings/document-page-setup/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ दस्तावेज़ लेआउट कॉन्फ़िगर करने के लिए C# स्रोत कोड के माध्यम से चलेंगे। यह सुविधा आपको लेआउट मोड, प्रति पंक्ति वर्णों की संख्या और प्रति पृष्ठ पंक्तियों की संख्या सेट करने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम वह Word दस्तावेज़ लोड करेंगे जिसे हम कॉन्फ़िगर करना चाहते हैं। दस्तावेज़ लोड करने के लिए निम्न कोड का उपयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहाँ आपका दस्तावेज़ स्थित है।

## चरण 3: लेआउट सेट करना

अब दस्तावेज़ लेआउट को कॉन्फ़िगर करें। लेआउट मोड, प्रति पंक्ति वर्णों की संख्या और प्रति पृष्ठ पंक्तियों की संख्या सेट करने के लिए निम्न कोड का उपयोग करें:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

यह कोड लेआउट मोड को "ग्रिड" पर सेट करता है और फिर प्रति पंक्ति वर्णों की संख्या और प्रति पृष्ठ पंक्तियों की संख्या निर्दिष्ट करता है।

### .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ पृष्ठ सेटअप के लिए उदाहरण स्रोत कोड


```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// दस्तावेज़ ग्रिड व्यवहार को परिभाषित करने की अनुमति देते हुए किसी अनुभाग के लिए लेआउट मोड सेट करें।
	// ध्यान दें कि दस्तावेज़ ग्रिड टैब एमएस वर्ड के पेज सेटअप संवाद में दिखाई देता है
	// यदि किसी एशियाई भाषा को संपादन भाषा के रूप में परिभाषित किया जाता है।
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 सुनिश्चित करें कि आपने सही दस्तावेज़ पथ निर्दिष्ट किया है.`dataDir` चर।

अब आप सीख चुके हैं कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ के लेआउट को कैसे कॉन्फ़िगर किया जाए। इस ट्यूटोरियल में दिए गए चरण-दर-चरण गाइड का पालन करके, आप आसानी से अपने दस्तावेज़ों के लेआउट को कस्टमाइज़ कर सकते हैं।