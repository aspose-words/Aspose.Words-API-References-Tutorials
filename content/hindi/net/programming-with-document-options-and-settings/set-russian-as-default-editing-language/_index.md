---
title: रूसी को डिफ़ॉल्ट संपादन भाषा के रूप में सेट करें
linktitle: रूसी को डिफ़ॉल्ट संपादन भाषा के रूप में सेट करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ किसी दस्तावेज़ की डिफ़ॉल्ट संपादन भाषा के रूप में रूसी भाषा को सेट करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ रूसी को डिफ़ॉल्ट संपादन भाषा के रूप में सेट करने के लिए C# स्रोत कोड के माध्यम से मार्गदर्शन करेंगे। यह सुविधा आपको दस्तावेज़ लोड करते समय डिफ़ॉल्ट भाषा सेट करने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम उस Word दस्तावेज़ को लोड करेंगे जिसके लिए हम रूसी को डिफ़ॉल्ट संपादन भाषा के रूप में सेट करना चाहते हैं। दस्तावेज़ को लोड करने के लिए निम्न कोड का उपयोग करें:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहाँ आपका दस्तावेज़ स्थित है।

## चरण 3: डिफ़ॉल्ट भाषा की जाँच करना

दस्तावेज़ अपलोड करने के बाद, हम जाँच करेंगे कि डिफ़ॉल्ट भाषा रूसी पर सही ढंग से सेट की गई है या नहीं। डिफ़ॉल्ट भाषा आईडी प्राप्त करने के लिए निम्न कोड का उपयोग करें:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

कोड जाँचता है कि भाषा आईडी रूसी से मेल खाती है या नहीं। परिणाम के अनुसार, यह एक संगत संदेश प्रदर्शित करता है।

### .NET के लिए Aspose.Words का उपयोग करके रूसी को डिफ़ॉल्ट संपादन भाषा के रूप में सेट करने के लिए उदाहरण स्रोत कोड

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 सुनिश्चित करें कि आपने सही दस्तावेज़ पथ निर्दिष्ट किया है.`dataDir` चर।

अब आप सीख चुके हैं कि Aspose.Words for .NET का उपयोग करके किसी दस्तावेज़ के लिए डिफ़ॉल्ट संपादन भाषा के रूप में रूसी भाषा कैसे सेट करें। चरण-दर-चरण मार्गदर्शिका का पालन करके