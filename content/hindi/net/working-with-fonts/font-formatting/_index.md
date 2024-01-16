---
title: फ़ॉन्ट स्वरूपण
linktitle: फ़ॉन्ट स्वरूपण
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: इस ट्यूटोरियल में, सीखें कि .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में फ़ॉन्ट को कैसे प्रारूपित करें।
type: docs
weight: 10
url: /hi/net/working-with-fonts/font-formatting/
---

इस ट्यूटोरियल में, हम आपको बताएंगे कि .NET के लिए Aspose.Words लाइब्रेरी का उपयोग करके किसी Word दस्तावेज़ में फ़ॉन्ट फ़ॉर्मेटिंग कैसे करें। फ़ॉन्ट फ़ॉर्मेटिंग आपको टेक्स्ट के स्वरूप को अनुकूलित करने देता है, जिसमें आकार, बोल्ड, रंग, फ़ॉन्ट, अंडरलाइन और बहुत कुछ शामिल है। हम आपके .NET प्रोजेक्ट में कोड को समझने और लागू करने में आपकी सहायता के लिए चरण-दर-चरण कदम उठाएंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित चीज़ें हैं:
- C# प्रोग्रामिंग भाषा का कार्यसाधक ज्ञान
- आपके प्रोजेक्ट में .NET के लिए Aspose.Words लाइब्रेरी स्थापित है

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें
 सबसे पहले, आपको अपने Word दस्तावेज़ के स्थान पर निर्देशिका पथ सेट करना होगा। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उचित पथ के साथ कोड में।

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: एक नया दस्तावेज़ और दस्तावेज़ जनरेटर बनाएं
 इसके बाद, हम इंस्टेंटियेट करके एक नया दस्तावेज़ बनाएंगे`Document` क्लास और एक दस्तावेज़ निर्माता को इंस्टेंटिअट करके`DocumentBuilder` कक्षा।

```csharp
// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();

//एक दस्तावेज़ जनरेटर बनाएँ
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: फ़ॉन्ट स्वरूपण कॉन्फ़िगर करें
 अब हम एक्सेस करेंगे`Font` दस्तावेज़ जनरेटर का ऑब्जेक्ट बनाएं और फ़ॉन्ट स्वरूपण गुणों जैसे आकार, बोल्ड, रंग, फ़ॉन्ट, अंडरलाइन इत्यादि को कॉन्फ़िगर करें।

```csharp
// फ़ॉन्ट तक पहुंचें
Font font = builder.Font;

// फ़ॉन्ट स्वरूपण कॉन्फ़िगर करें
font.Size = 16;
font. Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;
```

## चरण 4: दस्तावेज़ में टेक्स्ट जोड़ें
इसके बाद, हम दस्तावेज़ में कुछ स्वरूपित पाठ जोड़ने के लिए दस्तावेज़ निर्माता का उपयोग करेंगे।

```csharp
// दस्तावेज़ में टेक्स्ट जोड़ें
builder.Write("Example text.");
```

## चरण 5: दस्तावेज़ सहेजें
अंत में, हम फ़ॉन्ट फ़ॉर्मेटिंग वाले दस्तावेज़ को सहेजेंगे।

```csharp
doc.Save(dataDir + "WorkingWithFonts.FontFormatting.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके फ़ॉन्ट फ़ॉर्मेटिंग के लिए नमूना स्रोत कोड 
```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;
builder.Write("Sample text.");
doc.Save(dataDir + "WorkingWithFonts.FontFormatting.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने देखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में फ़ॉन्ट फ़ॉर्मेटिंग कैसे की जाती है। फ़ॉन्ट फ़ॉर्मेटिंग आपको अपने दस्तावेज़ों में टेक्स्ट की उपस्थिति को अनुकूलित करने की अनुमति देता है। आकर्षक और पेशेवर दस्तावेज़ बनाने के लिए बेझिझक इस सुविधा का उपयोग करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या किसी Word दस्तावेज़ में विशिष्ट टेक्स्ट का फ़ॉन्ट आकार बदलना संभव है?

उ: हां, Aspose.Words के साथ आप Word दस्तावेज़ में विशिष्ट टेक्स्ट का फ़ॉन्ट आकार आसानी से बदल सकते हैं। आप वांछित टेक्स्ट का चयन करने और उचित फ़ॉन्ट आकार लागू करने के लिए एपीआई का उपयोग कर सकते हैं।

#### प्रश्न: क्या मैं किसी Word दस्तावेज़ में विभिन्न अनुच्छेदों पर भिन्न फ़ॉन्ट शैलियाँ लागू कर सकता हूँ?

उत्तर: बिल्कुल! Aspose.Words आपको Word दस्तावेज़ में विभिन्न अनुच्छेदों पर भिन्न फ़ॉन्ट शैलियाँ लागू करने देता है। आप आवश्यकतानुसार प्रत्येक अनुच्छेद को व्यक्तिगत रूप से प्रारूपित करने के लिए एपीआई द्वारा प्रदान की गई विधियों का उपयोग कर सकते हैं।

#### प्रश्न: मैं किसी Word दस्तावेज़ में बोल्ड टेक्स्ट को कैसे हाइलाइट कर सकता हूँ?

उत्तर: Aspose.Words के साथ, आप Word दस्तावेज़ में बोल्ड टेक्स्ट को आसानी से हाइलाइट कर सकते हैं। बस एपीआई का उपयोग करके विशिष्ट टेक्स्ट पर बोल्ड फ़ॉन्ट शैली लागू करें।

#### प्रश्न: क्या Aspose.Words कस्टम फ़ॉन्ट का समर्थन करता है?

उत्तर: हाँ, Aspose.Words Word दस्तावेज़ों में कस्टम फ़ॉन्ट का समर्थन करता है। आप अपने दस्तावेज़ों में कस्टम फ़ॉन्ट का उपयोग कर सकते हैं और उन्हें अपनी प्राथमिकताओं के अनुसार प्रारूपित कर सकते हैं।

#### प्रश्न: मैं किसी Word दस्तावेज़ में टेक्स्ट पर एक विशिष्ट फ़ॉन्ट रंग कैसे लागू कर सकता हूं?

उत्तर: Aspose.Words के साथ, आप Word दस्तावेज़ में टेक्स्ट पर एक विशिष्ट फ़ॉन्ट रंग आसानी से लागू कर सकते हैं। टेक्स्ट का चयन करने और उचित रंग कोड निर्दिष्ट करके वांछित फ़ॉन्ट रंग लागू करने के लिए एपीआई का उपयोग करें।