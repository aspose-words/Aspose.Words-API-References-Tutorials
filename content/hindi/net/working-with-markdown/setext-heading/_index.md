---
title: सेटेक्स हेडिंग
linktitle: सेटेक्स हेडिंग
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: Aspose.Words for .NET चरण-दर-चरण मार्गदर्शिका के साथ अपने दस्तावेज़ों को प्रारूपित करने के लिए Settext शीर्षकों का उपयोग करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-markdown/setext-heading/
---

इस ट्यूटोरियल में, हम आपको बताएंगे कि .NET के लिए Aspose.Words के साथ सेटेक्स्ट हेडिंग सुविधा का उपयोग कैसे करें। सेटेक्स्ट हेडिंग मार्कडाउन दस्तावेज़ों में शीर्षकों को फ़ॉर्मेट करने का एक वैकल्पिक तरीका है।

## चरण 1: दस्तावेज़ जनरेटर का उपयोग करना

सबसे पहले, हम अपने दस्तावेज़ में सामग्री जोड़ने के लिए एक दस्तावेज़ जनरेटर का उपयोग करेंगे।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## चरण 2: सेटेक्स्ट शीर्षक शैली का उपयोग करना

हम अपने दस्तावेज़ में लेवल 1 शीर्षक बनाने के लिए डिफ़ॉल्ट "शीर्षक 1" पैराग्राफ़ शैली का उपयोग करने जा रहे हैं।

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## चरण 3: शैलियाँ रीसेट करना

अनुच्छेदों के बीच शैलियों के किसी भी अवांछित संयोजन से बचने के लिए हम पहले से लागू फ़ॉन्ट शैलियों को रीसेट करते हैं।

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## चरण 4: सेटटेक्स्ट शीर्षक स्तरों को अनुकूलित करना

हम मौजूदा शीर्षक शैलियों के आधार पर नई पैराग्राफ शैलियों को जोड़कर सेटेक्स्ट शीर्षक स्तरों को अनुकूलित कर सकते हैं। इस उदाहरण में, हम Settext प्रारूप में स्तर 1 शीर्षक का प्रतिनिधित्व करने के लिए "Heading 1" शैली के आधार पर एक "SetextHeading1" शैली बना रहे हैं।

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## चरण 5: दस्तावेज़ सहेजना

अंत में, हम दस्तावेज़ को वांछित प्रारूप में सहेज सकते हैं।

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### .NET के लिए Aspose.Words के साथ Settext शीर्षकों के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ में सामग्री जोड़ने के लिए दस्तावेज़ निर्माता का उपयोग करें।
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

उ: सेटेक्स्ट मार्कडाउन हेडर मार्कडाउन दस्तावेज़ में शीर्षक बनाने का एक वैकल्पिक तरीका है। यह शीर्षकों के विभिन्न स्तरों को इंगित करने के लिए अंडरस्कोर वर्ण (= या -) का उपयोग करता है।

#### प्रश्न: सेटेक्स्ट मार्कडाउन हेडर का उपयोग कैसे करें?

उ: सेटेक्स्ट मार्कडाउन शीर्षकों का उपयोग करने के लिए, शीर्षक टेक्स्ट के नीचे अंडरस्कोर लगाएं। लेवल 1 हेडर के लिए समान चिह्न (=) और लेवल 2 हेडर के लिए हाइफ़न (-) का उपयोग करें।

#### प्रश्न: क्या सेटेक्स्ट मार्कडाउन हेडर का उपयोग करने में कोई सीमाएँ हैं?

उत्तर: सेटेक्स्ट मार्कडाउन शीर्षकों में शीर्षक पदानुक्रम के संदर्भ में सीमाएँ हैं और वे मानक मार्कडाउन शीर्षकों की तरह दृष्टिगत रूप से भिन्न नहीं हैं।

#### प्रश्न: क्या मैं सेटेक्स्ट मार्कडाउन हेडर के स्वरूप को अनुकूलित कर सकता हूँ?

उ: मानक मार्कडाउन में, सेटटेक्स्ट मार्कडाउन हेडर की उपस्थिति को अनुकूलित करना संभव नहीं है। उपयोग किए गए अंडरस्कोर वर्णों के आधार पर उनकी पूर्वनिर्धारित उपस्थिति होती है।

#### प्रश्न: क्या सेटेक्स्ट मार्कडाउन हेडर सभी मार्कडाउन संपादकों द्वारा समर्थित हैं?

उ: सेटेक्स्ट मार्कडाउन हेडर के लिए समर्थन मार्कडाउन संपादकों के बीच भिन्न हो सकता है। सुनिश्चित करने के लिए अपने प्रकाशक के विशिष्ट दस्तावेज़ की जाँच करें।