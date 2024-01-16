---
title: वास्तविक आकार सीमा अंक प्राप्त करें
linktitle: वास्तविक आकार सीमा अंक प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में बिंदुओं (माप इकाई) में किसी आकृति की वास्तविक सीमा को पुनः प्राप्त करने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-shapes/get-actual-shape-bounds-points/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में बिंदुओं (माप इकाई) में किसी आकृति की वास्तविक सीमा को कैसे पुनः प्राप्त किया जाए। सीमाएँ दस्तावेज़ के भीतर आकृति के आकार और स्थिति का प्रतिनिधित्व करती हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, आपके पास निम्नलिखित होना चाहिए:

- .NET लाइब्रेरी के लिए Aspose.Words स्थापित।
- वर्ड दस्तावेजों के साथ सी# और वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: एक नया दस्तावेज़ और दस्तावेज़बिल्डर बनाएँ
 का एक नया उदाहरण बनाएं`Document` कक्षा और ए`DocumentBuilder` दस्तावेज़ के साथ काम करने पर आपत्ति।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: एक छवि आकार डालें
 उपयोग`InsertImage` की विधि`DocumentBuilder` दस्तावेज़ में एक छवि आकृति सम्मिलित करने के लिए ऑब्जेक्ट। एक पैरामीटर के रूप में छवि फ़ाइल का पथ प्रदान करें।

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## चरण 3: वास्तविक आकार सीमा बिंदु पुनर्प्राप्त करें
 आकृतियों तक पहुंचें`ShapeRenderer` का उपयोग`GetShapeRenderer` तरीका। फिर, का उपयोग करके आकृति की वास्तविक सीमाओं को बिंदुओं में पुनः प्राप्त करें`BoundsInPoints` संपत्ति।

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### .NET के लिए Aspose.Words का उपयोग करके वास्तविक आकार सीमा बिंदु प्राप्त करने के लिए उदाहरण स्रोत कोड 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ में बिंदुओं में किसी आकृति की वास्तविक सीमा को सफलतापूर्वक पुनः प्राप्त कर लिया है।