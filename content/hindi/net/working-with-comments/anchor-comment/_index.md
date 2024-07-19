---
title: एंकर टिप्पणी
linktitle: एंकर टिप्पणी
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में विशिष्ट पाठ पर टिप्पणी उत्तरों को एंकर करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-comments/anchor-comment/
---

इस व्यापक ट्यूटोरियल में, आप सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में विशिष्ट टेक्स्ट पर टिप्पणी उत्तरों को कैसे एंकर किया जाए। हम आपको इस प्रक्रिया के माध्यम से मार्गदर्शन करेंगे और आपको आवश्यक C# कोड स्निपेट प्रदान करेंगे। इस गाइड के अंत तक, आप अपने दस्तावेज़ों में विशिष्ट टेक्स्ट के साथ टिप्पणियों को संबद्ध करने में सक्षम होंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- आपके सिस्टम पर Aspose.Words for .NET लाइब्रेरी स्थापित है।

## चरण 1: नया दस्तावेज़ बनाएँ और टेक्स्ट जोड़ें
आरंभ करने के लिए, Document वर्ग का उपयोग करके एक नया दस्तावेज़ बनाएं और इच्छित पाठ जोड़ें:

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
इसके बाद, एक टिप्पणी बनाएं और उसे CommentRangeStart और CommentRangeEnd ऑब्जेक्ट का उपयोग करके विशिष्ट टेक्स्ट के साथ संबद्ध करें:

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
टिप्पणी को विशिष्ट पाठ पर एंकर करने के बाद, Document वर्ग की Save विधि का उपयोग करके दस्तावेज़ को फ़ाइल में सहेजें:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### .NET के लिए Aspose.Words का उपयोग करके एंकर टिप्पणी उत्तर के लिए उदाहरण स्रोत कोड
.NET के लिए Aspose.Words का उपयोग करके टिप्पणी उत्तर को एंकर करने के लिए पूरा स्रोत कोड यहां दिया गया है:

```csharp
// दस्तावेज़ का एक उदाहरण बनाएँ.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// तीन रन ऑब्जेक्ट बनाएं.
//पहले दो में कुछ पाठ है, जबकि तीसरे में एक टिप्पणी है

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

// प्रत्येक Run ऑब्जेक्ट में एक CommentRangeStart और CommentRangeEnd ऑब्जेक्ट संबद्ध होता है।

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: Aspose.Words for .NET में टिप्पणी एंकर क्या है?

उत्तर: .NET के लिए Aspose.Words में, एक टिप्पणी एंकर एक मार्कर है जो एक टिप्पणी को दस्तावेज़ में एक विशिष्ट स्थान से जोड़ता है।

#### प्रश्न: मैं Aspose.Words for .NET दस्तावेज़ में टिप्पणी एंकर कैसे जोड़ सकता हूं?

उत्तर: Aspose.Words for .NET दस्तावेज़ में टिप्पणी एंकर जोड़ने के लिए, ट्यूटोरियल में बताए गए चरणों का पालन करें।

#### प्रश्न: मैं Aspose.Words for .NET में मौजूदा टिप्पणी एंकर तक कैसे पहुंच सकता हूं?

 A: आप Aspose.Words for .NET में मौजूदा टिप्पणी एंकर तक पहुंच सकते हैं`Comment.Anchor` संपत्ति।

#### प्रश्न: क्या मैं .NET के लिए Aspose.Words में एक टिप्पणी एंकर का समर्थन कर सकता हूं?

 उत्तर: हां, आप .NET के लिए Aspose.Words में टिप्पणी एंकर को हटा सकते हैं`Comment.Remove` तरीका।

#### प्रश्न: मैं Aspose.Words for .NET में टिप्पणी एंकर से जुड़ी टिप्पणी के पाठ को कैसे संपादित कर सकता हूं?

A: Aspose.Words for .NET में टिप्पणी एंकर से जुड़ी टिप्पणी के पाठ को संशोधित करने के लिए, आप इसका उपयोग कर सकते हैं`Comment.Text` संबंधित संपत्ति`Comment` ऑब्जेक्ट पर क्लिक करें और आवश्यकतानुसार पाठ को संशोधित करें।

