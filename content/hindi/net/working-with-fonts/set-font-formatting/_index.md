---
title: फ़ॉन्ट फ़ॉर्मेटिंग सेट करें
linktitle: फ़ॉन्ट फ़ॉर्मेटिंग सेट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में फ़ॉन्ट फ़ॉर्मेटिंग सेट करना सीखें और आकर्षक दस्तावेज़ बनाएं।
type: docs
weight: 10
url: /hi/net/working-with-fonts/set-font-formatting/
---
इस ट्यूटोरियल में, हम आपको दिखाएंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में फ़ॉन्ट फ़ॉर्मेटिंग कैसे सेट करें। आप सीखेंगे कि बोल्ड, रंग, इटैलिक, फ़ॉन्ट, आकार, स्पेसिंग और अंडरलाइनिंग जैसी शैलियों को कैसे लागू किया जाए।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित चीज़ें हैं:
- C# प्रोग्रामिंग भाषा का कार्यसाधक ज्ञान
- आपके प्रोजेक्ट में .NET के लिए Aspose.Words लाइब्रेरी स्थापित है

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें
 अपने Word दस्तावेज़ के स्थान पर निर्देशिका पथ सेट करके प्रारंभ करें। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उचित पथ के साथ कोड में।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ बनाएं और प्रारूपित करें
 का एक उदाहरण बनाएं`Document` कक्षा और`DocumentBuilder` दस्तावेज़ बनाने के लिए क्लास। उपयोग`Font` की संपत्ति`DocumentBuilder` फ़ॉन्ट स्वरूपण गुणों तक पहुँचने के लिए।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font. Bold = true;
font.Color = Color.DarkBlue;
font. Italic = true;
font.Name = "Arial";
font.Size = 24;
font. Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nicely formatted string.");
```

## चरण 3: दस्तावेज़ सहेजें
 उपयोग`Save` फ़ॉन्ट स्वरूपण लागू करके दस्तावेज़ को सहेजने की विधि। प्रतिस्थापित करें`"WorkingWithFonts.SetFontFormatting.docx"` वांछित फ़ाइल नाम के साथ.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके फ़ॉन्ट फ़ॉर्मेटिंग सेट करने के लिए नमूना स्रोत कोड 
```csharp

// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Bold = true;
font.Color = Color.DarkBlue;
font.Italic = true;
font.Name = "Arial";
font.Size = 24;
font.Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nice formatted string.");
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");

```

## निष्कर्ष
बधाई हो! अब आप जानते हैं कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में फ़ॉन्ट फ़ॉर्मेटिंग कैसे सेट करें। आप अधिक फ़ॉन्ट फ़ॉर्मेटिंग विकल्प तलाश सकते हैं और वैयक्तिकृत और आकर्षक वर्ड दस्तावेज़ बना सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में किसी फ़ॉन्ट पर बोल्ड स्टाइल कैसे लागू कर सकता हूं?

उ: Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में फ़ॉन्ट पर बोल्ड शैली लागू करने के लिए, आप वांछित फ़ॉन्ट पर नेविगेट करने और उसकी शैली को "बोल्ड" पर सेट करने के लिए एपीआई का उपयोग कर सकते हैं। यह निर्दिष्ट फ़ॉन्ट पर बोल्ड शैली लागू करेगा।

#### प्रश्न: क्या Aspose.Words के साथ किसी Word दस्तावेज़ में टेक्स्ट के किसी विशिष्ट भाग पर इटैलिक शैली लागू करना संभव है?

उ: हाँ, Aspose.Words के साथ आप किसी Word दस्तावेज़ में टेक्स्ट के एक विशिष्ट भाग पर इटैलिक शैली लागू कर सकते हैं। आप वांछित टेक्स्ट श्रेणी का चयन करने और उसकी शैली को "इटैलिक" पर सेट करने के लिए एपीआई का उपयोग कर सकते हैं।

#### प्रश्न: मैं Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में फ़ॉन्ट का रंग कैसे बदल सकता हूँ?

उ: Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में फ़ॉन्ट का रंग बदलने के लिए, आप API का उपयोग करके वांछित फ़ॉन्ट तक पहुंच सकते हैं और उसका रंग वांछित रंग में सेट कर सकते हैं। इससे दस्तावेज़ में फ़ॉन्ट का रंग बदल जाएगा.

#### प्रश्न: क्या Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में फ़ॉन्ट आकार बदलना संभव है?

उ: हाँ, आप Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में फ़ॉन्ट आकार बदल सकते हैं। एपीआई आपको फ़ॉन्ट तक पहुंचने और आपकी आवश्यकताओं के आधार पर उसका आकार बिंदुओं या स्केल बिंदुओं में सेट करने की सुविधा देता है।

#### प्रश्न: क्या मैं किसी Word दस्तावेज़ में एक ही टेक्स्ट पर बोल्ड और इटैलिक जैसे एकाधिक फ़ॉन्ट प्रारूप लागू कर सकता हूँ?

उ: हाँ, Aspose.Words के साथ आप Word दस्तावेज़ में एक ही टेक्स्ट पर बोल्ड और इटैलिक जैसे कई फ़ॉन्ट प्रारूप लागू कर सकते हैं। आप टेक्स्ट के अलग-अलग हिस्सों के लिए अपनी इच्छित अलग-अलग फ़ॉन्ट शैलियाँ सेट करने के लिए एपीआई का उपयोग कर सकते हैं।