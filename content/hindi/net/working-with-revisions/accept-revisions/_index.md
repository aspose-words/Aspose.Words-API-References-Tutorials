---
title: संशोधन स्वीकार करें
linktitle: संशोधन स्वीकार करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में संशोधन स्वीकार करना सीखें
type: docs
weight: 10
url: /hi/net/working-with-revisions/accept-revisions/
---

इस ट्यूटोरियल में, हम आपको Aspose.Words for .NET की Accept Revisions सुविधा का उपयोग करके Word दस्तावेज़ में संशोधन स्वीकार करने के बारे में बताएँगे। स्रोत कोड को समझने और दस्तावेज़ में परिवर्तन स्वीकार करने के लिए नीचे दिए गए चरणों का पालन करें।

## चरण 1: दस्तावेज़ सामग्री जोड़ना और संपादित करना

इस उदाहरण में, हम एक दस्तावेज़ बना रहे हैं और उसमें सामग्री जोड़ रहे हैं। हम परिवर्तनों और संशोधनों को दर्शाने के लिए कई पैराग्राफ़ का उपयोग करते हैं। यहाँ बताया गया है कि कैसे:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// पहले पैराग्राफ में पाठ जोड़ें, फिर दो और पैराग्राफ जोड़ें।
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## चरण 2: समीक्षाओं को ट्रैक करें और समीक्षाएँ जोड़ें

हम संशोधन ट्रैकिंग सक्षम करते हैं और दस्तावेज़ में संशोधन जोड़ते हैं। यहाँ बताया गया है कि कैसे:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// यह पैराग्राफ एक संशोधन है और इसमें संगत "IsInsertRevision" ध्वज सेट होगा।
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## चरण 3: पैराग्राफ़ हटाएं और संशोधन प्रबंधित करें

हम पैराग्राफ़ हटाते हैं और सहेजे गए संशोधनों की जांच करते हैं। यह इस प्रकार है:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// चूंकि हम संशोधनों पर नज़र रख रहे हैं, इसलिए अनुच्छेद अभी भी दस्तावेज़ में मौजूद है, इसमें "IsDeleteRevision" फ़्लैग सेट होगा
// और इसे माइक्रोसॉफ्ट वर्ड में समीक्षा के रूप में प्रदर्शित किया जाएगा, जब तक कि हम सभी समीक्षाओं को स्वीकार या अस्वीकार नहीं कर देते।
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## चरण 4: परिवर्तन स्वीकार करें

हम दस्तावेज़ में सभी बदलावों को स्वीकार करते हैं। यहाँ बताया गया है कि कैसे:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## चरण 5: समीक्षाओं पर नज़र रखना बंद करें

हम संशोधनों को ट्रैक करना बंद करने जा रहे हैं ताकि दस्तावेज़ में किए गए परिवर्तन अब संशोधन के रूप में दिखाई न दें। यहाँ बताया गया है कि कैसे:

```csharp
doc.StopTrackRevisions();
```
## चरण 6: दस्तावेज़ को सहेजना

 टेक्स्ट इनपुट फॉर्म फ़ील्ड डालने के बाद, दस्तावेज़ को इच्छित स्थान पर सहेजें`Save`विधि। उचित फ़ाइल पथ प्रदान करना सुनिश्चित करें:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके संशोधन स्वीकार करने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में परिवर्तन स्वीकार करने के लिए पूरा स्रोत कोड यहां दिया गया है:


