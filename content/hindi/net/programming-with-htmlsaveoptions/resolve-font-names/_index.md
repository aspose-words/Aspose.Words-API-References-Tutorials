---
title: फ़ॉन्ट नाम हल करें
linktitle: फ़ॉन्ट नाम हल करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ HTML में कनवर्ट करते समय गायब फ़ॉन्ट नामों को हल करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-htmlsaveoptions/resolve-font-names/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ गुम फ़ॉन्ट नामों को हल करने के लिए C# स्रोत कोड के माध्यम से मार्गदर्शन करेंगे। यह सुविधा आपको दस्तावेज़ को HTML में परिवर्तित करते समय गुम फ़ॉन्ट नामों को स्वचालित रूप से हल करने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम प्रोसेस किए जाने वाले दस्तावेज़ को लोड करेंगे। निर्दिष्ट निर्देशिका से दस्तावेज़ लोड करने के लिए निम्न कोड का उपयोग करें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 यह कोड एक उदाहरण बनाता है`Document` निर्दिष्ट निर्देशिका से दस्तावेज़ लोड करके.

## चरण 3: HTML बैकअप विकल्प कॉन्फ़िगर करना

अब हम रूपांतरण के दौरान गायब फ़ॉन्ट नामों को हल करने के लिए HTML सेव विकल्पों को कॉन्फ़िगर करेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 यह कोड एक उदाहरण बनाता है`HtmlSaveOptions` और सेट करता है`ResolveFontNames` विकल्प`true`HTML में कनवर्ट करते समय गायब फ़ॉन्ट नामों को हल करने के लिए। साथ ही,`PrettyFormat` विकल्प सेट है`true` अच्छी तरह से स्वरूपित HTML कोड प्राप्त करने के लिए.

## चरण 4: दस्तावेज़ को HTML में परिवर्तित करना और सहेजना

अंत में, हम पहले से कॉन्फ़िगर किए गए HTML सेविंग विकल्पों का उपयोग करके दस्तावेज़ को HTML में बदल देंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

यह कोड गायब फ़ॉन्ट नामों को स्वचालित रूप से हल करके दस्तावेज़ को HTML में परिवर्तित करता है, और परिवर्तित HTML फ़ाइल को निर्दिष्ट निर्देशिका में सहेजता है।

### .NET के लिए Aspose.Words का उपयोग करके फ़ॉन्ट नाम हल करने के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 दस्तावेज़ निर्देशिका में सही पथ निर्दिष्ट करना सुनिश्चित करें.`dataDir` चर।