---
title: Mhtml संसाधनों के लिए Cid URL निर्यात करें
linktitle: Mhtml संसाधनों के लिए Cid URL निर्यात करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ सहेजते समय MHTML संसाधनों के CID URL को निर्यात करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ MHTML संसाधनों के लिए CID URL निर्यात करने के लिए C# स्रोत कोड के माध्यम से मार्गदर्शन करेंगे। यह सुविधा आपको MHTML प्रारूप में दस्तावेज़ सहेजते समय MHTML संसाधनों के CID URL निर्यात करने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम निर्यात करने के लिए दस्तावेज़ लोड करेंगे। निर्दिष्ट निर्देशिका से दस्तावेज़ लोड करने के लिए निम्न कोड का उपयोग करें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 यह कोड एक उदाहरण बनाता है`Document` निर्दिष्ट निर्देशिका से दस्तावेज़ लोड करके.

## चरण 3: HTML बैकअप विकल्प कॉन्फ़िगर करना

अब हम MHTML संसाधनों के CID URL को निर्यात करने के लिए HTML सेव विकल्पों को कॉन्फ़िगर करेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 यह कोड एक उदाहरण बनाता है`HtmlSaveOptions` सेव फ़ॉर्मेट को MHTML पर सेट करके। यह सेटिंग करके MHTML संसाधनों के CID URL के निर्यात को भी सक्षम बनाता है`ExportCidUrlsForMhtmlResources` को`true`.

## चरण 4: दस्तावेज़ को MHTML में परिवर्तित करना और सहेजना

अंत में, हम पहले से कॉन्फ़िगर किए गए HTML सेविंग विकल्पों का उपयोग करके दस्तावेज़ को MHTML में बदल देंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

यह कोड दस्तावेज़ को MHTML में परिवर्तित करता है और इसे निर्यातित MHTML संसाधनों के CID URL के साथ एक फ़ाइल में सहेजता है।

### .NET के लिए Aspose.Words का उपयोग करके Mhtml संसाधनों के लिए Cid Urls निर्यात करने के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 दस्तावेज़ निर्देशिका में सही पथ निर्दिष्ट करना सुनिश्चित करें.`dataDir` चर।

अब आप सीख चुके हैं कि Aspose.Words for .NET का उपयोग करके MHTML प्रारूप में दस्तावेज़ सहेजते समय MHTML संसाधनों के CID URL को कैसे निर्यात किया जाए। इस ट्यूटोरियल में दिए गए चरण-दर-चरण गाइड का पालन करके, आप अपने निर्यात किए गए MHTML दस्तावेज़ों में CID URL को आसानी से प्रबंधित कर सकते हैं।

