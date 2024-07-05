---
title: राउंडट्रिप जानकारी निर्यात करें
linktitle: राउंडट्रिप जानकारी निर्यात करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ HTML के रूप में दस्तावेज़ सहेजते समय राउंडट्रिप जानकारी निर्यात करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

इस ट्यूटोरियल में, हम आपको Aspose.Words for .NET के साथ दस्तावेज़ से राउंडट्रिप जानकारी निर्यात करने के लिए C# स्रोत कोड के माध्यम से मार्गदर्शन करेंगे। यह सुविधा आपको निर्यात की गई HTML फ़ाइल में राउंडट्रिप जानकारी शामिल करने की अनुमति देती है, जिससे मूल दस्तावेज़ में किए गए परिवर्तनों को पुनः प्राप्त करना आसान हो जाता है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम निर्यात करने के लिए दस्तावेज़ लोड करेंगे। निर्दिष्ट निर्देशिका से दस्तावेज़ लोड करने के लिए निम्न कोड का उपयोग करें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 यह कोड एक उदाहरण बनाता है`Document` निर्दिष्ट निर्देशिका से दस्तावेज़ लोड करके.

## चरण 3: HTML बैकअप विकल्प कॉन्फ़िगर करना

अब हम दस्तावेज़ की राउंडट्रिप जानकारी को निर्यात करने के लिए HTML सेव विकल्पों को कॉन्फ़िगर करेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 यह कोड एक उदाहरण बनाता है`HtmlSaveOptions`और सेट करता है`ExportRoundtripInformation` विकल्प`true` निर्यात करते समय राउंडट्रिप जानकारी शामिल करने के लिए.

## चरण 4: दस्तावेज़ को HTML में परिवर्तित करना और सहेजना

अंत में, हम पहले से कॉन्फ़िगर किए गए HTML सेविंग विकल्पों का उपयोग करके दस्तावेज़ को HTML में बदल देंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

यह कोड राउंडट्रिप जानकारी सहित दस्तावेज़ को HTML में परिवर्तित करता है, और निर्यातित HTML फ़ाइल को निर्दिष्ट निर्देशिका में सहेजता है।

### .NET के लिए Aspose.Words का उपयोग करके राउंडट्रिप जानकारी निर्यात करने के लिए उदाहरण स्रोत कोड


```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 दस्तावेज़ निर्देशिका में सही पथ निर्दिष्ट करना सुनिश्चित करें.`dataDir` चर।