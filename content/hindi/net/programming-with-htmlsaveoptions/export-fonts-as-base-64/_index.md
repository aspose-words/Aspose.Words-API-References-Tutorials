---
title: आधार 64 के रूप में फ़ॉन्ट निर्यात करें
linktitle: आधार 64 के रूप में फ़ॉन्ट निर्यात करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ किसी दस्तावेज़ को सहेजते समय आधार 64 फ़ॉन्ट निर्यात करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ बेस 64 फ़ॉन्ट निर्यात करने के लिए C# स्रोत कोड के बारे में बताएंगे। यह सुविधा आपको किसी दस्तावेज़ को HTML प्रारूप में सहेजते समय बेस 64 डेटा के रूप में फ़ॉन्ट निर्यात करने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएं। सुनिश्चित करें कि आपके प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम दस्तावेज़ को निर्यात करने के लिए लोड करेंगे। किसी निर्दिष्ट निर्देशिका से दस्तावेज़ लोड करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 यह कोड एक उदाहरण बनाता है`Document` निर्दिष्ट निर्देशिका से दस्तावेज़ लोड करके।

## चरण 3: HTML बैकअप विकल्पों को कॉन्फ़िगर करना

अब हम बेस 64 फ़ॉन्ट्स को निर्यात करने के लिए HTML सेव विकल्पों को कॉन्फ़िगर करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 यह कोड एक उदाहरण बनाता है`HtmlSaveOptions` और सेट`ExportFontsAsBase64` को`true` यह निर्दिष्ट करने के लिए कि HTML के रूप में सहेजते समय फ़ॉन्ट को बेस 64 डेटा के रूप में निर्यात किया जाना चाहिए।

## चरण 4: दस्तावेज़ को HTML में परिवर्तित करना और सहेजना

अंत में, हम पहले कॉन्फ़िगर किए गए HTML बचत विकल्पों का उपयोग करके दस्तावेज़ को HTML में परिवर्तित करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

यह कोड दस्तावेज़ को HTML में परिवर्तित करता है और इसे बेस 64 डेटा के रूप में निर्यात किए गए फ़ॉन्ट के साथ एक फ़ाइल में सहेजता है।

### .NET के लिए Aspose.Words का उपयोग करके बेस 64 के रूप में निर्यात फ़ॉन्ट्स के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 दस्तावेज़ निर्देशिका में सही पथ निर्दिष्ट करना सुनिश्चित करें`dataDir` चर।

अब आपने सीख लिया है कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को HTML के रूप में सहेजते समय बेस 64 फ़ॉन्ट कैसे निर्यात करें। इस ट्यूटोरियल में दिए गए चरण-दर-चरण मार्गदर्शिका का पालन करके, आप आसानी से फ़ॉन्ट को सुरक्षित रूप से निर्यात कर सकते हैं और अपने HTML दस्तावेज़ों में एम्बेड कर सकते हैं।