---
title: पेज सेटअप और अनुभाग स्वरूपण सेट करें
linktitle: पेज सेटअप और अनुभाग स्वरूपण सेट करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ का लेआउट और अनुभाग स्वरूपण सेट करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ लेआउट और सेक्शन फ़ॉर्मेटिंग सेट करने के लिए C# सोर्स कोड के बारे में बताएँगे। यह सुविधा आपको पेज ओरिएंटेशन, मार्जिन और पेपर साइज़ सेट करने देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ बनाना

इस चरण में, हम एक नया दस्तावेज़ बनाएंगे। दस्तावेज़ बनाने और कंस्ट्रक्टर को आरंभ करने के लिए निम्न कोड का उपयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहाँ आप दस्तावेज़ को सहेजना चाहते हैं।

## चरण 3: लेआउट सेट करना और दस्तावेज़ सहेजना

अब दस्तावेज़ लेआउट को कॉन्फ़िगर करें। ओरिएंटेशन, मार्जिन और पेपर साइज़ सेट करने के लिए निम्न कोड का उपयोग करें:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

यह कोड पृष्ठ ओरिएंटेशन को लैंडस्केप, बाएं मार्जिन को 50, तथा पेपर आकार को 10x14 पर सेट करेगा।

### .NET के लिए Aspose.Words का उपयोग करके पृष्ठ सेटअप और अनुभाग स्वरूपण सेट करने के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

 उस निर्देशिका का सही पथ निर्दिष्ट करना सुनिश्चित करें जहाँ आप दस्तावेज़ को सहेजना चाहते हैं`dataDir` चर।

अब आप सीख चुके हैं कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ के लेआउट और सेक्शन फ़ॉर्मेटिंग को कैसे कॉन्फ़िगर किया जाए। इस ट्यूटोरियल में दिए गए चरण-दर-चरण गाइड का पालन करके, आप आसानी से अपने दस्तावेज़ों के लेआउट और फ़ॉर्मेटिंग को कस्टमाइज़ कर सकते हैं।