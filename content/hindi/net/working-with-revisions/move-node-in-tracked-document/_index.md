---
title: ट्रैक किए गए दस्तावेज़ में नोड ले जाएँ
linktitle: ट्रैक किए गए दस्तावेज़ में नोड ले जाएँ
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ ट्रैक किए गए दस्तावेज़ में नोड्स को स्थानांतरित करें।
type: docs
weight: 10
url: /hi/net/working-with-revisions/move-node-in-tracked-document/
---

इस चरण-दर-चरण मार्गदर्शिका में, हम आपको Aspose.Words for .NET का उपयोग करके ट्रैक किए गए Word दस्तावेज़ में नोड को स्थानांतरित करने का तरीका बताएंगे। हम आपको पूरा स्रोत कोड प्रदान करेंगे और आपको मार्कडाउन आउटपुट को फ़ॉर्मेट करने का तरीका दिखाएंगे।

## चरण 1: दस्तावेज़ बनाना

पहला चरण एक नया दस्तावेज़ बनाना और पैराग्राफ़ जोड़ना है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## चरण 2: संशोधनों पर नज़र रखें

हम दस्तावेज़ में संशोधन ट्रैकिंग सक्षम करने जा रहे हैं।

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## चरण 3: नोड को स्थानांतरित करें

हम संशोधन तैयार करते समय नोड (पैराग्राफ) को एक स्थान से दूसरे स्थान पर ले जाएंगे।

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## चरण 4: समीक्षाओं पर नज़र रखना बंद करें

हम दस्तावेज़ में संशोधनों पर नज़र रखना बंद कर देंगे.

```csharp
doc.StopTrackRevisions();
```

## चरण 5: दस्तावेज़ को सहेजना

 टेक्स्ट इनपुट फॉर्म फ़ील्ड डालने के बाद, दस्तावेज़ को इच्छित स्थान पर सहेजें`Save`विधि। उचित फ़ाइल पथ प्रदान करना सुनिश्चित करें:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### .NET के लिए Aspose.Words का उपयोग करके ट्रैक किए गए दस्तावेज़ में नोड ले जाने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके ट्रैक किए गए दस्तावेज़ में नोड को स्थानांतरित करने के लिए पूर्ण स्रोत कोड यहां दिया गया है:


```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// संशोधनों पर नज़र रखना शुरू करें.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// किसी नोड को एक स्थान से दूसरे स्थान पर ले जाते समय संशोधन उत्पन्न करें।
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// संशोधनों पर नज़र रखने की प्रक्रिया बंद करें.
doc.StopTrackRevisions();

// मूव-फ्रॉम श्रेणी में 3 अतिरिक्त पैराग्राफ हैं।
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि Aspose.Words for .NET का उपयोग करके ट्रैक किए गए Word दस्तावेज़ में नोड को कैसे स्थानांतरित किया जाए। दस्तावेज़ बनाने, संशोधन ट्रैकिंग सक्षम करने, नोड को स्थानांतरित करने और संशोधन ट्रैकिंग को रोकने के चरणों का पालन करके, हम इस हेरफेर को सफलतापूर्वक करने में सक्षम थे। Aspose.Words for .NET Word दस्तावेज़ों के साथ Words प्रोसेसिंग के लिए एक शक्तिशाली उपकरण है और संशोधनों के प्रबंधन के लिए उन्नत सुविधाएँ प्रदान करता है। अब आप इस ज्ञान का उपयोग Aspose.Words for .NET का उपयोग करके संशोधनों को ट्रैक करते हुए अपने स्वयं के Word दस्तावेज़ों में नोड्स को स्थानांतरित करने के लिए कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words for .NET दस्तावेज़ में संशोधन ट्रैकिंग कैसे सक्षम कर सकता हूं?

 A: किसी Aspose.Words for .NET दस्तावेज़ में संशोधन ट्रैकिंग सक्षम करने के लिए, आप इसका उपयोग कर सकते हैं`StartTrackRevisions` की विधि`Document` ऑब्जेक्ट। यह विधि संशोधन के लेखक का नाम और संशोधनों के अनुवर्ती की आरंभ तिथि को पैरामीटर के रूप में लेती है।

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### प्रश्न: मैं संशोधन उत्पन्न किए बिना ट्रैक किए गए दस्तावेज़ में नोड को कैसे स्थानांतरित कर सकता हूं?

 उत्तर: यदि आप संशोधन उत्पन्न किए बिना ट्रैक किए गए दस्तावेज़ में नोड को स्थानांतरित करना चाहते हैं, तो आप इसका उपयोग कर सकते हैं`Remove` और`InsertAfter` या`InsertBefore` के तरीके`Node` ऑब्जेक्ट. उदाहरण के लिए, एक पैराग्राफ़ को दूसरे पैराग्राफ़ के बाद ले जाने के लिए, आप निम्न कोड का उपयोग कर सकते हैं:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### प्रश्न: मैं Aspose.Words for .NET दस्तावेज़ में संशोधन ट्रैकिंग कैसे रोक सकता हूँ?

 A: किसी Aspose.Words for .NET दस्तावेज़ में संशोधनों को ट्रैक करना बंद करने के लिए, आप इसका उपयोग कर सकते हैं`StopTrackRevisions` की विधि`Document` वस्तु।

```csharp
doc.StopTrackRevisions();
```