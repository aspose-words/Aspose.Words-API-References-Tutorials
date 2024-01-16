---
title: निर्यात संसाधन
linktitle: निर्यात संसाधन
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ HTML के रूप में सहेजते समय दस्तावेज़ संसाधनों को निर्यात करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-htmlsaveoptions/export-resources/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ दस्तावेज़ संसाधनों को निर्यात करने के लिए C# स्रोत कोड के बारे में बताएंगे। यह सुविधा आपको किसी दस्तावेज़ को HTML प्रारूप में सहेजते समय फ़ॉन्ट जैसे संसाधनों को बाहरी फ़ाइलों के रूप में निर्यात करने की अनुमति देती है।

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

अब हम दस्तावेज़ संसाधनों को निर्यात करने के लिए HTML सेव विकल्पों को कॉन्फ़िगर करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resources"
};
```

 यह कोड एक उदाहरण बनाता है`HtmlSaveOptions` और निम्नलिखित विकल्प सेट करता है:

- `CssStyleSheetType` इसके लिए सेट है`CssStyleSheetType.External`सीएसएस स्टाइल शीट को बाहरी फ़ाइल में निर्यात करने के लिए।
- `ExportFontResources` इसके लिए सेट है`true` फ़ॉन्ट संसाधनों को निर्यात करने के लिए.
- `ResourceFolder` गंतव्य निर्देशिका निर्दिष्ट करता है जहां संसाधन सहेजे जाएंगे।
- `ResourceFolderAlias` यूआरएल उपनाम निर्दिष्ट करता है जिसका उपयोग संसाधनों तक पहुंचने के लिए किया जाएगा।

## चरण 4: दस्तावेज़ को HTML में परिवर्तित करना और सहेजना

अंत में, हम पहले कॉन्फ़िगर किए गए HTML बचत विकल्पों का उपयोग करके दस्तावेज़ को HTML में परिवर्तित करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

यह कोड दस्तावेज़ को HTML में परिवर्तित करता है और निर्दिष्ट URL उपनाम का उपयोग करके संसाधनों को निर्दिष्ट निर्देशिका में सहेजता है।

### .NET के लिए Aspose.Words का उपयोग करके निर्यात संसाधनों के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resources"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 दस्तावेज़ निर्देशिका में सही पथ निर्दिष्ट करना सुनिश्चित करें`dataDir` चर।