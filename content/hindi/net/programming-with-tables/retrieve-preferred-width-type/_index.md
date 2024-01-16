---
title: पसंदीदा चौड़ाई प्रकार पुनः प्राप्त करें
linktitle: पसंदीदा चौड़ाई प्रकार पुनः प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ Word तालिका में सेल के प्रकार और पसंदीदा चौड़ाई मान को पुनः प्राप्त करने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/retrieve-preferred-width-type/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका सेल से पसंदीदा चौड़ाई प्रकार और उसके मान को कैसे पुनः प्राप्त किया जाए। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण दर चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत में, आप अपने वर्ड दस्तावेज़ तालिकाओं में एक विशिष्ट सेल के लिए पसंदीदा चौड़ाई प्रकार (पूर्ण, सापेक्ष, या स्वचालित) और उसके मूल्य को पुनः प्राप्त करने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. विज़ुअल स्टूडियो लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ लोड करना
दस्तावेज़ के साथ वर्ड प्रोसेसिंग प्रारंभ करने के लिए, इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Tables.docx");
```

अपने दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ "आपकी दस्तावेज़ निर्देशिका" को बदलना सुनिश्चित करें और सही फ़ाइल नाम प्रदान करें।

## चरण 3: पसंदीदा चौड़ाई प्रकार और मान पुनर्प्राप्त करना
इसके बाद, हम एक विशिष्ट तालिका सेल के लिए पसंदीदा चौड़ाई प्रकार और उसका मान पुनः प्राप्त करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
// तालिका पुनः प्राप्त करें
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// स्वचालित तालिका समायोजन सक्रिय करें
table. AllowAutoFit = true;

// पहली पंक्ति का पहला सेल पुनः प्राप्त करें
Cell firstCell = table.FirstRow.FirstCell;

// पसंदीदा चौड़ाई प्रकार और उसका मान पुनर्प्राप्त करें
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

यहां हम पहली तालिका लाने के लिए दस्तावेज़ का उपयोग करते हैं, फिर हम स्वचालित तालिका फ़िट को सक्षम करते हैं`AllowAutoFit` संपत्ति। फिर हम तालिका की पहली पंक्ति के पहले सेल को पुनः प्राप्त करते हैं। इस सेल से, हम पसंदीदा चौड़ाई प्रकार को पुनः प्राप्त कर सकते हैं`PreferredWidth.Type` संपत्ति और उसके मूल्य के साथ`PreferredWidth.Value` संपत्ति।

### .NET के लिए Aspose.Words का उपयोग करके पसंदीदा चौड़ाई प्रकार प्राप्त करने के लिए नमूना स्रोत कोड 

```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका सेल से पसंदीदा चौड़ाई प्रकार और उसके मान को कैसे पुनः प्राप्त किया जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप अपने Word दस्तावेज़ तालिकाओं में विशिष्ट कक्षों के लिए यह जानकारी पुनः प्राप्त कर सकते हैं।