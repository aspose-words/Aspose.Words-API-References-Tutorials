---
title: समीक्षाएँ स्वीकार करें
linktitle: समीक्षाएँ स्वीकार करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में संशोधन स्वीकार करना सीखें
type: docs
weight: 10
url: /hi/net/working-with-revisions/accept-revisions/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words की एक्सेप्ट रिवीजन सुविधा का उपयोग करके किसी Word दस्तावेज़ में संशोधन स्वीकार करने के बारे में बताएंगे। स्रोत कोड को समझने और दस्तावेज़ में परिवर्तन स्वीकार करने के लिए नीचे दिए गए चरणों का पालन करें।

## चरण 1: दस्तावेज़ सामग्री जोड़ना और संपादित करना

इस उदाहरण में, हम एक दस्तावेज़ बना रहे हैं और सामग्री जोड़ रहे हैं। हम परिवर्तनों और संशोधनों को दर्शाने के लिए कई अनुच्छेदों का उपयोग करते हैं। ऐसे:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// पहले पैराग्राफ में टेक्स्ट जोड़ें, फिर दो और पैराग्राफ जोड़ें।
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## चरण 2: समीक्षाएँ ट्रैक करें और समीक्षाएँ जोड़ें

हम संशोधन ट्रैकिंग सक्षम करते हैं और दस्तावेज़ में एक संशोधन जोड़ते हैं। ऐसे:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// यह अनुच्छेद एक संशोधन है और इसमें संबंधित "IsInsertRevision" ध्वज सेट होगा।
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## चरण 3: एक पैराग्राफ हटाएं और संशोधन प्रबंधित करें

हम एक अनुच्छेद हटाते हैं और सहेजे गए संशोधनों की जाँच करते हैं। ऐसे:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// चूंकि हम संशोधनों पर नज़र रख रहे हैं, पैराग्राफ अभी भी दस्तावेज़ में मौजूद है, इसमें "IsDeleteRevision" ध्वज सेट होगा
// और Microsoft Word में एक समीक्षा के रूप में प्रदर्शित किया जाएगा, जब तक कि हम सभी समीक्षाओं को स्वीकार या अस्वीकार नहीं कर देते।
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## चरण 4: परिवर्तन स्वीकार करें

हम दस्तावेज़ में सभी परिवर्तन स्वीकार करते हैं. ऐसे:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## चरण 5: समीक्षाओं पर नज़र रखना बंद करें

हम संशोधनों को ट्रैक करना बंद करने जा रहे हैं ताकि दस्तावेज़ में परिवर्तन अब संशोधन के रूप में दिखाई न दें। ऐसे:

```csharp
doc.StopTrackRevisions();
```
## चरण 6: दस्तावेज़ सहेजना

 टेक्स्ट इनपुट फॉर्म फ़ील्ड डालने के बाद, दस्तावेज़ को वांछित स्थान पर सहेजें`Save` तरीका। उचित फ़ाइल पथ प्रदान करना सुनिश्चित करें:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके संशोधन स्वीकार करने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में परिवर्तन स्वीकार करने के लिए संपूर्ण स्रोत कोड यहां दिया गया है:


