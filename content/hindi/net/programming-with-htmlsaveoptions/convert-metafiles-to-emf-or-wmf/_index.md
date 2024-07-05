---
title: मेटाफ़ाइल्स को Emf या Wmf में बदलें
linktitle: मेटाफ़ाइल्स को Emf या Wmf में बदलें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ को HTML में परिवर्तित करते समय मेटाफ़ाइलों को EMF या WMF प्रारूपों में परिवर्तित करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ मेटाफ़ाइल को EMF या WMF फ़ॉर्मेट में बदलने के लिए C# सोर्स कोड के बारे में बताएँगे। यह सुविधा आपको दस्तावेज़ को HTML में बदलते समय मेटाफ़ाइल फ़ॉर्मेट में मौजूद छवियों को EMF या WMF जैसे ज़्यादा संगत फ़ॉर्मेट में बदलने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ में छवि सम्मिलित करना

इस चरण में, हम दस्तावेज़ में एक छवि डालेंगे जिसे परिवर्तित किया जाना है। HTML टैग का उपयोग करके डेटा स्रोत से एक छवि डालने के लिए निम्न कोड का उपयोग करें:

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

 यह कोड एक उदाहरण बनाता है`Document` और`DocumentBuilder` दस्तावेज़ बनाने के लिए। यह एक सम्मिलित करता है`<img>` टैग को एक बेस64 एनकोडेड छवि के साथ दस्तावेज़ में जोड़ें।

## चरण 3: HTML सेव विकल्प सेट करें

अब हम HTML सेव ऑप्शन सेट करेंगे, जिसमें इमेज के लिए इस्तेमाल किए जाने वाले मेटाफ़ाइल फ़ॉर्मेट भी शामिल है। निम्नलिखित कोड का उपयोग करें:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 यह कोड एक उदाहरण बनाता है`HtmlSaveOptions` और सेट`MetafileFormat` को`HtmlMetafileFormat.EmfOrWmf` यह निर्दिष्ट करने के लिए कि HTML में कनवर्ट करते समय मेटाफ़ाइलों को EMF या WMF प्रारूप में कनवर्ट किया जाना चाहिए।

## चरण 4: दस्तावेज़ को HTML में परिवर्तित करना और सहेजना

अंत में हम पहले से परिभाषित HTML सहेजें विकल्पों का उपयोग करके दस्तावेज़ को HTML में बदल देंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

यह कोड दस्तावेज़ को HTML में परिवर्तित करता है और इसे सेट किए गए सेव विकल्पों के आधार पर EMF या WMF प्रारूप में परिवर्तित मेटाफाइल्स के साथ एक फाइल में सेव करता है।

### .NET के लिए Aspose.Words का उपयोग करके मेटाफ़ाइल्स को Emf या Wmf में परिवर्तित करने के लिए उदाहरण स्रोत कोड

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

 दस्तावेज़ निर्देशिका में सही पथ निर्दिष्ट करना सुनिश्चित करें.`dataDir` चर।

अब आप सीख चुके हैं कि Aspose.Words for .NET का उपयोग करके दस्तावेज़ को HTML में परिवर्तित करते समय मेटाफ़ाइल को EMF या WMF फ़ॉर्मेट में कैसे परिवर्तित किया जाए। इस ट्यूटोरियल में दिए गए चरण-दर-चरण गाइड का पालन करके, आप अपने परिवर्तित HTML दस्तावेज़ों में मेटाफ़ाइल को आसानी से प्रबंधित कर सकते हैं।