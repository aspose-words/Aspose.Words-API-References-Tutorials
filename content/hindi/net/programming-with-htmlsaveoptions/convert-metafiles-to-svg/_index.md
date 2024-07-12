---
title: मेटाफ़ाइल्स को Svg में बदलें
linktitle: मेटाफ़ाइल्स को Svg में बदलें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ को HTML में परिवर्तित करते समय मेटाफ़ाइलों को SVG प्रारूप में परिवर्तित करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ मेटाफ़ाइल्स को SVG फ़ॉर्मेट में बदलने के लिए C# सोर्स कोड के बारे में बताएँगे। यह सुविधा आपको दस्तावेज़ को HTML में बदलते समय मेटाफ़ाइल्स को SVG फ़ॉर्मेट में बदलने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ में SVG छवि सम्मिलित करना

इस चरण में, हम कन्वर्ट किए जाने वाले दस्तावेज़ में एक SVG छवि डालेंगे। HTML टैग का उपयोग करके SVG छवि डालने के लिए निम्न कोड का उपयोग करें:

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

 यह कोड एक उदाहरण बनाता है`Document`और`DocumentBuilder` दस्तावेज़ बनाने के लिए। यह एक सम्मिलित करता है`<svg>` टैग युक्त एक`<polygon>` एसवीजी छवि के आकार और शैली को परिभाषित करने के लिए विशेषताओं वाला तत्व।

## चरण 3: HTML सेव विकल्प सेट करें

अब हम HTML सेव ऑप्शन सेट करेंगे, जिसमें यह निर्दिष्ट किया जाएगा कि मेटाफाइल्स को SVG फॉर्मेट में बदला जाना चाहिए। निम्नलिखित कोड का उपयोग करें:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 यह कोड एक उदाहरण बनाता है`HtmlSaveOptions` और सेट`MetafileFormat` को`HtmlMetafileFormat.Svg` यह निर्दिष्ट करने के लिए कि HTML में कनवर्ट करते समय मेटाफ़ाइलों को SVG प्रारूप में परिवर्तित किया जाना चाहिए।

## चरण 4: दस्तावेज़ को HTML में परिवर्तित करना और सहेजना

अंत में, हम पहले परिभाषित HTML सेव विकल्पों का उपयोग करके दस्तावेज़ को HTML में बदल देंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

यह कोड दस्तावेज़ को HTML में परिवर्तित करता है और इसे एक फाइल में सहेजता है, जिसमें मेटाफाइल्स को SVG में परिवर्तित किया जाता है।

### .NET के लिए Aspose.Words का उपयोग करके मेटाफ़ाइल्स को Svg में परिवर्तित करने के लिए उदाहरण स्रोत कोड

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
