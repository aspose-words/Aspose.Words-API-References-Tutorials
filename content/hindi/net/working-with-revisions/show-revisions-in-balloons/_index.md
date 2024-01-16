---
title: गुब्बारों में संशोधन दिखाएँ
linktitle: गुब्बारों में संशोधन दिखाएँ
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ गुब्बारों में संशोधन दिखाएं।
type: docs
weight: 10
url: /hi/net/working-with-revisions/show-revisions-in-balloons/
---

इस चरण-दर-चरण मार्गदर्शिका में, हम आपको यह दिखाने जा रहे हैं कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में गुब्बारों में संशोधन कैसे दिखाया जाए। हम आपको संपूर्ण स्रोत कोड प्रदान करेंगे और आपको दिखाएंगे कि मार्कडाउन आउटपुट को कैसे प्रारूपित किया जाए।

## चरण 1: दस्तावेज़ लोड करना

पहला कदम संशोधन वाले दस्तावेज़ को अपलोड करना है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## चरण 2: समीक्षा शो विकल्प कॉन्फ़िगर करें

हम संशोधनों को गुब्बारों में दृश्यमान बनाने के लिए शो विकल्पों को कॉन्फ़िगर करेंगे।

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## चरण 3: दस्तावेज़ को पीडीएफ प्रारूप में सहेजें

अंत में, हम दस्तावेज़ को गुब्बारों में दिखाए गए संशोधनों के साथ पीडीएफ के रूप में सहेजेंगे।

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## मार्कडाउन आउटपुट प्रारूप

पठनीयता में सुधार के लिए आउटपुट को मार्कडाउन में स्वरूपित किया जा सकता है। उदाहरण के लिए :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### .NET के लिए Aspose.Words का उपयोग करके गुब्बारों में संशोधन दिखाने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में गुब्बारों में संशोधन दिखाने के लिए संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// रेंडर गुब्बारों में संशोधनों को इनलाइन सम्मिलित करते हैं, हटाते हैं और संशोधनों को प्रारूपित करते हैं।
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// किसी पृष्ठ के दाईं ओर पुनरीक्षण पट्टियाँ प्रस्तुत करता है।
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में गुब्बारों में संशोधन कैसे प्रदर्शित करें। उचित प्रदर्शन विकल्पों का उपयोग करके, हम संशोधनों को दाईं ओर संशोधन पट्टियों के साथ बुलबुले में दृश्यमान बनाने में सक्षम थे। .NET के लिए Aspose.Words संशोधन प्रबंधन सहित Word दस्तावेज़ों में हेरफेर करने के लिए कई शक्तिशाली सुविधाएँ प्रदान करता है। अब आप इस ज्ञान का उपयोग .NET के लिए Aspose.Words का उपयोग करके अपने स्वयं के Word दस्तावेज़ों में गुब्बारों में संशोधन दिखाने के लिए कर सकते हैं।


### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में दस्तावेज़ कैसे अपलोड करें?

 ए: का प्रयोग करें`Document` किसी फ़ाइल से दस्तावेज़ लोड करने के लिए .NET के लिए Aspose.Words का वर्ग। आप संपूर्ण दस्तावेज़ पथ निर्दिष्ट कर सकते हैं.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### प्रश्न: .NET के लिए Aspose.Words के साथ गुब्बारों में संशोधन कैसे प्रदर्शित करें?

 ए: का प्रयोग करें`ShowInBalloons` की संपत्ति`RevisionOptions` गुब्बारों में संशोधनों के प्रदर्शन को कॉन्फ़िगर करने के लिए ऑब्जेक्ट। आप इस संपत्ति को चालू कर सकते हैं`ShowInBalloons.FormatAndDelete` विलोपन और स्वरूपण संशोधनों के साथ गुब्बारों में संशोधन दिखाने के लिए।

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### प्रश्न: .NET के लिए Aspose.Words के साथ किसी दस्तावेज़ को PDF प्रारूप में कैसे सहेजें?

 ए: का प्रयोग करें`Save` की विधि`Document` दस्तावेज़ को पीडीएफ प्रारूप में सहेजने के लिए ऑब्जेक्ट करें। आपको ".pdf" एक्सटेंशन के साथ पूरा गंतव्य पथ निर्दिष्ट करना होगा।

```csharp
doc.Save("path/to/destination/document.pdf");
```