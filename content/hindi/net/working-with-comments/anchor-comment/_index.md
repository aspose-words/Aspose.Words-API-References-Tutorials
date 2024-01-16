---
title: एंकर टिप्पणी
linktitle: एंकर टिप्पणी
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में विशिष्ट पाठ पर टिप्पणी उत्तरों को एंकर करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-comments/anchor-comment/
---

इस व्यापक ट्यूटोरियल में, आप सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में विशिष्ट पाठ पर टिप्पणी उत्तरों को कैसे एंकर किया जाए। हम प्रक्रिया में आपका मार्गदर्शन करेंगे और आपको आवश्यक C# कोड स्निपेट प्रदान करेंगे। इस गाइड के अंत तक, आप टिप्पणियों को अपने दस्तावेज़ों में विशिष्ट पाठ के साथ संबद्ध करने में सक्षम होंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- आपके सिस्टम पर .NET लाइब्रेरी के लिए Aspose.Words इंस्टॉल किया गया है।

## चरण 1: एक नया दस्तावेज़ बनाएं और टेक्स्ट जोड़ें
आरंभ करने के लिए, दस्तावेज़ वर्ग का उपयोग करके एक नया दस्तावेज़ बनाएं और वांछित पाठ जोड़ें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## चरण 2: एक टिप्पणी बनाएं और टिप्पणी श्रेणी जोड़ें
इसके बाद, एक टिप्पणी बनाएं और इसे CommentRangeStart और CommentRangeEnd ऑब्जेक्ट का उपयोग करके विशिष्ट पाठ के साथ संबद्ध करें:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## चरण 3: दस्तावेज़ सहेजें
टिप्पणी को विशिष्ट पाठ में एंकर करने के बाद, दस्तावेज़ वर्ग की सेव विधि का उपयोग करके दस्तावेज़ को फ़ाइल में सहेजें:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### .NET के लिए Aspose.Words का उपयोग करके एंकर टिप्पणी उत्तर के लिए उदाहरण स्रोत कोड
.NET के लिए Aspose.Words का उपयोग करके एक टिप्पणी उत्तर को एंकर करने के लिए संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp
// दस्तावेज़ का एक उदाहरण बनाएँ।
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// तीन रन ऑब्जेक्ट बनाएं।
// पहले दो कुछ पाठ चलाते हैं, जबकि तीसरा एक टिप्पणी चलाता है

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

// प्रत्येक रन ऑब्जेक्ट में एक संबंधित CommentRangeStart और CommentRangeEnd ऑब्जेक्ट होता है।

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में एक टिप्पणी एंकर क्या है?

उ: .NET के लिए Aspose.Words में, एक टिप्पणी एंकर एक मार्कर है जो एक टिप्पणी को किसी दस्तावेज़ में एक विशिष्ट स्थान से जोड़ता है।

#### प्रश्न: मैं Aspose.Words for .NET दस्तावेज़ में एक टिप्पणी एंकर कैसे जोड़ सकता हूँ?

उ: Aspose.Words for .NET दस्तावेज़ में एक टिप्पणी एंकर जोड़ने के लिए, ट्यूटोरियल में उल्लिखित चरणों का पालन करें।

#### प्रश्न: मैं .NET के लिए Aspose.Words में मौजूदा टिप्पणी एंकर तक कैसे पहुंच सकता हूं?

 उ: आप इसका उपयोग करके .NET के लिए Aspose.Words में मौजूदा टिप्पणी एंकर तक पहुंच सकते हैं`Comment.Anchor` संपत्ति।

#### प्रश्न: क्या मैं .NET के लिए Aspose.Words में एक टिप्पणी एंकर का समर्थन कर सकता हूँ?

 उत्तर: हाँ, आप .NET के लिए Aspose.Words में एक टिप्पणी एंकर को हटा सकते हैं`Comment.Remove` तरीका।

#### प्रश्न: मैं .NET के लिए Aspose.Words में किसी टिप्पणी एंकर से जुड़ी टिप्पणी के पाठ को कैसे संपादित कर सकता हूं?

 उ: .NET के लिए Aspose.Words में एक टिप्पणी एंकर से जुड़ी टिप्पणी के पाठ को संशोधित करने के लिए, आप इसका उपयोग कर सकते हैं`Comment.Text` संबंधित की संपत्ति`Comment` ऑब्जेक्ट करें और आवश्यकतानुसार टेक्स्ट को संशोधित करें।

