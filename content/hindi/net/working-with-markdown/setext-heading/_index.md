---
title: सेटेक्स्ट शीर्षक
linktitle: सेटेक्स्ट शीर्षक
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: Aspose.Words for .NET चरण-दर-चरण मार्गदर्शिका के साथ अपने दस्तावेज़ों को प्रारूपित करने के लिए Setext शीर्षकों का उपयोग करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-markdown/setext-heading/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ Setext Heading सुविधा का उपयोग करने का तरीका बताएँगे। Setext Heading, Markdown दस्तावेज़ों में शीर्षकों को फ़ॉर्मेट करने का एक वैकल्पिक तरीका है।

## चरण 1: दस्तावेज़ जनरेटर का उपयोग करना

सबसे पहले, हम अपने दस्तावेज़ में सामग्री जोड़ने के लिए दस्तावेज़ जनरेटर का उपयोग करेंगे।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## चरण 2: सेटेक्स्ट शीर्षक शैली का उपयोग करना

हम अपने दस्तावेज़ में स्तर 1 शीर्षक बनाने के लिए डिफ़ॉल्ट "शीर्षक 1" पैराग्राफ़ शैली का उपयोग करने जा रहे हैं।

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## चरण 3: शैलियाँ रीसेट करना

पैराग्राफों के बीच शैलियों के किसी भी अवांछित संयोजन से बचने के लिए हम पहले से लागू फ़ॉन्ट शैलियों को रीसेट करते हैं।

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## चरण 4: सेटेक्स्ट शीर्षक स्तर को अनुकूलित करना

हम मौजूदा शीर्षक शैलियों के आधार पर नई पैराग्राफ़ शैलियाँ जोड़कर Setext शीर्षक स्तरों को अनुकूलित कर सकते हैं। इस उदाहरण में, हम Setext प्रारूप में स्तर 1 शीर्षक का प्रतिनिधित्व करने के लिए "Heading 1" शैली के आधार पर "SetextHeading1" शैली बना रहे हैं।

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## चरण 5: दस्तावेज़ को सहेजना

अंततः, हम दस्तावेज़ को वांछित प्रारूप में सहेज सकते हैं।

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### .NET के लिए Aspose.Words के साथ Setext शीर्षकों के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ में सामग्री जोड़ने के लिए दस्तावेज़ बिल्डर का उपयोग करें.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// पैराग्राफों के बीच शैलियों को संयोजित न करने के लिए पिछले पैराग्राफ से शैलियों को रीसेट करें।
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// पैराग्राफों के बीच शैलियों को संयोजित न करने के लिए पिछले पैराग्राफ से शैलियों को रीसेट करें।
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// यदि आधार पैराग्राफ का शीर्षक स्तर 2 से अधिक है तो सेटेक्स शीर्षक स्तर 2 पर रीसेट हो जाएगा।
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: सेटेक्स्ट मार्कडाउन हेडर क्या है?

उत्तर: सेटेक्स्ट मार्कडाउन हेडर मार्कडाउन दस्तावेज़ में शीर्षक बनाने का एक वैकल्पिक तरीका है। यह शीर्षकों के विभिन्न स्तरों को इंगित करने के लिए अंडरस्कोर वर्णों (= या -) का उपयोग करता है।

#### प्रश्न: सेटेक्स्ट मार्कडाउन हेडर का उपयोग कैसे करें?

उत्तर: सेटेक्स्ट मार्कडाउन शीर्षकों का उपयोग करने के लिए, शीर्षक टेक्स्ट के नीचे अंडरस्कोर रखें। लेवल 1 हेडर के लिए बराबर चिह्न (=) और लेवल 2 हेडर के लिए हाइफ़न (-) का उपयोग करें।

#### प्रश्न: क्या सेटेक्स्ट मार्कडाउन हेडर का उपयोग करने में कोई सीमाएं हैं?

उत्तर: सेटेक्स्ट मार्कडाउन शीर्षकों में शीर्षक पदानुक्रम के संदर्भ में सीमाएं हैं और वे मानक मार्कडाउन शीर्षकों की तरह दृश्य रूप से अलग नहीं हैं।

#### प्रश्न: क्या मैं सेटेक्स्ट मार्कडाउन हेडर्स के स्वरूप को अनुकूलित कर सकता हूँ?

उत्तर: मानक मार्कडाउन में, सेटेक्स्ट मार्कडाउन हेडर की उपस्थिति को अनुकूलित करना संभव नहीं है। उनके पास उपयोग किए गए अंडरस्कोर वर्णों के आधार पर एक पूर्वनिर्धारित उपस्थिति होती है।

#### प्रश्न: क्या सेटेक्स्ट मार्कडाउन हेडर सभी मार्कडाउन संपादकों द्वारा समर्थित हैं?

उत्तर: सेटेक्स्ट मार्कडाउन हेडर के लिए समर्थन मार्कडाउन संपादकों के बीच भिन्न हो सकता है। सुनिश्चित करने के लिए अपने प्रकाशक के विशिष्ट दस्तावेज़ देखें।