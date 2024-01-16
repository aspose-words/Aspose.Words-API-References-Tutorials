---
title: बाड़ कोड
linktitle: बाड़ कोड
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: Aspose.Words for .NET चरण-दर-चरण मार्गदर्शिका के साथ फ़ेंसिड कोड सुविधा का उपयोग करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-markdown/fenced-code/
---

इस उदाहरण में, हम आपको बताएंगे कि .NET के लिए Aspose.Words के साथ फ़ेंस्ड कोड सुविधा का उपयोग कैसे करें। फ़ेंस्ड कोड का उपयोग विशिष्ट स्वरूपण के साथ कोड के ब्लॉक का प्रतिनिधित्व करने के लिए किया जाता है।

## चरण 1: दस्तावेज़ जनरेटर का उपयोग करना

सबसे पहले, हम अपने दस्तावेज़ में सामग्री जोड़ने के लिए एक दस्तावेज़ जनरेटर का उपयोग करेंगे।

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## चरण 2: फ़ेंस कोड के लिए एक शैली जोड़ना

 हम इसका उपयोग करके फेंसिड कोड के लिए एक कस्टम शैली जोड़ेंगे`Styles.Add` की विधि`Document` वस्तु। इस उदाहरण में, हम फ़ेंस कोड के लिए "फ़ेंस कोड" नामक एक शैली बना रहे हैं।

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## चरण 3: बिना जानकारी के फ़ेंस कोड जोड़ना

अब हम "फ़ेंस्डकोड" कस्टम शैली का उपयोग करके बिना किसी सूचना स्ट्रिंग के एक फ़ेंस्ड कोड ब्लॉक जोड़ सकते हैं।

```csharp
builder.Writeln("This is an fenced code");
```

## चरण 4: जानकारी स्ट्रिंग के साथ फ़ेंस कोड जोड़ें

हम किसी अन्य कस्टम शैली का उपयोग करके जानकारी की एक स्ट्रिंग के साथ एक बाड़ कोड ब्लॉक भी जोड़ सकते हैं। इस उदाहरण में, हम C# कोड के एक ब्लॉक को दर्शाने के लिए "FencedCode.C#" नामक एक शैली बना रहे हैं।

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### .NET के लिए Aspose.Words का उपयोग करके फ़ेंस्ड कोड के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ में सामग्री जोड़ने के लिए दस्तावेज़ निर्माता का उपयोग करें।
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मार्कडाउन में सीमांकित कोड क्या है?

उ: मार्कडाउन में सीमांकित कोड एक स्वरूपण विधि है जिसका उपयोग मार्कडाउन दस्तावेज़ में कोड प्रदर्शित करने के लिए किया जाता है। इसमें विशिष्ट सीमांकक के साथ कोड तैयार करना शामिल है।

#### प्रश्न: मार्कडाउन में सीमांकित कोड के क्या लाभ हैं?

उत्तर: मार्कडाउन में सीमांकित कोड कोड पठनीयता में सुधार करता है और पाठकों के लिए इसे समझना आसान बनाता है। यह कुछ मार्कडाउन संपादकों में सिंटैक्स हाइलाइटिंग को संरक्षित करने की भी अनुमति देता है।

#### प्रश्न: मार्कडाउन में सीमांकित और इंडेंटेड कोड के बीच क्या अंतर है?

ए: सीमांकित कोड कोड को संलग्न करने के लिए विशिष्ट सीमांकक का उपयोग करता है, जबकि इंडेंटेड कोड में कोड की प्रत्येक पंक्ति को रिक्त स्थान या टैब के साथ इंडेंट करना शामिल होता है।

#### प्रश्न: क्या मार्कडाउन में सीमांकित कोड सभी मार्कडाउन संपादकों द्वारा समर्थित है?

उ: मार्कडाउन में सीमांकित कोड के लिए समर्थन मार्कडाउन संपादकों के बीच भिन्न हो सकता है। सुनिश्चित करने के लिए अपने प्रकाशक के विशिष्ट दस्तावेज़ की जाँच करें।

