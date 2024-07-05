---
title: शब्दों के प्रकार का पुनरीक्षण प्राप्त करें
linktitle: शब्दों के प्रकार का पुनरीक्षण प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में शब्दों के संशोधन प्रकार प्राप्त करें।
type: docs
weight: 10
url: /hi/net/working-with-revisions/get-revision-types/
---

इस चरण-दर-चरण मार्गदर्शिका में, हम आपको बताएंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में शब्दों के संशोधन के प्रकार कैसे प्राप्त करें। हम आपको पूरा स्रोत कोड प्रदान करेंगे और आपको दिखाएंगे कि मार्कडाउन आउटपुट को कैसे प्रारूपित किया जाए।

## चरण 1: दस्तावेज़ लोड करना

पहला चरण संशोधनों वाले दस्तावेज़ को अपलोड करना है।

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## चरण 2: पैराग्राफ़ों के माध्यम से आगे बढ़ें

इसके बाद, हम दस्तावेज़ के पैराग्राफों को देखेंगे और प्रत्येक पैराग्राफ से जुड़े शब्द संशोधनों के प्रकार की जांच करेंगे।

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

इस ट्यूटोरियल में, हमने सीखा कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में शब्दों के संशोधन के प्रकार कैसे प्राप्त करें। हमने दस्तावेज़ को लोड करने, पैराग्राफ़ देखने और प्रत्येक पैराग्राफ़ से जुड़े शब्द समीक्षाओं के प्रकारों की जाँच करने के लिए चरणों का पालन किया। अब आप इस ज्ञान को Aspose.Words for .NET का उपयोग करके अपने स्वयं के Word दस्तावेज़ों में शब्द समीक्षाओं का विश्लेषण करने के लिए लागू कर सकते हैं।

### शब्दों के संशोधन प्रकार के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में दस्तावेज़ कैसे अपलोड करें?

 उत्तर: का प्रयोग करें`Document` फ़ाइल से दस्तावेज़ लोड करने के लिए .NET के लिए Aspose.Words की क्लास। आप पूर्ण दस्तावेज़ पथ निर्दिष्ट कर सकते हैं।

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### प्रश्न: मैं Aspose.Words for .NET में किसी दस्तावेज़ में पैराग्राफ़ के माध्यम से लूप कैसे करूँ?

 उत्तर: का प्रयोग करें`Paragraphs` पैराग्राफ़ का संग्रह प्राप्त करने के लिए दस्तावेज़ अनुभाग की संपत्ति। फिर आप प्रत्येक पैराग्राफ़ के माध्यम से लूप का उपयोग कर सकते हैं।

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // प्रत्येक पैराग्राफ़ को यहाँ प्रोसेस करें
}
```

#### प्रश्न: Aspose.Words for .NET में कैसे जांचें कि कोई पैराग्राफ़ स्थानांतरित (हटा) गया है या नहीं?

 उत्तर: एक पैराग्राफ का उपयोग करें`IsMoveFromRevision`संपत्ति को यह जांचने के लिए चुनें कि क्या इसे स्थानांतरित (हटा) किया गया है।

```csharp
if (paragraph. IsMove

FromRevision)
{
     // पैराग्राफ़ को स्थानांतरित कर दिया गया है (हटा दिया गया है)
}
```

#### प्रश्न: Aspose.Words for .NET में कैसे जांचें कि कोई पैराग्राफ़ स्थानांतरित (सम्मिलित) किया गया है?

 उत्तर: एक पैराग्राफ का उपयोग करें`IsMoveToRevision` संपत्ति को यह जांचने के लिए चुनें कि क्या इसे स्थानांतरित (सम्मिलित) किया गया है।

```csharp
if (paragraph.IsMoveToRevision)
{
     // पैराग्राफ़ को स्थानांतरित कर दिया गया है (सम्मिलित किया गया है)
}
```