---
title: डुप्लिकेट स्टाइल साफ़ करें
linktitle: डुप्लिकेट स्टाइल साफ़ करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में डुप्लिकेट शैलियों को साफ़ करने के लिए चरण-दर-चरण मार्गदर्शिका। पूर्ण स्रोत कोड शामिल है।
type: docs
weight: 10
url: /hi/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ डुप्लिकेट शैलियों को साफ करने के लिए चरण दर चरण C# स्रोत कोड के माध्यम से चलेंगे। यह सुविधा किसी दस्तावेज़ से डुप्लिकेट शैलियों को हटाने में मदद करती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम उस Word दस्तावेज़ को लोड करेंगे जिसे हम साफ़ करना चाहते हैं। दस्तावेज़ को लोड करने के लिए निम्न कोड का उपयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहाँ आपका दस्तावेज़ स्थित है।

## चरण 3: सफाई से पहले शैलियों की गणना करें

सफाई के साथ आगे बढ़ने से पहले, हम दस्तावेज़ में मौजूद शैलियों की संख्या की गणना करेंगे। शैलियों की संख्या प्रदर्शित करने के लिए निम्न कोड का उपयोग करें:

```csharp
Console.WriteLine(doc.Styles.Count);
```

यह कथन दस्तावेज़ में मौजूद शैलियों की संख्या प्रदर्शित करता है।

## चरण 4: डुप्लिकेट शैलियों को साफ़ करें

अब आइए दस्तावेज़ से डुप्लिकेट शैलियों को साफ़ करें। सफ़ाई करने के लिए निम्न कोड का उपयोग करें:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 यह कोड निर्दिष्ट विकल्पों का उपयोग करके दस्तावेज़ से डुप्लिकेट शैलियों को साफ़ करता है। इस उदाहरण में, हमने सक्षम किया है`DuplicateStyle` डुप्लिकेट शैलियों को साफ़ करने का विकल्प.

## चरण 5: सफाई के बाद स्टाइल की गिनती करें

सफाई करने के बाद, हम फिर से स्टाइल की संख्या गिनेंगे ताकि यह पता चल सके कि यह कम हुई है या नहीं। नई स्टाइल की संख्या प्रदर्शित करने के लिए निम्न कोड का उपयोग करें:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

यह कथन सफाई के बाद शेष बची शैलियों की संख्या प्रदर्शित करता है।

### .NET के लिए Aspose.Words का उपयोग करके डुप्लिकेट स्टाइल को साफ़ करने के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// सफाई से पहले शैलियों की गिनती.
	Console.WriteLine(doc.Styles.Count);

	// दस्तावेज़ से डुप्लिकेट शैलियों को साफ़ करता है.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	// क्लीनअप के बाद शैलियों की संख्या कम हो गई।
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```