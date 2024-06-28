---
title: आकार संशोधन
linktitle: आकार संशोधन
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में आकृतियों को संशोधित करें।
type: docs
weight: 10
url: /hi/net/working-with-revisions/shape-revision/
---

इस चरण-दर-चरण मार्गदर्शिका में, हम आपको बताएंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में आकृतियों में संशोधन कैसे करें। हम आपको संपूर्ण स्रोत कोड प्रदान करेंगे और आपको दिखाएंगे कि मार्कडाउन आउटपुट को कैसे प्रारूपित किया जाए।

## चरण 1: दस्तावेज़ बनाना और आकृतियाँ जोड़ना

पहला कदम एक नया दस्तावेज़ बनाना और आकृतियाँ जोड़ना है।

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## चरण 2: संशोधनों को ट्रैक करें और दूसरा आकार जोड़ें

हम पुनरीक्षण ट्रैकिंग चालू करेंगे और एक अन्य आकृति जोड़ेंगे।

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## चरण 3: आकृति संग्रह प्राप्त करें और संशोधनों की जाँच करें।

हम दस्तावेज़ से आकृतियों का संग्रह प्राप्त करेंगे और प्रत्येक आकृति से जुड़े संशोधनों की जाँच करेंगे।

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## चरण 4: आकार परिवर्तन संशोधनों की जाँच करना

हम आकार विस्थापन संशोधन वाले मौजूदा दस्तावेज़ को लोड करने जा रहे हैं और संबंधित संशोधनों की जांच करेंगे।

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### .NET के लिए Aspose.Words का उपयोग करके आकार संशोधन के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में आकृतियों में संशोधन करने के लिए संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp
Document doc = new Document();

//संशोधनों को ट्रैक किए बिना एक इनलाइन आकृति सम्मिलित करें।
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// संशोधनों को ट्रैक करना शुरू करें और फिर दूसरी आकृति डालें।
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// दस्तावेज़ का आकार संग्रह प्राप्त करें जिसमें हमारे द्वारा जोड़े गए केवल दो आकार शामिल हैं।
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// पहला आकार हटाएँ.
shapes[0].Remove();

// चूँकि परिवर्तनों को ट्रैक करते समय हमने उस आकृति को हटा दिया था, आकृति को हटाए गए संशोधन के रूप में गिना जाता है।
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// और हमने परिवर्तनों को ट्रैक करते समय एक और आकार डाला, ताकि वह आकार सम्मिलित संशोधन के रूप में गिना जाएगा।
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// दस्तावेज़ में एक आकृति है जिसे स्थानांतरित किया गया था, लेकिन आकृति स्थानांतरण संशोधनों में उस आकृति के दो उदाहरण होंगे।
// एक आकृति अपने आगमन गंतव्य पर होगी और दूसरी आकृति अपने मूल स्थान पर होगी।
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// यह संशोधन की ओर कदम है, इसके आगमन गंतव्य पर आकार भी है।
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// यह पुनरीक्षण से एक कदम है, जो अपने मूल स्थान पर आकार है।
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में आकृतियों में संशोधन कैसे करें। दस्तावेज़ बनाने के चरणों का पालन करके, संशोधन ट्रैकिंग को सक्षम करके, प्रत्येक आकृति से जुड़े संशोधनों की जाँच करके, और आकृतियों को स्थानांतरित करने के लिए संशोधनों की जाँच करके, हम संशोधनों को सफलतापूर्वक प्रबंधित करने में सक्षम थे। .NET के लिए Aspose.Words Word दस्तावेज़ों में समीक्षाओं और प्रपत्रों के साथ Words प्रोसेसिंग के लिए एक शक्तिशाली API प्रदान करता है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं एक नया दस्तावेज़ कैसे बना सकता हूँ और .NET के लिए Aspose.Words में आकृतियाँ कैसे जोड़ सकता हूँ?

उ: एक नया दस्तावेज़ बनाने और .NET के लिए Aspose.Words में आकृतियाँ जोड़ने के लिए, आप निम्नलिखित कोड का उपयोग कर सकते हैं। यहां हम दस्तावेज़ के पहले खंड में दो आकृतियाँ, एक घन और एक सूर्य जोड़ते हैं:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### प्रश्न: मैं .NET के लिए Aspose.Words में पुनरीक्षण ट्रैकिंग कैसे सक्षम करूं?

 उ: .NET के लिए Aspose.Words में पुनरीक्षण ट्रैकिंग सक्षम करने के लिए, आप इसका उपयोग कर सकते हैं`StartTrackRevisions` की विधि`Document` वस्तु। यह विधि संशोधन के लेखक का नाम एक पैरामीटर के रूप में लेती है:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### प्रश्न: मैं .NET दस्तावेज़ के लिए Aspose.Words में प्रत्येक आकृति से जुड़े संशोधनों की जांच कैसे कर सकता हूं?

उ: .NET दस्तावेज़ के लिए Aspose.Words में प्रत्येक आकृति से जुड़े संशोधनों की जांच करने के लिए, आप दस्तावेज़ के आकृतियों का संग्रह प्राप्त कर सकते हैं`GetChildNodes` विधि के साथ`NodeType.Shape` नोड प्रकार. फिर आप प्रत्येक आकृति तक पहुंच सकते हैं`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , और`IsMoveToRevision` यह निर्धारित करने के लिए गुण कि आकार के साथ किस प्रकार का संशोधन जुड़ा हुआ है:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### प्रश्न: मैं Aspose.Words for .NET दस्तावेज़ में आकृतियों के विस्थापन संशोधन की जांच कैसे कर सकता हूं?

 उ: .NET दस्तावेज़ के लिए Aspose.Words में आकार विस्थापन संशोधनों की जांच करने के लिए, आप एक मौजूदा दस्तावेज़ लोड कर सकते हैं जिसमें आकार विस्थापन संशोधन शामिल हैं। फिर आप प्रत्येक आकृति तक पहुंच सकते हैं`IsMoveFromRevision` और`IsMoveToRevision` यह निर्धारित करने के लिए गुण कि क्या इसे स्थानांतरित किया जा रहा है और यदि हां, तो कहां से और कहां तक:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```