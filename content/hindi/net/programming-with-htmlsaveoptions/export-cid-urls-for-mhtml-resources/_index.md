---
title: एमएचटीएमएल संसाधनों के लिए सीआईडी यूआरएल निर्यात करें
linktitle: एमएचटीएमएल संसाधनों के लिए सीआईडी यूआरएल निर्यात करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ सहेजते समय MHTML संसाधनों के CID URL निर्यात करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ MHTML संसाधनों के लिए CID URL निर्यात करने के लिए C# स्रोत कोड के बारे में बताएंगे। यह सुविधा आपको किसी दस्तावेज़ को एमएचटीएमएल प्रारूप में सहेजते समय एमएचटीएमएल संसाधनों के सीआईडी यूआरएल निर्यात करने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएं। सुनिश्चित करें कि आपके प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम दस्तावेज़ को निर्यात करने के लिए लोड करेंगे। किसी निर्दिष्ट निर्देशिका से दस्तावेज़ लोड करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 यह कोड एक उदाहरण बनाता है`Document` निर्दिष्ट निर्देशिका से दस्तावेज़ लोड करके।

## चरण 3: HTML बैकअप विकल्पों को कॉन्फ़िगर करना

अब हम एमएचटीएमएल संसाधनों के सीआईडी यूआरएल निर्यात करने के लिए एचटीएमएल सेव विकल्पों को कॉन्फ़िगर करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 यह कोड एक उदाहरण बनाता है`HtmlSaveOptions` सेव फॉर्मेट को एमएचटीएमएल पर सेट करके। यह सेटिंग द्वारा MHTML संसाधनों के CID URL के निर्यात को भी सक्षम बनाता है`ExportCidUrlsForMhtmlResources` को`true`.

## चरण 4: दस्तावेज़ को MHTML में परिवर्तित करना और सहेजना

अंत में, हम पहले कॉन्फ़िगर किए गए HTML बचत विकल्पों का उपयोग करके दस्तावेज़ को MHTML में परिवर्तित करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

यह कोड दस्तावेज़ को MHTML में परिवर्तित करता है और इसे निर्यातित MHTML संसाधनों के CID URL वाली फ़ाइल में सहेजता है।

### .NET के लिए Aspose.Words का उपयोग करके Mhtml संसाधनों के लिए निर्यात सीआईडी यूआरएल के लिए उदाहरण स्रोत कोड

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

 दस्तावेज़ निर्देशिका में सही पथ निर्दिष्ट करना सुनिश्चित करें`dataDir` चर।

अब आपने सीख लिया है कि .NET के लिए Aspose.Words का उपयोग करके MHTML प्रारूप में किसी दस्तावेज़ को सहेजते समय MHTML संसाधनों के CID URL को कैसे निर्यात किया जाए। इस ट्यूटोरियल में दिए गए चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने निर्यात किए गए एमएचटीएमएल दस्तावेज़ों में सीआईडी यूआरएल आसानी से प्रबंधित कर सकते हैं।

