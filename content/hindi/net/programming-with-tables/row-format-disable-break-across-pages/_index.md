---
title: पंक्ति प्रारूप पृष्ठों में विराम अक्षम करें
linktitle: पंक्ति प्रारूप पृष्ठों में विराम अक्षम करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: Aspose.Words for .NET के साथ Word दस्तावेज़ में एकाधिक पृष्ठों में तालिका के लिए लाइन ब्रेक को अक्षम करने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/row-format-disable-break-across-pages/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में मल्टी-पेज टेबल के लाइन ब्रेक को कैसे अक्षम किया जाए। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत तक, आप अपने Word दस्तावेज़ों में अपनी तालिका में सभी पंक्तियों के लिए लाइन ब्रेकिंग को अक्षम करने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. Visual Studio लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. Aspose.Words for .NET लाइब्रेरी में संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ लोड करना
दस्तावेज़ के साथ वर्ड्स प्रोसेसिंग शुरू करने के लिए, इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

"आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से प्रतिस्थापित करना सुनिश्चित करें और सही फ़ाइल नाम प्रदान करें।

## चरण 3: तालिका पंक्ति विराम अक्षम करें
इसके बाद, हम तालिका में सभी पंक्तियों के लिए पंक्ति विखंडन अक्षम कर देंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
// तालिका पुनः प्राप्त करें
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// तालिका में सभी पंक्तियों के लिए पंक्ति विराम अक्षम करें
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 यहाँ हम पहले टेबल को लाने के लिए दस्तावेज़ का उपयोग करते हैं और फिर foreach लूप का उपयोग करके टेबल में सभी पंक्तियों के माध्यम से पुनरावृति करते हैं। लूप के अंदर, हम प्रत्येक पंक्ति के लिए पंक्ति विखंडन को अक्षम करके सेट करते हैं`RowFormat.AllowBreakAcrossPages`संपत्ति को`false`.

## चरण 4: संशोधित दस्तावेज़ को सहेजना
अंत में, हमें संशोधित दस्तावेज़ को टेबल लाइन ब्रेक अक्षम करके सहेजना होगा। निम्नलिखित कोड का उपयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके पंक्ति प्रारूप अक्षम पृष्ठ पार ब्रेक के लिए नमूना स्रोत कोड 

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// तालिका में सभी पंक्तियों के लिए पृष्ठों में विभाजन अक्षम करें.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में एक बहु-पृष्ठ तालिका के लाइन ब्रेक को कैसे अक्षम किया जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और प्रदान किए गए C# कोड को लागू करके, आप अपने Word दस्तावेज़ों में अपनी तालिकाओं पर इस अक्षमता को लागू कर सकते हैं।