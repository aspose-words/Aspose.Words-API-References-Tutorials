---
title: छवियाँ फ़ोल्डर सेट करें
linktitle: छवियाँ फ़ोल्डर सेट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि .NET के लिए Aspose.Words के साथ मार्कडाउन में निर्यात करते समय इमेज फ़ोल्डर कैसे सेट करें। बेहतर संगठन और एकीकरण के लिए छवियों के स्थान को अनुकूलित करें।
type: docs
weight: 10
url: /hi/net/programming-with-markdownsaveoptions/set-images-folder/
---

यहां निम्नलिखित C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है जो .NET के लिए Aspose.Words लाइब्रेरी का उपयोग करके मार्कडाउन निर्यात विकल्पों के लिए छवि फ़ोल्डर सेट करने में मदद करती है। सुनिश्चित करें कि आपने इस कोड का उपयोग करने से पहले Aspose.Words लाइब्रेरी को अपने प्रोजेक्ट में शामिल कर लिया है।

## चरण 1: दस्तावेज़ निर्देशिका पथ सेट करें

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

अपने दस्तावेज़ निर्देशिका के लिए सही पथ निर्दिष्ट करना सुनिश्चित करें जहां छवियों वाला दस्तावेज़ स्थित है।

## चरण 2: छवियों वाले दस्तावेज़ को लोड करें

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

हम निर्दिष्ट दस्तावेज़ को लोड करते हैं जिसमें वे छवियां शामिल हैं जिन्हें हम मार्कडाउन विकल्पों के साथ निर्यात करना चाहते हैं।

## चरण 3: मार्कडाउन निर्यात विकल्पों के लिए छवियाँ फ़ोल्डर सेट करें

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 हम इसका एक उदाहरण बनाते हैं`MarkdownSaveOptions` और का उपयोग करके छवि फ़ोल्डर के लिए पथ सेट करें`ImagesFolder` संपत्ति। उस फ़ोल्डर के लिए सही पथ निर्दिष्ट करना सुनिश्चित करें जहां आप निर्यात की गई छवियों को सहेजना चाहते हैं।

## चरण 4: दस्तावेज़ को मार्कडाउन निर्यात विकल्पों के साथ सहेजें

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

हम निर्दिष्ट मार्कडाउन निर्यात विकल्पों का उपयोग करके दस्तावेज़ को मेमोरी स्ट्रीम में सहेजते हैं। फिर आप अन्य ऑपरेशन करने के लिए प्रवाह का उपयोग कर सकते हैं, जैसे मार्कडाउन सामग्री को फ़ाइल में सहेजना।

### .NET के लिए Aspose.Words के साथ MarkdownSaveOptions के लिए इमेज फ़ोल्डर सेट करने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

यह स्रोत कोड दर्शाता है कि किसी दस्तावेज़ को कैसे लोड किया जाए जिसमें छवियां हैं और फिर मार्कडाउन निर्यात विकल्पों के लिए छवि फ़ोल्डर सेट करें। निर्दिष्ट विकल्पों का उपयोग करके, दस्तावेज़ को मेमोरी स्ट्रीम में सहेजा जाता है। यह आपको मार्कडाउन सामग्री निर्यात करते समय छवि फ़ोल्डर के स्थान को अनुकूलित करने की अनुमति देता है।