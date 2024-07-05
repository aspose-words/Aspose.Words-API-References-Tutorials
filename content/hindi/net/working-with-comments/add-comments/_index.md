---
title: टिप्पणी करें
linktitle: टिप्पणी करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में टिप्पणियाँ जोड़ना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-comments/add-comments/
---

इस व्यापक ट्यूटोरियल में, आप सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में टिप्पणियाँ कैसे जोड़ें। हम आपको इस प्रक्रिया में मार्गदर्शन करेंगे और आपको आवश्यक C# कोड स्निपेट प्रदान करेंगे। इस गाइड के अंत तक, आप अपने दस्तावेज़ों में टिप्पणियाँ सम्मिलित करने और उनकी सामग्री को अनुकूलित करने में सक्षम होंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- आपके सिस्टम पर Aspose.Words for .NET लाइब्रेरी स्थापित है।

## चरण 1: नया दस्तावेज़ और दस्तावेज़बिल्डर बनाएँ
आरंभ करने के लिए, Document वर्ग का उपयोग करके एक नया दस्तावेज़ बनाएं और DocumentBuilder ऑब्जेक्ट को आरंभीकृत करें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: दस्तावेज़ में सामग्री जोड़ें
इसके बाद, DocumentBuilder ऑब्जेक्ट का उपयोग करके दस्तावेज़ में वांछित सामग्री जोड़ें। इस उदाहरण में, हम कुछ पाठ जोड़ते हैं:

```csharp
builder.Write("Some text is added.");
```

## चरण 3: टिप्पणी बनाएं और सामग्री जोड़ें
टिप्पणी जोड़ने के लिए, Document ऑब्जेक्ट, लेखक का नाम, लेखक के नाम के पहले अक्षर और वर्तमान दिनांक को पास करते हुए, Comment वर्ग का एक उदाहरण बनाएँ:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

इसके बाद, टिप्पणी को वर्तमान पैराग्राफ में जोड़ें:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

टिप्पणी में विषय-वस्तु जोड़ें, जैसे पैराग्राफ और पाठ:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## चरण 4: दस्तावेज़ सहेजें
टिप्पणी और उसकी सामग्री जोड़ने के बाद, Document वर्ग की Save विधि का उपयोग करके दस्तावेज़ को फ़ाइल में सहेजें:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## .NET के लिए Aspose.Words का उपयोग करके टिप्पणियाँ जोड़ने के लिए उदाहरण स्रोत कोड
.NET के लिए Aspose.Words का उपयोग करके टिप्पणियाँ जोड़ने के लिए पूरा स्रोत कोड यहां दिया गया है:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## निष्कर्ष
बधाई हो! आपने सफलतापूर्वक सीख लिया है कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में टिप्पणियाँ कैसे जोड़ें। चरण-दर-चरण मार्गदर्शिका का पालन करके और प्रदान किए गए स्रोत कोड का उपयोग करके, अब आप अपने दस्तावेज़ों में टिप्पणियाँ डाल सकते हैं और उनकी सामग्री को अनुकूलित कर सकते हैं।

टिप्पणियाँ सहयोग करने, अतिरिक्त जानकारी प्रदान करने या दस्तावेज़ के भीतर नोट्स बनाने के लिए उपयोगी होती हैं। अपनी विशिष्ट आवश्यकताओं को पूरा करने के लिए अलग-अलग लेखक के नाम, आद्याक्षर और टिप्पणी सामग्री के साथ प्रयोग करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words for .NET दस्तावेज़ में टिप्पणी कैसे जोड़ सकता हूँ?

A: Aspose.Words for .NET दस्तावेज़ में टिप्पणी जोड़ने के लिए, आपको ट्यूटोरियल में बताए गए चरणों का पालन करना होगा।

#### प्रश्न: क्या मैं .NET के लिए Aspose.Words में टिप्पणी पाठ को प्रारूपित कर सकता हूं?

उत्तर: हां, आप उपलब्ध स्वरूपण गुणों का उपयोग करके .NET के लिए Aspose.Words में टिप्पणी पाठ को प्रारूपित कर सकते हैं।

#### प्रश्न: मैं किसी दस्तावेज़ में मौजूद सभी टिप्पणियाँ कैसे प्राप्त कर सकता हूँ?

 उत्तर: आप किसी दस्तावेज़ में मौजूद सभी टिप्पणियाँ पुनः प्राप्त कर सकते हैं`Document.Comments` संपत्ति।

#### प्रश्न: क्या मैं .NET के लिए Aspose.Words में कोई विशिष्ट टिप्पणी हटा सकता हूँ?

 उत्तर: हां, आप .NET के लिए Aspose.Words में एक विशिष्ट टिप्पणी को हटा सकते हैं`Comment.Remove` तरीका।

#### प्रश्न: मैं Aspose.Words for .NET में किसी मौजूदा टिप्पणी के पाठ को कैसे संशोधित कर सकता हूं?

 A: Aspose.Words for .NET में मौजूदा टिप्पणी के पाठ को संशोधित करने के लिए, आप इसका उपयोग कर सकते हैं`Comment.Text` संबंधित संपत्ति`Comment` ऑब्जेक्ट पर क्लिक करें और आवश्यकतानुसार पाठ को संशोधित करें।