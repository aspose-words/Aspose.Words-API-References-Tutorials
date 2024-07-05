---
title: संशोधन समूह प्राप्त करें
linktitle: संशोधन समूह प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में संशोधन समूह प्राप्त करें।
type: docs
weight: 10
url: /hi/net/working-with-revisions/get-revision-groups/
---

इस चरण-दर-चरण मार्गदर्शिका में, हम आपको बताएंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में संशोधन समूह कैसे प्राप्त करें। हम आपको पूरा स्रोत कोड प्रदान करेंगे और आपको दिखाएंगे कि मार्कडाउन आउटपुट को कैसे प्रारूपित किया जाए।

## चरण 1: दस्तावेज़ लोड करना

पहला चरण संशोधनों वाले दस्तावेज़ को अपलोड करना है।

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## चरण 2: संशोधन समूह ब्राउज़ करें

इसके बाद, हम दस्तावेज़ में मौजूद संशोधन समूहों को देखेंगे और उनके विवरण प्रदर्शित करेंगे, जैसे कि लेखक, संशोधन प्रकार और संशोधित पाठ।

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### .NET के लिए Aspose.Words का उपयोग करके रिविज़न समूह प्राप्त करने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में संशोधन समूह प्राप्त करने के लिए यहां पूर्ण स्रोत कोड दिया गया है:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में संशोधन समूह कैसे प्राप्त करें। हमने दस्तावेज़ को लोड करने और समीक्षा समूहों को ब्राउज़ करने के लिए चरणों का पालन किया, लेखक और समीक्षा प्रकार जैसे विवरण प्रदर्शित किए। अब आप इस ज्ञान को Aspose.Words for .NET का उपयोग करके अपने स्वयं के Word दस्तावेज़ के संशोधनों का विश्लेषण करने के लिए लागू कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में दस्तावेज़ कैसे अपलोड करें?

 उत्तर: का प्रयोग करें`Document` फ़ाइल से दस्तावेज़ लोड करने के लिए .NET के लिए Aspose.Words की क्लास। आप पूर्ण दस्तावेज़ पथ निर्दिष्ट कर सकते हैं।

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### प्रश्न: Aspose.Words for .NET में किसी दस्तावेज़ में संशोधन समूहों को कैसे ब्राउज़ करें?

 उत्तर: का प्रयोग करें`Groups` दस्तावेज़ की संपत्ति`Revisions`संशोधन समूहों का संग्रह प्राप्त करने के लिए ऑब्जेक्ट। फिर आप प्रत्येक समीक्षा समूह के माध्यम से लूप का उपयोग कर सकते हैं।

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // प्रत्येक समीक्षा समूह की प्रक्रिया यहां करें
}
```

#### प्रश्न: Aspose.Words for .NET में समीक्षा समूह के लेखक को कैसे प्राप्त करें?

 उत्तर: का प्रयोग करें`Author` की संपत्ति`RevisionGroup` संशोधन समूह के लेखक को पाने के लिए ऑब्जेक्ट का उपयोग करें।

```csharp
string author = group.Author;
```

#### प्रश्न: Aspose.Words for .NET में संशोधन समूह का संशोधन प्रकार कैसे प्राप्त करें?

 उत्तर: का प्रयोग करें`RevisionType` की संपत्ति`RevisionGroup` समूह का संशोधन प्रकार प्राप्त करने के लिए ऑब्जेक्ट का उपयोग करें।

```csharp
string revisionType = group.RevisionType;
```