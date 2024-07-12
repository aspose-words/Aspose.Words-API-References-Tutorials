---
title: आकार संशोधन
linktitle: आकार संशोधन
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में आकृतियों को संशोधित करें।
type: docs
weight: 10
url: /hi/net/working-with-revisions/shape-revision/
---

इस चरण-दर-चरण मार्गदर्शिका में, हम आपको Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में आकृतियों में संशोधन करने का तरीका बताएँगे। हम आपको पूरा स्रोत कोड प्रदान करेंगे और आपको दिखाएंगे कि मार्कडाउन आउटपुट को कैसे प्रारूपित किया जाए।

## चरण 1: दस्तावेज़ बनाना और आकृतियाँ जोड़ना

पहला चरण एक नया दस्तावेज़ बनाना और उसमें आकृतियाँ जोड़ना है।

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## चरण 2: संशोधनों को ट्रैक करें और एक और आकृति जोड़ें

हम संशोधन ट्रैकिंग चालू करेंगे और एक और आकृति जोड़ेंगे.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## चरण 3: आकृति संग्रह प्राप्त करें और संशोधनों की जांच करें

हम दस्तावेज़ से आकृतियों का संग्रह प्राप्त करेंगे और प्रत्येक आकृति से जुड़े संशोधनों की जाँच करेंगे।

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## चरण 4: आकार परिवर्तन संशोधन की जाँच करना

हम आकार विस्थापन संशोधनों वाले एक मौजूदा दस्तावेज़ को लोड करने जा रहे हैं और संबंधित संशोधनों की जांच करेंगे।

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### .NET के लिए Aspose.Words का उपयोग करके आकृति संशोधन के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में आकृतियों में संशोधन करने के लिए पूर्ण स्रोत कोड यहां दिया गया है:

```csharp
Document doc = new Document();

//संशोधनों को ट्रैक किए बिना एक इनलाइन आकार सम्मिलित करें।
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// संशोधनों को ट्रैक करना प्रारंभ करें और फिर कोई अन्य आकृति डालें.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// दस्तावेज़ का आकार संग्रह प्राप्त करें जिसमें हमारे द्वारा जोड़े गए केवल दो आकार शामिल हैं।
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// पहली आकृति हटाएँ.
shapes[0].Remove();

// चूंकि हमने उस आकृति को तब हटा दिया था जब परिवर्तनों पर नज़र रखी जा रही थी, इसलिए आकृति को हटाए गए संशोधन के रूप में गिना जाता है।
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// और हमने परिवर्तनों को ट्रैक करते हुए एक अन्य आकृति भी सम्मिलित की, अतः वह आकृति सम्मिलित संशोधन के रूप में गिनी जाएगी।
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// दस्तावेज़ में एक आकृति है जिसे स्थानांतरित किया गया था, लेकिन आकृति स्थानांतरण संशोधन में उस आकृति के दो उदाहरण होंगे।
// एक आकृति अपने आगमन गंतव्य पर होगी और दूसरी आकृति अपने मूल स्थान पर होगी।
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// यह संशोधन की ओर कदम है, तथा इसके आगमन के गंतव्य पर आकार भी है।
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// यह संशोधन से आगे की चाल है, जो कि आकृति को उसके मूल स्थान पर ले जाना है।
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में आकृतियों में संशोधन कैसे करें। दस्तावेज़ बनाने, संशोधन ट्रैकिंग सक्षम करने, प्रत्येक आकृति से जुड़े संशोधनों की जाँच करने और आकृतियों को स्थानांतरित करने के लिए संशोधनों की जाँच करने के चरणों का पालन करके, हम संशोधनों को सफलतापूर्वक प्रबंधित करने में सक्षम थे। Aspose.Words for .NET Word दस्तावेज़ों में समीक्षाओं और फ़ॉर्म के साथ Words प्रोसेसिंग के लिए एक शक्तिशाली API प्रदान करता है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words for .NET में नया दस्तावेज़ कैसे बना सकता हूँ और आकृतियाँ कैसे जोड़ सकता हूँ?

उत्तर: Aspose.Words for .NET में नया दस्तावेज़ बनाने और आकृतियाँ जोड़ने के लिए, आप निम्न कोड का उपयोग कर सकते हैं। यहाँ हम दस्तावेज़ के पहले भाग में दो आकृतियाँ, एक घन और एक सूर्य जोड़ते हैं:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### प्रश्न: मैं .NET के लिए Aspose.Words में संशोधन ट्रैकिंग कैसे सक्षम करूं?

 उत्तर: Aspose.Words for .NET में संशोधन ट्रैकिंग सक्षम करने के लिए, आप इसका उपयोग कर सकते हैं`StartTrackRevisions` की विधि`Document` ऑब्जेक्ट. यह विधि संशोधन के लेखक का नाम पैरामीटर के रूप में लेती है:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### प्रश्न: मैं Aspose.Words for .NET दस्तावेज़ में प्रत्येक आकृति से जुड़े संशोधनों की जांच कैसे कर सकता हूं?

उत्तर: Aspose.Words for .NET दस्तावेज़ में प्रत्येक आकृति से जुड़े संशोधनों की जांच करने के लिए, आप दस्तावेज़ के आकृतियों का संग्रह प्राप्त कर सकते हैं।`GetChildNodes` विधि के साथ`NodeType.Shape` नोड प्रकार। फिर आप प्रत्येक आकृति तक पहुँच सकते हैं`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , और`IsMoveToRevision` आकृति के साथ किस प्रकार का संशोधन जुड़ा है, यह निर्धारित करने के लिए गुण:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### प्रश्न: मैं Aspose.Words for .NET दस्तावेज़ में आकृतियों के विस्थापन संशोधनों की जांच कैसे कर सकता हूं?

 उत्तर: Aspose.Words for .NET दस्तावेज़ में आकार विस्थापन संशोधनों की जाँच करने के लिए, आप एक मौजूदा दस्तावेज़ लोड कर सकते हैं जिसमें आकार विस्थापन संशोधन शामिल हैं। फिर आप प्रत्येक आकृति तक पहुँच सकते हैं`IsMoveFromRevision`और`IsMoveToRevision` यह निर्धारित करने के लिए कि क्या इसे स्थानांतरित किया जा रहा है और यदि हां, तो कहां से और कहां के लिए:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```