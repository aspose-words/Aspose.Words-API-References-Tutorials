---
title: टेक्स्ट इनपुट फ़ॉर्म फ़ील्ड को टेक्स्ट के रूप में निर्यात करें
linktitle: टेक्स्ट इनपुट फ़ॉर्म फ़ील्ड को टेक्स्ट के रूप में निर्यात करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ टेक्स्ट इनपुट फॉर्म फ़ील्ड को सादे टेक्स्ट के रूप में निर्यात करने के लिए चरण दर चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ टेक्स्ट इनपुट फ़ॉर्म फ़ील्ड को सादे टेक्स्ट के रूप में निर्यात करने के लिए C# स्रोत कोड के माध्यम से मार्गदर्शन करेंगे। यह सुविधा आपको टेक्स्ट इनपुट फ़ॉर्म फ़ील्ड को HTML इनपुट तत्वों के रूप में निर्यात करने के बजाय पठनीय टेक्स्ट के रूप में निर्यात करने की अनुमति देती है।

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

अब हम टेक्स्ट इनपुट फ़ॉर्म फ़ील्ड को सादे टेक्स्ट के रूप में निर्यात करने के लिए HTML सेव विकल्पों को कॉन्फ़िगर करेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// निर्दिष्ट फ़ोल्डर मौजूद होना चाहिए और खाली होना चाहिए.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 यह कोड एक उदाहरण बनाता है`HtmlSaveOptions`और सेट करता है`ExportTextInputFormFieldAsText` विकल्प`true` टेक्स्ट इनपुट फॉर्म फ़ील्ड को सादे टेक्स्ट के रूप में निर्यात करने के लिए। इसके अलावा, यह उस फ़ोल्डर को निर्दिष्ट करता है जहाँ निकाली गई छवियाँ सहेजी जाएँगी।

## चरण 4: दस्तावेज़ को HTML में परिवर्तित करना और सहेजना

अंत में, हम पहले से कॉन्फ़िगर किए गए HTML सेविंग विकल्पों का उपयोग करके दस्तावेज़ को HTML में बदल देंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

यह कोड टेक्स्ट इनपुट फॉर्म फ़ील्ड को सादे टेक्स्ट के रूप में निर्यात करके दस्तावेज़ को HTML में परिवर्तित करता है, और निर्यातित HTML फ़ाइल को निर्दिष्ट निर्देशिका में सहेजता है।

### .NET के लिए Aspose.Words का उपयोग करके टेक्स्ट इनपुट फॉर्म फ़ील्ड को टेक्स्ट के रूप में निर्यात करने के लिए उदाहरण स्रोत कोड


```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// निर्दिष्ट फ़ोल्डर मौजूद होना चाहिए और खाली होना चाहिए.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// फ़ॉर्म फ़ील्ड को HTML इनपुट तत्वों के रूप में नहीं, बल्कि सादे पाठ के रूप में निर्यात करने का विकल्प सेट करें.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 दस्तावेज़ निर्देशिका में सही पथ निर्दिष्ट करना सुनिश्चित करें.`dataDir` चर।