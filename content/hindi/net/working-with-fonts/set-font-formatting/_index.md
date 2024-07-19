---
title: फ़ॉन्ट स्वरूपण सेट करें
linktitle: फ़ॉन्ट स्वरूपण सेट करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में फ़ॉन्ट फ़ॉर्मेटिंग सेट करना और आकर्षक दस्तावेज़ बनाना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-fonts/set-font-formatting/
---
इस ट्यूटोरियल में, हम आपको दिखाएंगे कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में फ़ॉन्ट फ़ॉर्मेटिंग कैसे सेट करें। आप सीखेंगे कि बोल्ड, रंग, इटैलिक्स, फ़ॉन्ट, आकार, स्पेसिंग और अंडरलाइनिंग जैसी शैलियाँ कैसे लागू करें।

## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित वस्तुएं हैं:
- C# प्रोग्रामिंग भाषा का कार्यसाधक ज्ञान
- आपके प्रोजेक्ट में .NET के लिए Aspose.Words लाइब्रेरी स्थापित है

## चरण 1: दस्तावेज़ निर्देशिका निर्धारित करें
अपने Word दस्तावेज़ के स्थान पर निर्देशिका पथ सेट करके प्रारंभ करें।`"YOUR DOCUMENT DIRECTORY"` कोड में उचित पथ के साथ.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ बनाएँ और फ़ॉर्मेट करें
 इसका एक उदाहरण बनाएं`Document` वर्ग और`DocumentBuilder` दस्तावेज़ बनाने के लिए क्लास का उपयोग करें।`Font` की संपत्ति`DocumentBuilder` फ़ॉन्ट स्वरूपण गुणों तक पहुँचने के लिए.

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
 उपयोग`Save`दस्तावेज़ को फ़ॉन्ट फ़ॉर्मेटिंग के साथ सहेजने की विधि।`"WorkingWithFonts.SetFontFormatting.docx"` इच्छित फ़ाइल नाम के साथ.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके फ़ॉन्ट स्वरूपण सेट करने के लिए नमूना स्रोत कोड 
```csharp

// आपके दस्तावेज़ निर्देशिका का पथ
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
बधाई हो! अब आप जानते हैं कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में फ़ॉन्ट फ़ॉर्मेटिंग कैसे सेट करें। आप अधिक फ़ॉन्ट फ़ॉर्मेटिंग विकल्पों का पता लगा सकते हैं और व्यक्तिगत और आकर्षक Word दस्तावेज़ बना सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words का उपयोग करके Word दस्तावेज़ में फ़ॉन्ट पर बोल्ड शैली कैसे लागू कर सकता हूं?

उत्तर: Aspose.Words का उपयोग करके Word दस्तावेज़ में फ़ॉन्ट पर बोल्ड शैली लागू करने के लिए, आप वांछित फ़ॉन्ट पर नेविगेट करने के लिए API का उपयोग कर सकते हैं और इसकी शैली को "बोल्ड" पर सेट कर सकते हैं। यह निर्दिष्ट फ़ॉन्ट पर बोल्ड शैली लागू करेगा।

#### प्रश्न: क्या Aspose.Words के साथ Word दस्तावेज़ में पाठ के किसी विशिष्ट भाग पर इटैलिक शैली लागू करना संभव है?

उत्तर: हाँ, Aspose.Words के साथ आप Word दस्तावेज़ में टेक्स्ट के किसी विशिष्ट भाग पर इटैलिक शैली लागू कर सकते हैं। आप वांछित टेक्स्ट रेंज का चयन करने के लिए API का उपयोग कर सकते हैं और इसकी शैली को "इटैलिक" पर सेट कर सकते हैं।

#### प्रश्न: मैं Aspose.Words का उपयोग करके Word दस्तावेज़ में फ़ॉन्ट का रंग कैसे बदल सकता हूँ?

उत्तर: Aspose.Words का उपयोग करके Word दस्तावेज़ में फ़ॉन्ट रंग बदलने के लिए, आप API का उपयोग करके वांछित फ़ॉन्ट तक पहुँच सकते हैं और उसका रंग इच्छित रंग पर सेट कर सकते हैं। इससे दस्तावेज़ में फ़ॉन्ट का रंग बदल जाएगा।

#### प्रश्न: क्या Aspose.Words का उपयोग करके Word दस्तावेज़ में फ़ॉन्ट का आकार बदलना संभव है?

उत्तर: हाँ, आप Aspose.Words का उपयोग करके Word दस्तावेज़ में फ़ॉन्ट का आकार बदल सकते हैं। API आपको फ़ॉन्ट तक पहुँचने और अपनी ज़रूरतों के आधार पर पॉइंट या स्केल पॉइंट में उसका आकार सेट करने देता है।

#### प्रश्न: क्या मैं वर्ड दस्तावेज़ में एक ही पाठ पर बोल्ड और इटैलिक जैसे एकाधिक फ़ॉन्ट प्रारूप लागू कर सकता हूँ?

उत्तर: हाँ, Aspose.Words के साथ आप Word दस्तावेज़ में एक ही टेक्स्ट पर कई फ़ॉन्ट फ़ॉर्मेट, जैसे बोल्ड और इटैलिक, लागू कर सकते हैं। आप टेक्स्ट के अलग-अलग हिस्सों के लिए अपनी पसंद की अलग-अलग फ़ॉन्ट शैलियाँ सेट करने के लिए API का इस्तेमाल कर सकते हैं।