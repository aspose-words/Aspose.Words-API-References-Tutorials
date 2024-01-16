---
title: रूसी को डिफ़ॉल्ट संपादन भाषा के रूप में सेट करें
linktitle: रूसी को डिफ़ॉल्ट संपादन भाषा के रूप में सेट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ की डिफ़ॉल्ट संपादन भाषा के रूप में रूसी को सेट करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ रूसी को डिफ़ॉल्ट संपादन भाषा के रूप में सेट करने के लिए C# स्रोत कोड के बारे में बताएंगे। यह सुविधा आपको दस्तावेज़ लोड करते समय डिफ़ॉल्ट भाषा सेट करने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएं। सुनिश्चित करें कि आपके प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम Word दस्तावेज़ को लोड करेंगे जिसके लिए हम रूसी को डिफ़ॉल्ट संपादन भाषा के रूप में सेट करना चाहते हैं। दस्तावेज़ लोड करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आपका दस्तावेज़ स्थित है।

## चरण 3: डिफ़ॉल्ट भाषा की जाँच करना

दस्तावेज़ अपलोड करने के बाद, हम जाँचेंगे कि क्या डिफ़ॉल्ट भाषा सही ढंग से रूसी पर सेट की गई है। डिफ़ॉल्ट भाषा आईडी प्राप्त करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

कोड जाँचता है कि भाषा आईडी रूसी से मेल खाती है या नहीं। परिणाम के अनुसार, यह संबंधित संदेश प्रदर्शित करता है।

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

 में सही दस्तावेज़ पथ निर्दिष्ट करना सुनिश्चित करें`dataDir` चर।

अब आपने सीख लिया है कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ के लिए रूसी को डिफ़ॉल्ट संपादन भाषा के रूप में कैसे सेट किया जाए। चरण मार्गदर्शिका का पालन करके