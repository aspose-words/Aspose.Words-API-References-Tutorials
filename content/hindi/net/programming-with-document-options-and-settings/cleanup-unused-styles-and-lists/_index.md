---
title: अप्रयुक्त शैलियों और सूचियों को साफ़ करें
linktitle: अप्रयुक्त शैलियों और सूचियों को साफ़ करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ में अप्रयुक्त शैलियों और सूचियों को साफ़ करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ अप्रयुक्त शैलियों और सूचियों को साफ़ करने के लिए C# स्रोत कोड के बारे में बताएंगे। यह सुविधा आपको उन शैलियों और सूचियों को हटाने की अनुमति देती है जिनका उपयोग किसी दस्तावेज़ में नहीं किया जाता है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएं। सुनिश्चित करें कि आपके प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम Word दस्तावेज़ को लोड करेंगे जिसमें अप्रयुक्त शैलियाँ और सूचियाँ होंगी जिन्हें हम साफ़ करना चाहते हैं। दस्तावेज़ लोड करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आपका दस्तावेज़ स्थित है।

## चरण 3: सफाई से पहले शैलियों और सूचियों की गणना करें

सफ़ाई से पहले, हम दस्तावेज़ में मौजूद शैलियों और सूचियों की संख्या की गणना करेंगे। काउंटर प्रदर्शित करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

ये निर्देश सफाई से पहले दस्तावेज़ में मौजूद शैलियों और सूचियों की संख्या दिखाते हैं।

## चरण 4: अप्रयुक्त शैलियों और सूचियों को साफ़ करें

आइए अब दस्तावेज़ से अप्रयुक्त शैलियों और सूचियों को साफ़ करें। सफ़ाई करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 यह कोड निर्दिष्ट विकल्पों का उपयोग करके दस्तावेज़ से अप्रयुक्त शैलियों और सूचियों को साफ़ करता है। इस उदाहरण में, हमने इसे सक्षम किया है`UnusedStyles` अप्रयुक्त शैलियों को हटाने और अक्षम करने का विकल्प`UnusedLists` सूचियाँ उपयोग न होने पर भी उन्हें रखने का विकल्प।

## चरण 5: सफाई के बाद शैलियों और सूचियों की गणना करें

सफ़ाई करने के बाद, हम यह जाँचने के लिए शैलियों और सूचियों की फिर से गिनती करेंगे कि क्या वे ढह गई हैं। नए काउंटर प्रदर्शित करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

ये निर्देश सफाई के बाद बची हुई शैलियों और सूचियों की संख्या दर्शाते हैं।

### .NET के लिए Aspose.Words का उपयोग करके अप्रयुक्त शैलियों और सूचियों को साफ़ करने के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// अंतर्निहित शैलियों के साथ, दस्तावेज़ में अब आठ शैलियाँ हैं।
	// एक कस्टम शैली को "प्रयुक्त" के रूप में चिह्नित किया जाता है जबकि दस्तावेज़ में कोई पाठ मौजूद होता है
	// उस शैली में स्वरूपित. इसका मतलब यह है कि हमारे द्वारा जोड़ी गई 4 शैलियाँ वर्तमान में अप्रयुक्त हैं।
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//दिए गए CleanupOptions के आधार पर दस्तावेज़ से अप्रयुक्त शैलियों और सूचियों को साफ़ करता है।
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 में सही दस्तावेज़ पथ निर्दिष्ट करना सुनिश्चित करें`dataDir` चर।

अब आपने सीख लिया है कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ से अप्रयुक्त शैलियों और सूचियों को कैसे साफ़ किया जाए। इस ट्यूटोरियल में दिए गए चरण-दर-चरण मार्गदर्शिका का पालन करके, आप इस सुविधा को अपने दस्तावेज़ों पर आसानी से लागू कर सकते हैं।

