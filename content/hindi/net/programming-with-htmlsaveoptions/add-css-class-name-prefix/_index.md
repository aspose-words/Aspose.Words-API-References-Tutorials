---
title: सीएसएस क्लास नाम उपसर्ग जोड़ें
linktitle: सीएसएस क्लास नाम उपसर्ग जोड़ें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ किसी दस्तावेज़ को HTML में परिवर्तित करते समय CSS वर्ग नाम उपसर्ग जोड़ने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ CSS क्लास नाम उपसर्ग जोड़ने के लिए C# स्रोत कोड के माध्यम से चलेंगे। यह सुविधा आपको दस्तावेज़ को HTML में परिवर्तित करते समय जेनरेट किए गए CSS क्लास नामों में कस्टम उपसर्ग जोड़ने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम उस Word दस्तावेज़ को लोड करेंगे जिसे हम HTML में बदलना चाहते हैं। दस्तावेज़ को लोड करने के लिए निम्न कोड का उपयोग करें:

```csharp
//दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहाँ आपका दस्तावेज़ स्थित है।

## चरण 3: HTML सेव विकल्प सेट करें

अब हम HTML सेव ऑप्शन सेट करते हैं, जिसमें CSS स्टाइलशीट टाइप और CSS क्लास नाम प्रीफ़िक्स शामिल है। निम्नलिखित कोड का उपयोग करें:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 यह कोड एक उदाहरण बनाता है`HtmlSaveOptions` और सेट`CssStyleSheetType` को`CssStyleSheetType.External` एक बाहरी CSS स्टाइल शीट उत्पन्न करने के लिए, और`CssClassNamePrefix` को`"pfx_"` उपसर्ग करना`"pfx_"` सीएसएस वर्ग के नाम.

## चरण 4: दस्तावेज़ को HTML में परिवर्तित करना और सहेजना

अंत में, हम पहले परिभाषित HTML सेव विकल्पों का उपयोग करके दस्तावेज़ को HTML में बदल देंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

यह कोड दस्तावेज़ को HTML में परिवर्तित करता है और उसे CSS वर्ग नाम उपसर्ग के साथ एक फ़ाइल में सहेजता है।

### .NET के लिए Aspose.Words का उपयोग करके Css क्लास नाम उपसर्ग जोड़ने के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 सुनिश्चित करें कि आपने सही दस्तावेज़ पथ निर्दिष्ट किया है.`dataDir` चर।

अब आप सीख चुके हैं कि Aspose.Words for .NET का उपयोग करके किसी दस्तावेज़ को HTML में परिवर्तित करते समय CSS क्लास नाम उपसर्ग कैसे जोड़ें। इस ट्यूटोरियल में दिए गए चरण-दर-चरण मार्गदर्शिका चरण का पालन करके, आप अपने परिवर्तित HTML दस्तावेज़ों में CSS क्लास नामों को कस्टमाइज़ कर सकते हैं।