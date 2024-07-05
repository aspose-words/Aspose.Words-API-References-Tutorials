---
title: इनलाइन कोड
linktitle: इनलाइन कोड
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ कोड को इनलाइन करने का तरीका चरण-दर-चरण मार्गदर्शिका से सीखें।
type: docs
weight: 10
url: /hi/net/working-with-markdown/inline-code/
---

इस उदाहरण में, हम आपको Aspose.Words for .NET के साथ इनलाइन कोड सुविधा का उपयोग करने का तरीका बताएँगे। इनलाइन कोड का उपयोग पैराग्राफ़ के अंदर कोड के टुकड़ों को विज़ुअली दिखाने के लिए किया जाता है।

## चरण 1: दस्तावेज़ जनरेटर का उपयोग करना

सबसे पहले, हम अपने दस्तावेज़ में सामग्री जोड़ने के लिए दस्तावेज़ जनरेटर का उपयोग करेंगे।

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## चरण 2: इनलाइन कोड के लिए स्टाइलिंग जोड़ें

 हम इनलाइन कोड के लिए एक कस्टम स्टाइल जोड़ेंगे`Styles.Add` की विधि`Document` इस उदाहरण में, हम डिफ़ॉल्ट बैकटिक के साथ इनलाइन कोड के लिए "इनलाइनकोड" नामक एक शैली बना रहे हैं।

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## चरण 3: इनलाइन कोड जोड़ें

अब हम "इनलाइनकोड" कस्टम स्टाइल का उपयोग करके इनलाइन कोड जोड़ सकते हैं। इस उदाहरण में, हम बैकटिक्स की अलग-अलग संख्या वाले टेक्स्ट के दो टुकड़े जोड़ते हैं।

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### .NET के लिए Aspose.Words के साथ इनलाइन कोड के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ में सामग्री जोड़ने के लिए दस्तावेज़ बिल्डर का उपयोग करें.
DocumentBuilder builder = new DocumentBuilder();

// यदि बैकटिक्स की संख्या छूट गई है, तो डिफ़ॉल्ट रूप से एक बैकटिक का उपयोग किया जाएगा।
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// इसमें 3 बैकटिक्स होंगे।
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

बधाई हो! अब आपने सीख लिया है कि .NET के लिए Aspose.Words के साथ इनलाइन कोड कार्यक्षमता का उपयोग कैसे करें।


### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words में इनलाइन कोड का उपयोग कैसे कर सकता हूं?

 उत्तर: Aspose.Words में इनलाइन कोड का उपयोग करने के लिए, आप इनलाइन कोड के रूप में स्वरूपित किए जाने वाले टेक्स्ट को घेरने के लिए उपयुक्त टैग का उपयोग कर सकते हैं। उदाहरण के लिए, आप इसका उपयोग कर सकते हैं`<code>` या`<kbd>` टैग का उपयोग पाठ को चारों ओर से घेरने के लिए किया जाता है, ताकि उसे इनलाइन कोड के रूप में स्वरूपित किया जा सके।

#### प्रश्न: क्या Aspose.Words में इनलाइन कोड फ़ॉन्ट या रंग निर्दिष्ट करना संभव है?

 उत्तर: हाँ, आप Aspose.Words में इनलाइन कोड का फ़ॉन्ट या रंग निर्दिष्ट कर सकते हैं। आप इसका उपयोग कर सकते हैं`Font.Name` और`Font.Color` के गुण`Run` इनलाइन कोड का फ़ॉन्ट और रंग सेट करने के लिए ऑब्जेक्ट। उदाहरण के लिए, आप उपयोग कर सकते हैं`run.Font.Name = "Courier New"` इनलाइन कोड के लिए फ़ॉन्ट निर्दिष्ट करने के लिए और`run.Font.Color = Color.Blue`रंग निर्दिष्ट करने के लिए.

#### प्रश्न: क्या मैं अन्य पाठ तत्वों वाले पैराग्राफ में इनलाइन कोड का उपयोग कर सकता हूँ?

 उत्तर: हां, आप अन्य टेक्स्ट तत्वों वाले पैराग्राफ में इनलाइन कोड का उपयोग कर सकते हैं। आप कई टेक्स्ट तत्व बना सकते हैं`Run` पैराग्राफ के अलग-अलग हिस्सों को दर्शाने के लिए ऑब्जेक्ट का उपयोग करें, फिर इनलाइन कोड टैग का उपयोग करके केवल विशिष्ट भागों को इनलाइन कोड के रूप में फ़ॉर्मेट करें। फिर आप उन्हें पैराग्राफ में जोड़ सकते हैं`Paragraph.AppendChild(run)` तरीका।