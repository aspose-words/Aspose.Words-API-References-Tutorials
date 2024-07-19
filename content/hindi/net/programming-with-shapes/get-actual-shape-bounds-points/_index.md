---
title: वास्तविक आकार सीमा अंक प्राप्त करें
linktitle: वास्तविक आकार सीमा अंक प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में किसी आकृति की वास्तविक सीमाओं को बिंदुओं (माप इकाई) में पुनर्प्राप्त करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-shapes/get-actual-shape-bounds-points/
---

यह ट्यूटोरियल बताता है कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में किसी आकृति की वास्तविक सीमा को बिंदुओं (मापन इकाई) में कैसे प्राप्त किया जाए। सीमाएँ दस्तावेज़ के भीतर आकृति के आकार और स्थिति को दर्शाती हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए आपके पास निम्नलिखित चीजें होनी चाहिए:

- Aspose.Words for .NET लाइब्रेरी स्थापित की गई।
- C# और वर्ड दस्तावेजों के साथ वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: नया दस्तावेज़ और दस्तावेज़बिल्डर बनाएँ
 एक नया उदाहरण बनाएँ`Document` कक्षा और एक`DocumentBuilder` दस्तावेज़ के साथ काम करने पर आपत्ति।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: एक छवि आकार डालें
 उपयोग`InsertImage` की विधि`DocumentBuilder`दस्तावेज़ में छवि आकार सम्मिलित करने के लिए ऑब्जेक्ट। पैरामीटर के रूप में छवि फ़ाइल का पथ प्रदान करें।

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## चरण 3: वास्तविक आकार सीमा बिंदु पुनः प्राप्त करें
 आकृति तक पहुंचें`ShapeRenderer` का उपयोग`GetShapeRenderer` विधि। फिर, आकृति की वास्तविक सीमाओं को बिंदुओं में पुनः प्राप्त करें`BoundsInPoints` संपत्ति।

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

बस! आपने Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ में बिंदुओं में आकृति की वास्तविक सीमाओं को सफलतापूर्वक प्राप्त कर लिया है।