```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// पहले पैराग्राफ में पाठ जोड़ें, फिर दो और पैराग्राफ जोड़ें।
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//हमारे पास तीन पैराग्राफ हैं, जिनमें से किसी में भी किसी प्रकार का संशोधन दर्ज नहीं है
// यदि हम संशोधनों पर नज़र रखते हुए दस्तावेज़ में कोई सामग्री जोड़ते/हटाते हैं,
// वे दस्तावेज़ में उसी रूप में प्रदर्शित किये जायेंगे तथा उन्हें स्वीकार/अस्वीकार किया जा सकेगा।
doc.StartTrackRevisions("John Doe", DateTime.Now);

// यह अनुच्छेद एक संशोधन है और इसमें तदनुसार "IsInsertRevision" ध्वज सेट होगा।
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// दस्तावेज़ का पैराग्राफ़ संग्रह प्राप्त करें और एक पैराग्राफ़ हटाएँ.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// चूंकि हम संशोधनों पर नज़र रख रहे हैं, इसलिए अनुच्छेद अभी भी दस्तावेज़ में मौजूद है, इसमें "IsDeleteRevision" सेट होगा
// और जब तक हम सभी संशोधनों को स्वीकार या अस्वीकार नहीं कर देते, तब तक इसे माइक्रोसॉफ्ट वर्ड में संशोधन के रूप में प्रदर्शित किया जाएगा।
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// जब हम परिवर्तन स्वीकार कर लेते हैं तो हटाए गए संशोधन पैराग्राफ को हटा दिया जाता है।
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// संशोधनों की ट्रैकिंग रोकने से यह पाठ सामान्य पाठ के रूप में दिखाई देता है।
// दस्तावेज़ में परिवर्तन होने पर संशोधनों की गणना नहीं की जाती।
doc.StopTrackRevisions();

// दस्तावेज़ सहेजें.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि Aspose.Words for .NET की संशोधन स्वीकार करें सुविधा का उपयोग करके Word दस्तावेज़ में संशोधन कैसे स्वीकार करें। हमने दस्तावेज़ सामग्री जोड़ने और संपादित करने, संशोधनों को ट्रैक करने, संशोधित पैराग्राफ़ को हटाने, सभी परिवर्तनों को स्वीकार करने और संशोधनों को ट्रैक करना बंद करने के चरणों का पालन किया है। अब आप इस ज्ञान को Aspose.Words for .NET का उपयोग करके अपने स्वयं के Word दस्तावेज़ों में संशोधनों को प्रभावी ढंग से प्रबंधित करने के लिए लागू कर सकते हैं।

### पूछे जाने वाले प्रश्न

#### प्रश्न: मैं .NET के लिए Aspose.Words में संशोधन ट्रैकिंग कैसे सक्षम करूं?

#### समाधान 1:

 उत्तर: .NET के लिए Aspose.Words में संशोधन ट्रैकिंग सक्षम करने के लिए, का उपयोग करें`StartTrackRevisions` की विधि`Document` ऑब्जेक्ट चुनें और संशोधन ट्रैकिंग के लिए लेखक का नाम और आरंभ तिथि निर्दिष्ट करें।

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### समाधान 2:

 उत्तर: आप इसका उपयोग करके संशोधन ट्रैकिंग भी सक्षम कर सकते हैं`Document` कन्स्ट्रक्टर जो स्वीकार करता है`trackRevisions` और`author` पैरामीटर.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### प्रश्न: Aspose.Words for .NET के साथ किसी दस्तावेज़ में सभी परिवर्तनों को कैसे स्वीकार करें?

 उत्तर: का प्रयोग करें`AcceptAllRevisions` की विधि`Document` दस्तावेज़ में किए गए सभी परिवर्तनों को स्वीकार करने पर आपत्ति।

```csharp
doc.AcceptAllRevisions();
```

#### प्रश्न: मैं स्वीकृत संशोधनों के साथ संशोधित दस्तावेज़ को कैसे सहेज सकता हूँ?

 उपयोग`Save` की विधि`Document` संशोधित दस्तावेज़ को स्वीकृत संशोधनों के साथ सहेजने के लिए ऑब्जेक्ट का उपयोग करें। सही फ़ाइल पथ प्रदान करना सुनिश्चित करें।

```csharp
doc.Save("path/to/the/document.docx");
```

#### प्रश्न: मैं Aspose.Words for .NET में संशोधनों को ट्रैक करना कैसे रोकूँ?

 उत्तर: का प्रयोग करें`StopTrackRevisions` की विधि`Document` ट्रैकिंग संशोधनों को रोकने पर आपत्ति।

```csharp
doc.StopTrackRevisions();
```

#### प्रश्न: मैं Aspose.Words for .NET वाले दस्तावेज़ में संशोधित पैराग्राफ़ को कैसे हटाऊं?

 उत्तर: किसी दस्तावेज़ में संशोधित पैराग्राफ़ को हटाने के लिए, आप इसका उपयोग कर सकते हैं`Remove` पैराग्राफ़ संग्रह की विधि.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```