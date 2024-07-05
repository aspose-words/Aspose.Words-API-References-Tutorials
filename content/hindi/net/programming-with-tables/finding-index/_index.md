---
title: सूचकांक ढूँढना
linktitle: सूचकांक ढूँढना
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में तालिका, पंक्ति और सेल अनुक्रमणिकाएँ ढूँढना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/finding-index/
---

इस ट्यूटोरियल में, हम सीखेंगे कि Word दस्तावेज़ में तालिका, पंक्ति और सेल के इंडेक्स को खोजने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत में, आप अपने Word दस्तावेज़ों में सरणी तत्वों के इंडेक्स को प्रोग्रामेटिक रूप से खोजने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. Visual Studio लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. Aspose.Words for .NET लाइब्रेरी में संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ लोड करना और तालिका तक पहुँचना
टेबल के साथ वर्ड प्रोसेसिंग शुरू करने के लिए, हमें उस दस्तावेज़ को लोड करना होगा जिसमें यह शामिल है और इसे एक्सेस करना होगा। इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Tables.docx");

// सरणी तक पहुंच
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

"आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से प्रतिस्थापित करना सुनिश्चित करें।

## चरण 3: तालिका, पंक्ति और कक्ष अनुक्रमणिका खोजें
इसके बाद, हम .NET के लिए Aspose.Words द्वारा प्रदान की गई विधियों का उपयोग करके सरणी में तालिका, पंक्ति और सेल इंडेक्स ढूँढेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
// तालिका अनुक्रमणिका खोजें
NodeCollection allTables = doc.GetChildNodes(NodeType.Table, true);
int tableIndex = allTables.IndexOf(table);
Console.WriteLine("\nTable index is " + tableIndex);

// पंक्ति सूचकांक खोजें
int rowIndex = table.IndexOf(table.LastRow);
Console.WriteLine("\nLine index is " + rowIndex);

// सेल इंडेक्स खोजें
Row row = table. LastRow;
int cellIndex = row.IndexOf(row.Cells[4]);
Console.WriteLine("\nCell index is " + cellIndex);
```

 यहाँ हम उपयोग करते हैं`GetChildNodes` दस्तावेज़ में सभी तालिकाओं को प्राप्त करने के लिए विधि। फिर हम उपयोग करते हैं`IndexOf` सभी तालिकाओं के संग्रह में विशिष्ट तालिका का सूचकांक खोजने के लिए। इसी तरह, हम उपयोग करते हैं`IndexOf` तालिका में अंतिम पंक्ति का सूचकांक ज्ञात करने के लिए, तथा`IndexOf` किसी विशिष्ट सेल का सूचकांक खोजने के लिए पंक्ति के अंदर।

### .NET के लिए Aspose.Words का उपयोग करके इंडेक्स खोजने के लिए नमूना स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	NodeCollection allTables = doc.GetChildNodes(NodeType.Table, true);
	int tableIndex = allTables.IndexOf(table);
	Console.WriteLine("\nTable index is " + tableIndex);
	int rowIndex = table.IndexOf(table.LastRow);
	Console.WriteLine("\nRow index is " + rowIndex);
	Row row = table.LastRow;
	int cellIndex = row.IndexOf(row.Cells[4]);
	Console.WriteLine("\nCell index is " + cellIndex);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में तालिका, पंक्ति और सेल के इंडेक्स कैसे खोजें। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और प्रदान किए गए C# कोड को लागू करके, आप अपने Word दस्तावेज़ों में सरणी तत्वों की सटीक स्थिति को प्रोग्रामेटिक रूप से पा सकते हैं और पहचान सकते हैं। यह सुविधा आपको अपनी विशिष्ट आवश्यकताओं के अनुरूप सरणी तत्वों के साथ सटीक रूप से हेरफेर करने और बातचीत करने की अनुमति देती है।