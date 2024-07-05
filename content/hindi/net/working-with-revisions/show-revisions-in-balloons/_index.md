---
title: संशोधनों को गुब्बारों में दिखाएं
linktitle: संशोधनों को गुब्बारों में दिखाएं
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ गुब्बारों में संशोधन दिखाएं।
type: docs
weight: 10
url: /hi/net/working-with-revisions/show-revisions-in-balloons/
---

इस चरण-दर-चरण मार्गदर्शिका में, हम आपको दिखाएंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में गुब्बारों में संशोधन कैसे दिखाएं। हम आपको पूरा स्रोत कोड प्रदान करेंगे और आपको दिखाएंगे कि मार्कडाउन आउटपुट को कैसे प्रारूपित किया जाए।

## चरण 1: दस्तावेज़ लोड करना

पहला चरण संशोधनों वाले दस्तावेज़ को अपलोड करना है।

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

## चरण 3: दस्तावेज़ को PDF प्रारूप में सहेजें

अंत में, हम दस्तावेज़ को पीडीएफ के रूप में सहेज लेंगे, जिसमें संशोधन गुब्बारों में दिखाए जाएंगे।

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## मार्कडाउन आउटपुट प्रारूप

पठनीयता में सुधार के लिए आउटपुट को मार्कडाउन में फ़ॉर्मेट किया जा सकता है। उदाहरण के लिए:

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### .NET के लिए Aspose.Words का उपयोग करके गुब्बारों में संशोधन दिखाने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में गुब्बारों में संशोधन दिखाने के लिए यहां पूर्ण स्रोत कोड दिया गया है:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// रेंडर्स संशोधनों को इनलाइन सम्मिलित करते हैं, संशोधनों को हटाते हैं और गुब्बारों में प्रारूपित करते हैं।
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// पृष्ठ के दाईं ओर संशोधन पट्टियाँ प्रस्तुत करता है।
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में गुब्बारों में संशोधन कैसे प्रदर्शित करें। उचित प्रदर्शन विकल्पों का उपयोग करके, हम संशोधनों को दाईं ओर संशोधन पट्टियों के साथ बुलबुले में दृश्यमान बनाने में सक्षम थे। Aspose.Words for .NET Word दस्तावेज़ों में हेरफेर करने के लिए कई शक्तिशाली सुविधाएँ प्रदान करता है, जिसमें संशोधन प्रबंधन शामिल है। अब आप इस ज्ञान का उपयोग Aspose.Words for .NET का उपयोग करके अपने स्वयं के Word दस्तावेज़ों में गुब्बारों में संशोधन दिखाने के लिए कर सकते हैं।


### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में दस्तावेज़ कैसे अपलोड करें?

 उत्तर: का प्रयोग करें`Document` फ़ाइल से दस्तावेज़ लोड करने के लिए .NET के लिए Aspose.Words की क्लास। आप पूर्ण दस्तावेज़ पथ निर्दिष्ट कर सकते हैं।

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### प्रश्न: .NET के लिए Aspose.Words के साथ गुब्बारों में संशोधन कैसे प्रदर्शित करें?

 उत्तर: का प्रयोग करें`ShowInBalloons` की संपत्ति`RevisionOptions` गुब्बारों में संशोधनों के प्रदर्शन को कॉन्फ़िगर करने के लिए ऑब्जेक्ट। आप इस प्रॉपर्टी को सेट कर सकते हैं`ShowInBalloons.FormatAndDelete` संशोधनों को विलोपन और प्रारूपण के साथ गुब्बारों में दिखाने के लिए।

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### प्रश्न: .NET के लिए Aspose.Words के साथ PDF प्रारूप में दस्तावेज़ कैसे सहेजें?

 उत्तर: का प्रयोग करें`Save` की विधि`Document` दस्तावेज़ को PDF प्रारूप में सहेजने के लिए ऑब्जेक्ट का उपयोग करें। आपको ".pdf" एक्सटेंशन के साथ पूरा गंतव्य पथ निर्दिष्ट करना होगा।

```csharp
doc.Save("path/to/destination/document.pdf");
```