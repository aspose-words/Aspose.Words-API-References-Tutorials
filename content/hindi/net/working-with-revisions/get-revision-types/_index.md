---
title: शब्दों के संशोधन प्रकार प्राप्त करें
linktitle: शब्दों के संशोधन प्रकार प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ किसी Word दस्तावेज़ में शब्दों के संशोधन प्रकार प्राप्त करें।
type: docs
weight: 10
url: /hi/net/working-with-revisions/get-revision-types/
---

इस चरण-दर-चरण मार्गदर्शिका में, हम आपको बताने जा रहे हैं कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में शब्दों के प्रकार कैसे प्राप्त करें। हम आपको संपूर्ण स्रोत कोड प्रदान करेंगे और आपको दिखाएंगे कि मार्कडाउन आउटपुट को कैसे प्रारूपित किया जाए।

## चरण 1: दस्तावेज़ लोड करना

पहला कदम संशोधन वाले दस्तावेज़ को अपलोड करना है।

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## चरण 2: पैराग्राफ के माध्यम से कदम बढ़ाएं

इसके बाद, हम दस्तावेज़ के पैराग्राफों का अध्ययन करेंगे और प्रत्येक पैराग्राफ से जुड़े शब्दों के प्रकार की जाँच करेंगे।

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### .NET के लिए Aspose.Words का उपयोग करके संशोधन प्रकार प्राप्त करने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में संशोधन प्रकार प्राप्त करने के लिए पूर्ण स्रोत कोड यहां दिया गया है:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में शब्दों के प्रकार कैसे प्राप्त करें। हमने दस्तावेज़ को लोड करने, पैराग्राफों को पढ़ने और प्रत्येक पैराग्राफ से जुड़े शब्द समीक्षाओं के प्रकारों की जांच करने के लिए चरणों का पालन किया। अब आप .NET के लिए Aspose.Words का उपयोग करके अपने स्वयं के Word दस्तावेज़ों में शब्द समीक्षाओं का विश्लेषण करने के लिए इस ज्ञान को लागू कर सकते हैं।

### शब्दों के संशोधन प्रकार प्राप्त करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में दस्तावेज़ कैसे अपलोड करें?

 ए: का प्रयोग करें`Document` किसी फ़ाइल से दस्तावेज़ लोड करने के लिए .NET के लिए Aspose.Words का वर्ग। आप संपूर्ण दस्तावेज़ पथ निर्दिष्ट कर सकते हैं.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### प्रश्न: मैं .NET के लिए Aspose.Words में किसी दस्तावेज़ में पैराग्राफ के माध्यम से कैसे लूप करूं?

 ए: का प्रयोग करें`Paragraphs` अनुच्छेदों का संग्रह प्राप्त करने के लिए दस्तावेज़ अनुभाग की संपत्ति। फिर आप प्रत्येक पैराग्राफ को लूप करने के लिए लूप का उपयोग कर सकते हैं।

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // प्रत्येक अनुच्छेद को यहां संसाधित करें
}
```

#### प्रश्न: यह कैसे जांचें कि .NET के लिए Aspose.Words में कोई पैराग्राफ़ स्थानांतरित (हटाया गया) हो गया है?

 उत्तर: पैराग्राफ का प्रयोग करें`IsMoveFromRevision` संपत्ति की जाँच करें कि क्या उसे स्थानांतरित (हटाया) गया है।

```csharp
if (paragraph. IsMove

FromRevision)
{
     // अनुच्छेद को स्थानांतरित कर दिया गया है (हटा दिया गया है)
}
```

#### प्रश्न: यह कैसे जांचें कि .NET के लिए Aspose.Words में कोई पैराग्राफ़ स्थानांतरित (डाला) गया है?

 उत्तर: पैराग्राफ का प्रयोग करें`IsMoveToRevision`यह जांचने के लिए संपत्ति कि क्या इसे स्थानांतरित (डाला) किया गया है।

```csharp
if (paragraph.IsMoveToRevision)
{
     // अनुच्छेद को स्थानांतरित कर दिया गया है (सम्मिलित किया गया है)
}
```