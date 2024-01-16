---
title: क्लीनअप डुप्लिकेट शैली
linktitle: क्लीनअप डुप्लिकेट शैली
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में डुप्लिकेट शैलियों को साफ़ करने के लिए चरण दर चरण मार्गदर्शिका। पूर्ण स्रोत कोड शामिल है.
type: docs
weight: 10
url: /hi/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ डुप्लिकेट शैलियों को साफ़ करने के लिए चरण दर चरण C# स्रोत कोड के बारे में बताएंगे। यह सुविधा किसी दस्तावेज़ से डुप्लिकेट शैलियों को हटाने में मदद करती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएं। सुनिश्चित करें कि आपके प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ लोड करना

इस चरण में, हम उस Word दस्तावेज़ को लोड करेंगे जिसे हम साफ़ करना चाहते हैं। दस्तावेज़ लोड करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आपका दस्तावेज़ स्थित है।

## चरण 3: सफाई से पहले शैलियों की गणना करें

सफ़ाई के साथ आगे बढ़ने से पहले, हम दस्तावेज़ में मौजूद शैलियों की संख्या की गणना करेंगे। शैली गणना प्रदर्शित करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
Console.WriteLine(doc.Styles.Count);
```

यह कथन दस्तावेज़ में मौजूद शैलियों की संख्या प्रदर्शित करता है।

## चरण 4: डुप्लिकेट शैलियों को साफ़ करें

आइए अब दस्तावेज़ से डुप्लिकेट शैलियों को साफ़ करें। सफ़ाई करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 यह कोड निर्दिष्ट विकल्पों का उपयोग करके दस्तावेज़ से डुप्लिकेट शैलियों को साफ़ करता है। इस उदाहरण में, हमने इसे सक्षम किया है`DuplicateStyle` डुप्लिकेट शैलियों को साफ़ करने का विकल्प।

## चरण 5: सफाई के बाद शैलियों की गणना करें

सफाई करने के बाद, हम यह जांचने के लिए शैलियों की संख्या फिर से गिनेंगे कि क्या यह कम हुई है। नई शैलियों की संख्या प्रदर्शित करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

यह कथन सफ़ाई के बाद बची हुई शैलियों की संख्या प्रदर्शित करता है।

### .NET के लिए Aspose.Words का उपयोग करके क्लीनअप डुप्लिकेट स्टाइल के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// क्लीनअप से पहले शैलियों की गिनती।
	Console.WriteLine(doc.Styles.Count);

	// दस्तावेज़ से डुप्लिकेट शैलियों को साफ़ करता है।
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	//सफ़ाई के बाद शैलियों की संख्या कम हो गई थी।
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```