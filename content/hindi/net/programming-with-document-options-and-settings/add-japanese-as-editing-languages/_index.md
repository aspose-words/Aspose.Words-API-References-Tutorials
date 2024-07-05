---
title: संपादन भाषा के रूप में जापानी जोड़ें
linktitle: संपादन भाषा के रूप में जापानी जोड़ें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ जापानी को एक संपादन भाषा के रूप में जोड़ने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

इस ट्यूटोरियल में, हम आपको Aspose.Words for .NET के साथ जापानी को एक संपादन भाषा के रूप में जोड़ने की कार्यक्षमता को समझने और लागू करने के लिए चरण दर चरण मार्गदर्शन करेंगे। यह सुविधा आपको दस्तावेज़ लोड करते समय भाषा प्राथमिकताएँ सेट करने और जापानी को एक संपादन भाषा के रूप में जोड़ने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम वह Word दस्तावेज़ लोड करेंगे जिसमें डिफ़ॉल्ट संपादन भाषा नहीं है और जिसमें हम जापानी जोड़ना चाहते हैं। दस्तावेज़ लोड करने के लिए निम्न कोड का उपयोग करें:

```csharp
LoadOptions loadOptions = new LoadOptions();

// दस्तावेज़ लोड करते समय उपयोग की जाने वाली भाषा प्राथमिकताएँ सेट करें.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## चरण 3: डिफ़ॉल्ट भाषा की जाँच करना

दस्तावेज़ लोड करने के बाद, हम जाँचेंगे कि डिफ़ॉल्ट संपादन भाषा जापानी में सही ढंग से सेट की गई है या नहीं। सुदूर पूर्वी भाषा आईडी प्राप्त करने के लिए निम्न कोड का उपयोग करें:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

कोड यह जाँचता है कि सुदूर पूर्वी भाषा की आईडी जापानी से मेल खाती है या नहीं। परिणाम के अनुसार, यह एक संगत संदेश प्रदर्शित करता है।

### .NET के लिए Aspose.Words का उपयोग करके जापानी को संपादन भाषाओं के रूप में जोड़ने के लिए उदाहरण स्रोत कोड

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// दस्तावेज़ लोड होने पर उपयोग की जाने वाली भाषा प्राथमिकताएँ सेट करें.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

