---
title: DOM का उपयोग करके मेल मर्ज एड्रेस ब्लॉक फ़ील्ड डालें
linktitle: DOM का उपयोग करके मेल मर्ज एड्रेस ब्लॉक फ़ील्ड डालें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ अपने Word दस्तावेज़ों में मेल मर्ज एड्रेस ब्लॉक फ़ील्ड सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

नीचे C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है, जो .NET के लिए Aspose.Words की "इन्सर्ट मेल मर्ज एड्रेस ब्लॉक फील्ड" सुविधा का उपयोग करता है। वांछित परिणाम प्राप्त करने के लिए प्रत्येक चरण का सावधानीपूर्वक पालन करना सुनिश्चित करें।

## चरण 1: दस्तावेज़ निर्देशिका सेटअप

दिए गए कोड में, आपको अपने दस्तावेज़ों की निर्देशिका निर्दिष्ट करनी होगी। अपने दस्तावेज़ निर्देशिका के लिए उचित पथ के साथ "आपकी दस्तावेज़ निर्देशिका" मान को बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ और दस्तावेज़बिल्डर बनाना

हम एक नया दस्तावेज़ बनाकर और एक DocumentBuilder प्रारंभ करके शुरुआत करते हैं।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: कर्सर को पैराग्राफ़ पर ले जाना

 हम DocumentBuilder का उपयोग करते हैं`MoveTo()` कर्सर को उस पैराग्राफ पर ले जाने की विधि जहां हम मेल मर्ज एड्रेस ब्लॉक फ़ील्ड डालना चाहते हैं।

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## चरण 4: मेल मर्ज एड्रेस ब्लॉक फ़ील्ड सम्मिलित करना

 हम DocumentBuilder का उपयोग करते हैं`InsertField()` पैराग्राफ में मेल मर्ज एड्रेस ब्लॉक फ़ील्ड डालने की विधि।

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

फिर हम उपयुक्त विकल्पों को निर्दिष्ट करते हुए पता ब्लॉक फ़ील्ड के गुणों को कॉन्फ़िगर करते हैं, जैसे कि देश/क्षेत्र का नाम शामिल करना, देश/क्षेत्र के अनुसार पते का प्रारूपण करना, देश/क्षेत्र के नामों को बाहर करना, नाम और पता प्रारूप, और भाषा पहचानकर्ता।

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 अंत में, हम कॉल करते हैं`Update()` फ़ील्ड को अद्यतन करने की विधि.

```csharp
field. Update();
```

### .NET के लिए Aspose.Words के साथ मेल मर्ज एड्रेस ब्लॉक फ़ील्ड डालने के लिए नमूना स्रोत कोड

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// हम इस तरह एक मेल मर्ज एड्रेस ब्लॉक सम्मिलित करना चाहते हैं:
// { एड्रेसब्लॉक \\c 1 \\d \\e Test2 \\f Test3 \\l \"टेस्ट 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { पताब्लॉक \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { पताब्लॉक \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { एड्रेसब्लॉक \\c 1 \\d \\e Test2 }
field.ExcludedCountryOrRegionName = "Test2";

// { एड्रेसब्लॉक \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// { एड्रेसब्लॉक \\c 1 \\d \\e Test2 \\f Test3 \\l \"टेस्ट 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं .NET के लिए Aspose.Words के साथ किसी Word दस्तावेज़ में मेलिंग पते के प्रारूप को कैसे अनुकूलित कर सकता हूँ?

 उ: आप .NET के गुणों का उपयोग करके Aspose.Words के साथ किसी Word दस्तावेज़ में मेलिंग पते के प्रारूप को अनुकूलित कर सकते हैं।`FieldAddressBlock`वस्तु। वांछित प्रारूप प्राप्त करने के लिए आप पता शैली, विभाजक, वैकल्पिक आइटम इत्यादि जैसे स्वरूपण विकल्प सेट कर सकते हैं।

#### प्रश्न: मैं .NET के लिए Aspose.Words में मेलिंग एड्रेस फ़ील्ड के लिए स्रोत डेटा कैसे निर्दिष्ट कर सकता हूं?

 उ: .NET के लिए Aspose.Words में मेलिंग एड्रेस फ़ील्ड के लिए स्रोत डेटा निर्दिष्ट करने के लिए, आप इसका उपयोग कर सकते हैं`FieldAddressBlock.StartAddress` और`FieldAddressBlock.EndAddress` गुण। इन गुणों का उपयोग बाहरी डेटा स्रोत, जैसे सीएसवी फ़ाइल, डेटाबेस इत्यादि में पता श्रेणियों को परिभाषित करने के लिए किया जाता है।

#### प्रश्न: क्या मैं .NET के लिए Aspose.Words के साथ मेलिंग एड्रेस फ़ील्ड में वैकल्पिक तत्व शामिल कर सकता हूँ?

 उत्तर: हां, आप .NET के लिए Aspose.Words के साथ मेलिंग एड्रेस फ़ील्ड में वैकल्पिक तत्व शामिल कर सकते हैं। आप इसका उपयोग करके वैकल्पिक तत्वों को परिभाषित कर सकते हैं`FieldAddressBlock.OmitOptional` यह निर्दिष्ट करने की विधि कि प्राप्तकर्ता का नाम, कंपनी का नाम इत्यादि जैसे वैकल्पिक तत्वों को शामिल करना है या बाहर करना है।

#### प्रश्न: क्या DOM का उपयोग करके मेलिंग एड्रेस फ़ील्ड डालने से .NET के लिए Aspose.Words के साथ Word दस्तावेज़ संरचना प्रभावित होती है?

उ: DOM का उपयोग करके मेलिंग एड्रेस फ़ील्ड सम्मिलित करना सीधे Word दस्तावेज़ की संरचना को प्रभावित नहीं करता है। हालाँकि, यह दस्तावेज़ सामग्री में एक नया फ़ील्ड तत्व जोड़ता है। आप अपनी आवश्यकताओं के अनुसार मौजूदा तत्वों को जोड़कर, हटाकर या संशोधित करके दस्तावेज़ संरचना में हेरफेर कर सकते हैं।