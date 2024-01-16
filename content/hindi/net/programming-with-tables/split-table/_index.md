---
title: विभाजित तालिका
linktitle: विभाजित तालिका
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में तालिका को विभाजित करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/split-table/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका को कैसे विभाजित किया जाए। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण दर चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत में, आप अपने Word दस्तावेज़ों में एक तालिका को एक निश्चित पंक्ति से विभाजित करने में सक्षम होंगे।

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

## चरण 3: तालिका को विभाजित करना
आगे हम तालिका को एक निश्चित पंक्ति से विभाजित करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
// पहली तालिका पुनः प्राप्त करें
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// उस रेखा का निर्धारण जिससे तालिका को विभाजित करना है
Row row = firstTable.Rows[2];

// स्प्लिट टेबल के लिए एक नया कंटेनर बनाएं
Table table = (Table)firstTable.Clone(false);

// मूल तालिका के बाद कंटेनर डालें
firstTable.ParentNode.InsertAfter(table, firstTable);

// तालिकाओं के बीच दूरी बनाए रखने के लिए एक बफर पैराग्राफ जोड़ें
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// पंक्तियों को मूल तालिका से विभाजित तालिका में ले जाएँ
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

यहां हम दस्तावेज़ नोड से पहली तालिका पुनर्प्राप्त करने के लिए दस्तावेज़ का उपयोग करते हैं। फिर हम वह पंक्ति निर्धारित करते हैं जिससे हम तालिका को विभाजित करना चाहते हैं, इस उदाहरण में यह तीसरी पंक्ति है (सूचकांक 2)। फिर हम मूल तालिका की क्लोनिंग करके एक नया कंटेनर बनाते हैं और फिर उसे मूल तालिका के बाद सम्मिलित करते हैं। हम दो तालिकाओं के बीच दूरी बनाए रखने के लिए एक बफर पैराग्राफ भी जोड़ते हैं। फिर हम डू-व्हाइल लूप का उपयोग करके पंक्तियों को मूल तालिका से विभाजित तालिका में ले जाते हैं जब तक कि हम निर्दिष्ट पंक्ति तक नहीं पहुंच जाते।

## चरण 4: संशोधित दस्तावेज़ को सहेजना
अंततः, हमें इसे बचाने की आवश्यकता है

  दस्तावेज़ को विभाजित तालिका के साथ संशोधित किया गया। निम्नलिखित कोड का प्रयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके स्प्लिट टेबल के लिए नमूना स्रोत कोड 

```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// हम तालिका को तीसरी पंक्ति (समावेशी) में विभाजित करेंगे।
Row row = firstTable.Rows[2];
// स्प्लिट टेबल के लिए एक नया कंटेनर बनाएं।
Table table = (Table) firstTable.Clone(false);
// मूल के बाद कंटेनर डालें।
firstTable.ParentNode.InsertAfter(table, firstTable);
// यह सुनिश्चित करने के लिए कि तालिकाएँ अलग रहें, एक बफ़र पैराग्राफ़ जोड़ें।
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका को कैसे विभाजित किया जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप आसानी से अपने Word दस्तावेज़ों में तालिकाओं को एक निश्चित पंक्ति से विभाजित कर सकते हैं।