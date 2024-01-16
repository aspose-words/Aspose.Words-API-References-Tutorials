---
title: मेटाफ़ाइल्स को ईएमएफ या डब्लूएमएफ में कनवर्ट करें
linktitle: मेटाफ़ाइल्स को ईएमएफ या डब्लूएमएफ में कनवर्ट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: किसी दस्तावेज़ को .NET के लिए Aspose.Words के साथ HTML में परिवर्तित करते समय मेटाफ़ाइलों को EMF या WMF प्रारूपों में परिवर्तित करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ मेटाफ़ाइल्स को EMF या WMF प्रारूप में परिवर्तित करने के लिए C# स्रोत कोड के बारे में बताएंगे। किसी दस्तावेज़ को HTML में परिवर्तित करते समय यह सुविधा आपको मेटाफ़ाइल प्रारूप में छवियों को ईएमएफ या डब्लूएमएफ जैसे अधिक संगत प्रारूपों में परिवर्तित करने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएं। सुनिश्चित करें कि आपके प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ में एक छवि सम्मिलित करना

इस चरण में, हम परिवर्तित किए जाने वाले दस्तावेज़ में एक छवि सम्मिलित करेंगे। HTML टैग का उपयोग करके डेटा स्रोत से एक छवि सम्मिलित करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 यह कोड एक उदाहरण बनाता है`Document` और`DocumentBuilder` दस्तावेज़ बनाने के लिए. यह एक सम्मिलित करता है`<img>` दस्तावेज़ में बेस64 एन्कोडेड छवि के साथ टैग करें।

## चरण 3: HTML सेव विकल्प सेट करें

अब हम छवियों के लिए उपयोग करने के लिए मेटाफ़ाइल प्रारूप सहित HTML सेव विकल्प सेट करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 यह कोड एक उदाहरण बनाता है`HtmlSaveOptions` और सेट`MetafileFormat` को`HtmlMetafileFormat.EmfOrWmf` यह निर्दिष्ट करने के लिए कि मेटाफ़ाइल्स को HTML में परिवर्तित करते समय EMF या WMF प्रारूप में परिवर्तित किया जाना चाहिए।

## चरण 4: दस्तावेज़ को HTML में परिवर्तित करना और सहेजना

अंत में हम पहले से परिभाषित सेव HTML विकल्पों का उपयोग करके दस्तावेज़ को HTML में परिवर्तित करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

यह कोड दस्तावेज़ को HTML में परिवर्तित करता है और सेव विकल्प सेट के आधार पर इसे EMF या WMF प्रारूप में परिवर्तित मेटाफ़ाइल्स वाली फ़ाइल में सहेजता है।

### .NET के लिए Aspose.Words का उपयोग करके मेटाफ़ाइल्स को ईएमएफ या डब्लूएमएफ में कनवर्ट करने के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 दस्तावेज़ निर्देशिका में सही पथ निर्दिष्ट करना सुनिश्चित करें`dataDir` चर।

अब आपने सीख लिया है कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को HTML में परिवर्तित करते समय मेटाफ़ाइल्स को EMF या WMF प्रारूप में कैसे परिवर्तित किया जाए। इस ट्यूटोरियल में दिए गए चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने परिवर्तित HTML दस्तावेज़ों में मेटाफ़ाइल्स को आसानी से प्रबंधित कर सकते हैं।