```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// पहले पैराग्राफ में टेक्स्ट जोड़ें, फिर दो और पैराग्राफ जोड़ें।
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//हमारे पास तीन पैराग्राफ हैं, जिनमें से कोई भी किसी भी प्रकार के संशोधन के रूप में पंजीकृत नहीं है
// यदि हम संशोधनों को ट्रैक करते समय दस्तावेज़ में कोई सामग्री जोड़ते/हटाते हैं,
// उन्हें दस्तावेज़ में इस रूप में प्रदर्शित किया जाएगा और उन्हें स्वीकार/अस्वीकार किया जा सकता है।
doc.StartTrackRevisions("John Doe", DateTime.Now);

// यह अनुच्छेद एक संशोधन है और इसमें "IsInsertRevision" ध्वज सेट के अनुसार होगा।
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// दस्तावेज़ का अनुच्छेद संग्रह प्राप्त करें और एक अनुच्छेद हटा दें।
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// चूँकि हम संशोधनों पर नज़र रख रहे हैं, पैराग्राफ अभी भी दस्तावेज़ में मौजूद है, इसमें "IsDeleteRevision" सेट होगा
// और Microsoft Word में एक संशोधन के रूप में प्रदर्शित किया जाएगा, जब तक कि हम सभी संशोधनों को स्वीकार या अस्वीकार नहीं कर देते।
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// एक बार जब हम परिवर्तन स्वीकार कर लेते हैं तो हटाया गया संशोधन पैराग्राफ हटा दिया जाता है।
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// संशोधनों की ट्रैकिंग रोकने से यह पाठ सामान्य पाठ के रूप में दिखाई देने लगता है।
// जब दस्तावेज़ बदला जाता है तो संशोधनों की गणना नहीं की जाती है।
doc.StopTrackRevisions();

// दस्तावेज़ सहेजें.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words के एक्सेप्ट रिविजन फीचर का उपयोग करके वर्ड डॉक्यूमेंट में संशोधन कैसे स्वीकार करें। हमने दस्तावेज़ सामग्री को जोड़ने और संपादित करने, संशोधनों को ट्रैक करने, एक संशोधित पैराग्राफ को हटाने, सभी परिवर्तनों को स्वीकार करने और ट्रैकिंग संशोधनों को रोकने के चरणों का पालन किया है। अब आप .NET के लिए Aspose.Words का उपयोग करके अपने स्वयं के Word दस्तावेज़ों में संशोधनों को प्रभावी ढंग से प्रबंधित करने के लिए इस ज्ञान को लागू कर सकते हैं।

### पूछे जाने वाले प्रश्न

#### प्रश्न: मैं .NET के लिए Aspose.Words में पुनरीक्षण ट्रैकिंग कैसे सक्षम करूं?

#### समाधान 1:

 उ: .NET के लिए Aspose.Words में पुनरीक्षण ट्रैकिंग सक्षम करने के लिए, का उपयोग करें`StartTrackRevisions` की विधि`Document` ऑब्जेक्ट करें और पुनरीक्षण ट्रैकिंग के लिए लेखक का नाम और आरंभ तिथि निर्दिष्ट करें।

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### समाधान 2:

 उ: आप इसका उपयोग करके पुनरीक्षण ट्रैकिंग भी सक्षम कर सकते हैं`Document` कंस्ट्रक्टर जो स्वीकार करता है`trackRevisions` और`author` पैरामीटर.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### प्रश्न: .NET के लिए Aspose.Words के साथ दस्तावेज़ में सभी परिवर्तनों को कैसे स्वीकार करें?

 ए: का प्रयोग करें`AcceptAllRevisions` की विधि`Document` दस्तावेज़ में किए गए सभी परिवर्तनों को स्वीकार करने पर आपत्ति।

```csharp
doc.AcceptAllRevisions();
```

#### प्रश्न: मैं स्वीकृत संशोधनों के साथ एक संशोधित दस्तावेज़ को कैसे सहेज सकता हूँ?

 उपयोग`Save` की विधि`Document` संशोधित दस्तावेज़ को स्वीकृत संशोधनों के साथ सहेजने के लिए ऑब्जेक्ट। सही फ़ाइल पथ प्रदान करना सुनिश्चित करें.

```csharp
doc.Save("path/to/the/document.docx");
```

#### प्रश्न: मैं .NET के लिए Aspose.Words में ट्रैकिंग संशोधनों को कैसे रोकूँ?

 ए: का प्रयोग करें`StopTrackRevisions` की विधि`Document` ट्रैकिंग संशोधनों को रोकने के लिए आपत्ति।

```csharp
doc.StopTrackRevisions();
```

#### प्रश्न: मैं .NET के लिए Aspose.Words वाले दस्तावेज़ में एक संशोधित अनुच्छेद को कैसे हटाऊं?

 उ: किसी दस्तावेज़ में संशोधित अनुच्छेद को हटाने के लिए, आप इसका उपयोग कर सकते हैं`Remove` अनुच्छेद संग्रह की विधि.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```