---
title: पीडीएफ फाइल में टिप्पणियाँ हटाएँ
linktitle: पीडीएफ फाइल में टिप्पणियाँ हटाएँ
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ PDF फ़ाइल में टिप्पणियाँ निकालें।
type: docs
weight: 10
url: /hi/net/working-with-revisions/remove-comments-in-pdf/
---

इस चरण-दर-चरण मार्गदर्शिका में, हम आपको बताएंगे कि .NET के लिए Aspose.Words का उपयोग करके PDF फ़ाइल में टिप्पणियाँ कैसे हटाएँ। हम आपको पूरा स्रोत कोड प्रदान करेंगे और आपको दिखाएंगे कि मार्कडाउन आउटपुट को कैसे प्रारूपित किया जाए।

## चरण 1: दस्तावेज़ लोड करना

पहला चरण टिप्पणियों वाले दस्तावेज़ को लोड करना है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## चरण 2: पीडीएफ में टिप्पणियाँ छिपाएँ

हम पीडीएफ बनाते समय टिप्पणियों को छिपाने के लिए लेआउट विकल्प को कॉन्फ़िगर करेंगे।

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## चरण 3: दस्तावेज़ को PDF के रूप में सहेजें

अंत में, हम टिप्पणियाँ हटाकर दस्तावेज़ को पीडीएफ प्रारूप में सहेज लेंगे।

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## मार्कडाउन आउटपुट प्रारूप

पठनीयता में सुधार के लिए आउटपुट को मार्कडाउन में फ़ॉर्मेट किया जा सकता है। उदाहरण के लिए:

```markdown
- Comments are hidden in the generated PDF.
```

### .NET के लिए Aspose.Words का उपयोग करके PDF में टिप्पणियां हटाने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके PDF फ़ाइल में टिप्पणियाँ हटाने के लिए पूरा स्रोत कोड यहां दिया गया है:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// पीडीएफ में टिप्पणियाँ छिपाएँ।
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि Aspose.Words for .NET का उपयोग करके PDF फ़ाइल से टिप्पणियाँ कैसे हटाएँ। उचित लेआउट विकल्पों का उपयोग करके, हम PDF बनाते समय टिप्पणियाँ छिपाने में सक्षम थे। Aspose.Words for .NET Word फ़ाइलों में हेरफेर करने और उन्हें PDF सहित विभिन्न स्वरूपों में बदलने के लिए बहुत लचीलापन प्रदान करता है। अब आप इस ज्ञान को Aspose.Words for .NET का उपयोग करके अपनी स्वयं की PDF फ़ाइलों में टिप्पणियाँ हटाने के लिए लागू कर सकते हैं।

### पीडीएफ फाइल में टिप्पणियां हटाने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में दस्तावेज़ कैसे अपलोड करें?

 उत्तर: का प्रयोग करें`Document` फ़ाइल से दस्तावेज़ लोड करने के लिए .NET के लिए Aspose.Words की क्लास। आप पूर्ण दस्तावेज़ पथ निर्दिष्ट कर सकते हैं।

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### प्रश्न: .NET के लिए Aspose.Words से उत्पन्न PDF में टिप्पणियाँ कैसे छिपाएँ?

 उत्तर: का प्रयोग करें`CommentDisplayMode` की संपत्ति`LayoutOptions` पीडीएफ जेनरेट करते समय टिप्पणियाँ कैसे प्रदर्शित की जाएँ, इसे कॉन्फ़िगर करने के लिए ऑब्जेक्ट। टिप्पणियाँ छिपाने के लिए, इस प्रॉपर्टी को इस पर सेट करें`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### प्रश्न: .NET के लिए Aspose.Words के साथ दस्तावेज़ को PDF के रूप में कैसे सहेजें?

 उत्तर: का प्रयोग करें`Save` की विधि`Document` दस्तावेज़ को PDF प्रारूप में सहेजने के लिए ऑब्जेक्ट का उपयोग करें। PDF फ़ाइल का पूरा पथ निर्दिष्ट करें।

```csharp
doc.Save("path/to/the/file.pdf");
```