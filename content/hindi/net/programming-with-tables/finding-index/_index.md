---
title: सूचकांक ढूँढना
linktitle: सूचकांक ढूँढना
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में तालिका, पंक्ति और सेल अनुक्रमणिका ढूँढ़ना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/finding-index/
---

इस ट्यूटोरियल में, हम सीखेंगे कि Word दस्तावेज़ में तालिका, पंक्ति और सेल के अनुक्रमणिका को खोजने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण दर चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत में, आप प्रोग्रामेटिक रूप से अपने वर्ड दस्तावेज़ों में सरणी तत्वों की अनुक्रमणिका पा सकेंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. विज़ुअल स्टूडियो लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ लोड करना और तालिका तक पहुँचना
तालिका के साथ वर्ड प्रोसेसिंग शुरू करने के लिए, हमें उस दस्तावेज़ को लोड करना होगा जिसमें यह शामिल है और इसे एक्सेस करना होगा। इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Tables.docx");

// सरणी तक पहुंच
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

अपने दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ "आपकी दस्तावेज़ निर्देशिका" को बदलना सुनिश्चित करें।

## चरण 3: तालिका, पंक्ति और सेल सूचकांक खोजें
इसके बाद, हम .NET के लिए Aspose.Words द्वारा प्रदान की गई विधियों का उपयोग करके सरणी में तालिका, पंक्ति और सेल इंडेक्स ढूंढेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
// तालिका अनुक्रमणिका खोजें
NodeCollection allTables = doc.GetChildNodes(NodeType.Table, true);
int tableIndex = allTables.IndexOf(table);
Console.WriteLine("\nTable index is " + tableIndex);

// पंक्ति अनुक्रमणिका खोजें
int rowIndex = table.IndexOf(table.LastRow);
Console.WriteLine("\nLine index is " + rowIndex);

// सेल इंडेक्स खोजें
Row row = table. LastRow;
int cellIndex = row.IndexOf(row.Cells[4]);
Console.WriteLine("\nCell index is " + cellIndex);
```

 यहां हम इसका उपयोग करते हैं`GetChildNodes` दस्तावेज़ में सभी तालिकाएँ प्राप्त करने की विधि। फिर हम प्रयोग करते हैं`IndexOf` सभी तालिकाओं के संग्रह में विशिष्ट तालिका का सूचकांक ढूँढ़ने के लिए। इसी तरह, हम उपयोग करते हैं`IndexOf` तालिका में अंतिम पंक्ति का सूचकांक खोजने के लिए, और`IndexOf` किसी विशिष्ट सेल का सूचकांक खोजने के लिए एक पंक्ति के अंदर।

### .NET के लिए Aspose.Words का उपयोग करके इंडेक्स खोजने के लिए नमूना स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
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
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका, पंक्ति और सेल के सूचकांक कैसे खोजें। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप प्रोग्रामेटिक रूप से अपने Word दस्तावेज़ों में सरणी तत्वों की सटीक स्थिति ढूंढ और पहचान सकते हैं। यह सुविधा आपको अपनी विशिष्ट आवश्यकताओं के अनुरूप सरणी तत्वों के साथ सटीक रूप से हेरफेर करने और बातचीत करने की अनुमति देती है।