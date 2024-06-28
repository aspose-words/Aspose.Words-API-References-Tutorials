---
title: छवि
linktitle: छवि
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET चरण-दर-चरण मार्गदर्शिका के लिए Aspose.Words के साथ छवि सम्मिलित करना और अनुकूलित करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-markdown/image/
---

इस उदाहरण में, हम बताएंगे कि .NET के लिए Aspose.Words के साथ छवि सुविधा का उपयोग कैसे करें। चित्र आपको किसी दस्तावेज़ में चित्र और ग्राफ़िक्स सम्मिलित करने की अनुमति देते हैं।

## चरण 1: दस्तावेज़ जनरेटर का उपयोग करना

सबसे पहले, हम अपने दस्तावेज़ में सामग्री जोड़ने के लिए एक दस्तावेज़ जनरेटर का उपयोग करेंगे।

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## चरण 2: एक छवि सम्मिलित करना

 हम इसका उपयोग करके एक छवि सम्मिलित कर सकते हैं`Shape` क्लास और यहां छवि का प्रकार निर्दिष्ट करना`ShapeType.Image` . हम छवि का रैप प्रकार भी सेट करते हैं`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## चरण 3: छवि अनुकूलन

 उदाहरण के लिए, हम छवि का पूरा पथ निर्दिष्ट करके उसे अनुकूलित करते हैं`"/attachment/1456/pic001.png"`, और छवि में एक शीर्षक जोड़ना।

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### .NET के लिए Aspose.Words वाली छवियों के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ में सामग्री जोड़ने के लिए दस्तावेज़ निर्माता का उपयोग करें।
DocumentBuilder builder = new DocumentBuilder();

// चित्र डालें।
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

बधाई हो! अब आपने सीख लिया है कि .NET के लिए Aspose.Words के साथ इमेज फीचर का उपयोग कैसे करें।


### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं स्थानीय फ़ाइल से Aspose.Words में एक छवि कैसे सम्मिलित कर सकता हूँ?

 उ: किसी स्थानीय फ़ाइल से Aspose.Words में एक छवि सम्मिलित करने के लिए, आप इसका उपयोग कर सकते हैं`Shape` कक्षा और`InsertImage` तरीका।

#### प्रश्न: क्या मैं Aspose.Words में किसी URL से एक छवि सम्मिलित कर सकता हूँ?

 उत्तर: हाँ, आप Aspose.Words में किसी URL से एक छवि सम्मिलित कर सकते हैं। आप वही प्रयोग कर सकते हैं`InsertImage`विधि और स्थानीय फ़ाइल पथ के बजाय छवि URL निर्दिष्ट करें।

#### प्रश्न: मैं Aspose.Words में किसी छवि का आकार कैसे बदल सकता हूँ?

 उत्तर: Aspose.Words में किसी छवि का आकार बदलने के लिए, आप इसका उपयोग कर सकते हैं`Width` और`Height` के गुण`Shape` वस्तु।

#### प्रश्न: क्या मैं Aspose.Words में छवियों पर फ़िल्टर लागू कर सकता हूँ?

 उत्तर: हाँ, आप Aspose.Words में छवियों पर फ़िल्टर लागू कर सकते हैं। उदाहरण के लिए, आप इसका उपयोग करके किसी छवि पर धुंधला फ़िल्टर लागू कर सकते हैं`ApplyGaussianBlur` की विधि`Shape` वस्तु।

#### प्रश्न: मैं Aspose.Words में एक छवि को दूसरी छवि से कैसे बदल सकता हूँ?

 उत्तर: Aspose.Words में एक छवि को दूसरी छवि से बदलने के लिए, आप इसका उपयोग कर सकते हैं`Replace` की विधि`Shape` कक्षा। यह विधि पैरामीटर के रूप में लेती है`Shape` प्रतिस्थापित की जाने वाली छवि का ऑब्जेक्ट और`Shape` नई छवि का ऑब्जेक्ट.