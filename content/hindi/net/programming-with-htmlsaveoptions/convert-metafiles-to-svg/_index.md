---
title: मेटाफ़ाइल्स को Svg में कनवर्ट करें
linktitle: मेटाफ़ाइल्स को Svg में कनवर्ट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: किसी दस्तावेज़ को .NET के लिए Aspose.Words के साथ HTML में परिवर्तित करते समय मेटाफ़ाइल्स को SVG प्रारूप में परिवर्तित करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ मेटाफ़ाइल्स को SVG प्रारूप में परिवर्तित करने के लिए C# स्रोत कोड के बारे में बताएंगे। किसी दस्तावेज़ को HTML में परिवर्तित करते समय यह सुविधा आपको मेटाफ़ाइल्स को SVG प्रारूप में परिवर्तित करने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएं। सुनिश्चित करें कि आपके प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ में एक एसवीजी छवि सम्मिलित करना

इस चरण में, हम परिवर्तित किए जाने वाले दस्तावेज़ में एक एसवीजी छवि डालेंगे। HTML टैग का उपयोग करके SVG छवि सम्मिलित करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 यह कोड एक उदाहरण बनाता है`Document` और`DocumentBuilder` दस्तावेज़ बनाने के लिए. यह एक सम्मिलित करता है`<svg>` टैग जिसमें a`<polygon>` एसवीजी छवि के आकार और शैली को परिभाषित करने के लिए विशेषताओं वाला तत्व।

## चरण 3: HTML सेव विकल्प सेट करें

अब हम HTML सेव विकल्प सेट करेंगे, यह निर्दिष्ट करते हुए कि मेटाफ़ाइल्स को एसवीजी प्रारूप में परिवर्तित किया जाना चाहिए। निम्नलिखित कोड का प्रयोग करें:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 यह कोड एक उदाहरण बनाता है`HtmlSaveOptions` और सेट`MetafileFormat` को`HtmlMetafileFormat.Svg` यह निर्दिष्ट करने के लिए कि HTML में परिवर्तित करते समय मेटाफ़ाइल्स को SVG प्रारूप में परिवर्तित किया जाना चाहिए।

## चरण 4: दस्तावेज़ को HTML में परिवर्तित करना और सहेजना

अंत में, हम पहले परिभाषित HTML सेव विकल्पों का उपयोग करके दस्तावेज़ को HTML में परिवर्तित करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

यह कोड दस्तावेज़ को HTML में परिवर्तित करता है और इसे SVG में परिवर्तित मेटाफ़ाइल वाली फ़ाइल में सहेजता है।

### .NET के लिए Aspose.Words का उपयोग करके मेटाफ़ाइल्स को Svg में कनवर्ट करने के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
