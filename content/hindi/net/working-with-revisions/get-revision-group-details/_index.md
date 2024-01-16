---
title: पुनरीक्षण समूह विवरण प्राप्त करें
linktitle: पुनरीक्षण समूह विवरण प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में संशोधन समूह विवरण प्राप्त करें।
type: docs
weight: 10
url: /hi/net/working-with-revisions/get-revision-group-details/
---

इस चरण-दर-चरण मार्गदर्शिका में, हम आपको यह दिखाने जा रहे हैं कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में संशोधनों के समूह का विवरण कैसे प्राप्त करें। हम आपको संपूर्ण स्रोत कोड प्रदान करेंगे और आपको दिखाएंगे कि मार्कडाउन आउटपुट को कैसे प्रारूपित किया जाए।

## चरण 1: दस्तावेज़ लोड करना

पहला कदम संशोधन वाले दस्तावेज़ को अपलोड करना है।

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## चरण 2: संशोधन ब्राउज़ करें

इसके बाद, हम दस्तावेज़ में मौजूद संशोधनों के माध्यम से लूप करेंगे और उनके विवरण, जैसे प्रकार, लेखक, तिथि और संशोधित पाठ प्रदर्शित करेंगे।

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### .NET के लिए Aspose.Words का उपयोग करके संशोधन समूह विवरण प्राप्त करने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में संशोधनों के समूह का विवरण प्राप्त करने के लिए संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में संशोधनों के समूह का विवरण कैसे प्राप्त किया जाए। एक लूप और उपयुक्त गुणों का उपयोग करके, हम संशोधन प्रकार, लेखक, तिथि और संशोधित पाठ जैसे विवरण प्रदर्शित करने में सक्षम थे। .NET के लिए Aspose.Words संशोधन प्रबंधन सहित Word दस्तावेज़ों में हेरफेर करने के लिए कई शक्तिशाली सुविधाएँ प्रदान करता है। अब आप इस ज्ञान का उपयोग .NET के लिए Aspose.Words का उपयोग करके अपने स्वयं के Word दस्तावेज़ों में संशोधन समूह विवरण प्राप्त करने के लिए कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं .NET के लिए Aspose.Words में संशोधन के साथ एक दस्तावेज़ कैसे लोड करूं?

 ए: का प्रयोग करें`Document`संशोधन वाली फ़ाइल से दस्तावेज़ लोड करने के लिए .NET के लिए Aspose.Words का वर्ग। आप संपूर्ण दस्तावेज़ पथ निर्दिष्ट कर सकते हैं.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### प्रश्न: मैं .NET के लिए Aspose.Words में एक संशोधन समूह का विवरण कैसे प्राप्त करूं?

 उ: एक लूप का उपयोग करके दस्तावेज़ के संशोधनों पर जाएँ और अपने इच्छित विवरण प्राप्त करने के लिए प्रत्येक संशोधन के गुणों तक पहुँचें। आप इसका उपयोग कर सकते हैं`RevisionType`, `Author`, `DateTime` और`ParentNode` क्रमशः संशोधन प्रकार, लेखक, दिनांक और संशोधित पाठ प्राप्त करने के लिए गुण।

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### प्रश्न: कैसे जांचें कि कोई संशोधन .NET के लिए Aspose.Words में किसी समूह से संबंधित है?

 ए: का प्रयोग करें`Group` की संपत्ति`Revision` यह जांचने के लिए ऑब्जेक्ट करें कि कोई संशोधन किसी समूह से संबंधित है या नहीं। यदि`Group` संपत्ति है`null`इसका मतलब यह है कि संशोधन किसी समूह से संबंधित नहीं है।

```csharp
if (revision.Group != null)
{
      // संशोधन एक समूह का है
}
else
{
      // संशोधन किसी समूह से संबंधित नहीं है
}
```