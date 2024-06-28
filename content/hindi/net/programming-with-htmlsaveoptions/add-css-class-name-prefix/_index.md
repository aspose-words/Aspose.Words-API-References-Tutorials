---
title: सीएसएस क्लास नाम उपसर्ग जोड़ें
linktitle: सीएसएस क्लास नाम उपसर्ग जोड़ें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: किसी दस्तावेज़ को .NET के लिए Aspose.Words के साथ HTML में कनवर्ट करते समय CSS क्लास नाम उपसर्ग जोड़ने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ CSS क्लास नाम उपसर्ग जोड़ने के लिए C# स्रोत कोड के बारे में बताएंगे। यह सुविधा आपको किसी दस्तावेज़ को HTML में कनवर्ट करते समय जेनरेट किए गए CSS क्लास नामों में एक कस्टम उपसर्ग जोड़ने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएं। सुनिश्चित करें कि आपके प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम उस Word दस्तावेज़ को लोड करेंगे जिसे हम HTML में कनवर्ट करना चाहते हैं। दस्तावेज़ लोड करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आपका दस्तावेज़ स्थित है।

## चरण 3: HTML सेव विकल्प सेट करें

अब सीएसएस स्टाइलशीट प्रकार और सीएसएस क्लास नाम उपसर्ग सहित HTML सेव विकल्प सेट करें। निम्नलिखित कोड का प्रयोग करें:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 यह कोड एक उदाहरण बनाता है`HtmlSaveOptions` और सेट`CssStyleSheetType` को`CssStyleSheetType.External`एक बाहरी सीएसएस स्टाइल शीट तैयार करने के लिए, और`CssClassNamePrefix` को`"pfx_"` उपसर्ग करना`"pfx_"` सीएसएस कक्षाओं को नाम देने के लिए।

## चरण 4: दस्तावेज़ को HTML में परिवर्तित करना और सहेजना

अंत में, हम पहले परिभाषित HTML सेव विकल्पों का उपयोग करके दस्तावेज़ को HTML में परिवर्तित करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

यह कोड दस्तावेज़ को HTML में परिवर्तित करता है और इसे CSS वर्ग नाम उपसर्ग के साथ एक फ़ाइल में सहेजता है।

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

 में सही दस्तावेज़ पथ निर्दिष्ट करना सुनिश्चित करें`dataDir` चर।

अब आपने सीख लिया है कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को HTML में कनवर्ट करते समय CSS क्लास नाम उपसर्ग कैसे जोड़ा जाता है। इस ट्यूटोरियल में दिए गए चरण-दर-चरण मार्गदर्शिका चरण का पालन करके, आप अपने परिवर्तित HTML दस्तावेज़ों में सीएसएस वर्ग नामों को अनुकूलित कर सकते हैं।