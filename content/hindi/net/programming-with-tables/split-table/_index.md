---
title: विभाजित तालिका
linktitle: विभाजित तालिका
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में तालिका को विभाजित करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/split-table/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में तालिका को कैसे विभाजित किया जाए। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत में, आप अपने Word दस्तावेज़ों में एक निश्चित पंक्ति से तालिका को विभाजित करने में सक्षम होंगे।

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

## चरण 3: तालिका को विभाजित करना
अब हम एक निश्चित पंक्ति से तालिका को विभाजित करेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
// पहली तालिका पुनः प्राप्त करें
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// तालिका को किस रेखा से विभाजित करना है इसका निर्धारण
Row row = firstTable.Rows[2];

// विभाजित तालिका के लिए एक नया कंटेनर बनाएँ
Table table = (Table)firstTable.Clone(false);

// मूल तालिका के बाद कंटेनर डालें
firstTable.ParentNode.InsertAfter(table, firstTable);

// तालिकाओं के बीच दूरी बनाए रखने के लिए बफर पैराग्राफ़ जोड़ें
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// मूल तालिका से पंक्तियों को विभाजित तालिका में ले जाएँ
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

यहाँ हम डॉक्यूमेंट नोड से पहली तालिका प्राप्त करने के लिए डॉक्यूमेंट का उपयोग करते हैं। फिर हम उस पंक्ति को निर्धारित करते हैं जिससे हम तालिका को विभाजित करना चाहते हैं, इस उदाहरण में यह तीसरी पंक्ति (इंडेक्स 2) है। फिर हम मूल तालिका को क्लोन करके एक नया कंटेनर बनाते हैं और फिर इसे मूल तालिका के बाद सम्मिलित करते हैं। हम दो तालिकाओं के बीच दूरी बनाए रखने के लिए एक बफर पैराग्राफ भी जोड़ते हैं। फिर हम do-while लूप का उपयोग करके मूल तालिका से पंक्तियों को विभाजित तालिका में तब तक ले जाते हैं जब तक कि हम निर्दिष्ट पंक्ति तक नहीं पहुँच जाते।

## चरण 4: संशोधित दस्तावेज़ को सहेजना
अंततः हमें इसे बचाने की आवश्यकता है।

  दस्तावेज़ को विभाजित तालिका के साथ संशोधित करें। निम्नलिखित कोड का उपयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके विभाजित तालिका के लिए नमूना स्रोत कोड 

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// हम मेज को तीसरी पंक्ति (सहित) में विभाजित करेंगे।
Row row = firstTable.Rows[2];
// विभाजित तालिका के लिए एक नया कंटेनर बनाएँ.
Table table = (Table) firstTable.Clone(false);
// मूल के बाद कंटेनर डालें।
firstTable.ParentNode.InsertAfter(table, firstTable);
// यह सुनिश्चित करने के लिए कि तालिकाएं अलग-अलग रहें, एक बफर पैराग्राफ जोड़ें।
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
इस ट्यूटोरियल में, हमने सीखा कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में तालिका को कैसे विभाजित किया जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और प्रदान किए गए C# कोड को लागू करके, आप अपने Word दस्तावेज़ों में किसी निश्चित पंक्ति से तालिकाओं को आसानी से विभाजित कर सकते हैं।