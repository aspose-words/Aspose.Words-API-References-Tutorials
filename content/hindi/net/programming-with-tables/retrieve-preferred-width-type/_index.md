---
title: पसंदीदा चौड़ाई प्रकार प्राप्त करें
linktitle: पसंदीदा चौड़ाई प्रकार प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ Word तालिका में किसी सेल के प्रकार और पसंदीदा चौड़ाई मान को पुनः प्राप्त करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/retrieve-preferred-width-type/
---

इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में टेबल सेल से पसंदीदा चौड़ाई प्रकार और उसका मान कैसे प्राप्त करें। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत में, आप अपने Word दस्तावेज़ तालिकाओं में किसी विशिष्ट सेल के लिए पसंदीदा चौड़ाई प्रकार (पूर्ण, सापेक्ष या स्वचालित) और उसका मान प्राप्त करने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. Visual Studio लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. Aspose.Words for .NET लाइब्रेरी में संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ लोड करना
दस्तावेज़ के साथ वर्ड्स प्रोसेसिंग शुरू करने के लिए, इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Tables.docx");
```

"आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से प्रतिस्थापित करना सुनिश्चित करें और सही फ़ाइल नाम प्रदान करें।

## चरण 3: पसंदीदा चौड़ाई प्रकार और मान प्राप्त करना
इसके बाद, हम किसी विशिष्ट टेबल सेल के लिए पसंदीदा चौड़ाई प्रकार और उसका मान प्राप्त करेंगे। निम्न कोड का उपयोग करें:

```csharp
// तालिका पुनः प्राप्त करें
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// स्वचालित तालिका समायोजन सक्रिय करें
table. AllowAutoFit = true;

// पहली पंक्ति का पहला सेल पुनः प्राप्त करें
Cell firstCell = table.FirstRow.FirstCell;

// पसंदीदा चौड़ाई प्रकार और उसका मान प्राप्त करें
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

यहां हम पहले तालिका को लाने के लिए दस्तावेज़ का उपयोग करते हैं, फिर हम स्वचालित तालिका फ़िट को सक्षम करते हैं`AllowAutoFit` प्रॉपर्टी। फिर हम टेबल की पहली पंक्ति के पहले सेल को पुनः प्राप्त करते हैं। इस सेल से, हम पसंदीदा चौड़ाई प्रकार को पुनः प्राप्त कर सकते हैं`PreferredWidth.Type` संपत्ति और उसका मूल्य`PreferredWidth.Value` संपत्ति।

### .NET के लिए Aspose.Words का उपयोग करके पसंदीदा चौड़ाई प्रकार प्राप्त करने के लिए नमूना स्रोत कोड 

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में टेबल सेल से पसंदीदा चौड़ाई प्रकार और उसका मान कैसे प्राप्त करें। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप अपने Word दस्तावेज़ तालिकाओं में विशिष्ट कक्षों के लिए यह जानकारी प्राप्त कर सकते हैं।