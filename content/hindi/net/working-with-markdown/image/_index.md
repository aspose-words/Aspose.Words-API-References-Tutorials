---
title: छवि
linktitle: छवि
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ छवि सम्मिलित और अनुकूलित करने का तरीका चरण-दर-चरण मार्गदर्शिका जानें।
type: docs
weight: 10
url: /hi/net/working-with-markdown/image/
---

इस उदाहरण में, हम बताएंगे कि .NET के लिए Aspose.Words के साथ छवि सुविधा का उपयोग कैसे करें। चित्र आपको दस्तावेज़ में चित्रण और ग्राफ़िक्स सम्मिलित करने की अनुमति देते हैं।

## चरण 1: दस्तावेज़ जनरेटर का उपयोग करना

सबसे पहले, हम अपने दस्तावेज़ में सामग्री जोड़ने के लिए दस्तावेज़ जनरेटर का उपयोग करेंगे।

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## चरण 2: छवि सम्मिलित करना

 हम इसका उपयोग करके एक छवि सम्मिलित कर सकते हैं`Shape` वर्ग और छवि के प्रकार को निर्दिष्ट करना, यहाँ`ShapeType.Image` . हमने छवि का रैप प्रकार भी सेट किया है`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## चरण 3: छवि अनुकूलन

 हम छवि का पूरा पथ निर्दिष्ट करके उसे अनुकूलित करते हैं, उदाहरण के लिए`"/attachment/1456/pic001.png"`, और छवि में एक शीर्षक जोड़ना।

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### .NET के लिए Aspose.Words के साथ छवियों के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ में सामग्री जोड़ने के लिए दस्तावेज़ बिल्डर का उपयोग करें.
DocumentBuilder builder = new DocumentBuilder();

// चित्र डालें।
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

बधाई हो! अब आप सीख चुके हैं कि .NET के लिए Aspose.Words के साथ चित्र सुविधा का उपयोग कैसे करें।


### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं स्थानीय फ़ाइल से Aspose.Words में छवि कैसे सम्मिलित कर सकता हूँ?

 उत्तर: स्थानीय फ़ाइल से Aspose.Words में छवि सम्मिलित करने के लिए, आप इसका उपयोग कर सकते हैं`Shape` वर्ग और`InsertImage` तरीका।

#### प्रश्न: क्या मैं Aspose.Words में URL से कोई छवि सम्मिलित कर सकता हूँ?

 उत्तर: हां, आप Aspose.Words में URL से कोई छवि डाल सकते हैं। आप उसी का उपयोग कर सकते हैं`InsertImage`विधि का उपयोग करें और स्थानीय फ़ाइल पथ के बजाय छवि URL निर्दिष्ट करें।

#### प्रश्न: मैं Aspose.Words में किसी छवि का आकार कैसे बदल सकता हूँ?

 A: Aspose.Words में किसी छवि का आकार बदलने के लिए, आप इसका उपयोग कर सकते हैं`Width` और`Height` के गुण`Shape` वस्तु।

#### प्रश्न: क्या मैं Aspose.Words में छवियों पर फ़िल्टर लागू कर सकता हूँ?

 उत्तर: हाँ, आप Aspose.Words में छवियों पर फ़िल्टर लागू कर सकते हैं। उदाहरण के लिए, आप किसी छवि पर ब्लर फ़िल्टर लागू कर सकते हैं`ApplyGaussianBlur` की विधि`Shape` वस्तु।

#### प्रश्न: मैं Aspose.Words में एक छवि को दूसरे से कैसे बदल सकता हूँ?

 A: Aspose.Words में एक छवि को दूसरे से बदलने के लिए, आप इसका उपयोग कर सकते हैं`Replace` की विधि`Shape` क्लास. यह विधि पैरामीटर के रूप में लेती है`Shape` छवि की वस्तु जिसे प्रतिस्थापित किया जाना है और`Shape` नई छवि की वस्तु.