---
title: व्याकरणिक और वर्तनी संबंधी त्रुटियाँ दिखाएँ
linktitle: व्याकरणिक और वर्तनी संबंधी त्रुटियाँ दिखाएँ
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ में व्याकरणिक और वर्तनी त्रुटियों के प्रदर्शन को सक्षम करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ व्याकरणिक और वर्तनी त्रुटियों के प्रदर्शन को सक्षम करने के लिए C# स्रोत कोड के बारे में बताएंगे। यह सुविधा आपको दस्तावेज़ में व्याकरणिक और वर्तनी संबंधी त्रुटियों को देखने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएं। सुनिश्चित करें कि आपके प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम Word दस्तावेज़ को लोड करेंगे जिसके लिए हम व्याकरणिक और वर्तनी संबंधी त्रुटियाँ प्रदर्शित करना चाहते हैं। दस्तावेज़ लोड करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आपका दस्तावेज़ स्थित है।

## चरण 3: त्रुटि प्रदर्शन सक्षम करें

अब हम दस्तावेज़ में व्याकरणिक और वर्तनी संबंधी त्रुटियों को प्रदर्शित करने में सक्षम करेंगे। त्रुटि प्रदर्शन सक्षम करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

यह कोड व्याकरण संबंधी त्रुटियों को प्रदर्शित करने में सक्षम बनाता है (`ShowGrammaticalErrors`) और वर्तनी संबंधी त्रुटियाँ (`ShowSpellingErrors`) दस्तावेज़ में.

### .NET के लिए Aspose.Words का उपयोग करके व्याकरणिक और वर्तनी संबंधी त्रुटियाँ दिखाने के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 में सही दस्तावेज़ पथ निर्दिष्ट करना सुनिश्चित करें`dataDir` चर।

अब आपने सीख लिया है कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में व्याकरणिक और वर्तनी त्रुटियों के प्रदर्शन को कैसे सक्षम किया जाए। इस ट्यूटोरियल में दिए गए चरण-दर-चरण मार्गदर्शिका का पालन करके, आप इस सुविधा को अपने दस्तावेज़ों में आसानी से सक्षम कर सकते हैं।