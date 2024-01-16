---
title: टेबल साथ रखें
linktitle: टेबल साथ रखें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में तालिका को एक साथ रखने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/keep-table-together/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका को एक साथ कैसे रखा जाए। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण दर चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत तक, आप अपने Word दस्तावेज़ों में एक तालिका को कई पृष्ठों में विभाजित किए बिना अक्षुण्ण रखने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. विज़ुअल स्टूडियो लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ लोड करना और तालिका पुनः प्राप्त करना
तालिका के साथ वर्ड प्रोसेसिंग शुरू करने के लिए, हमें दस्तावेज़ को लोड करना होगा और उस तालिका को लाना होगा जिसे हम एक साथ रखना चाहते हैं। इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// तालिका पुनः प्राप्त करें
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

अपने दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ "आपकी दस्तावेज़ निर्देशिका" को बदलना सुनिश्चित करें।

## चरण 3: "KeepWithNext" विकल्प सक्षम करें
तालिका को एक साथ रखने और इसे कई पृष्ठों में विभाजित होने से रोकने के लिए, हमें तालिका की अंतिम पंक्ति के अंतिम पैराग्राफ को छोड़कर तालिका के प्रत्येक पैराग्राफ के लिए "KeepWithNext" विकल्प को सक्षम करने की आवश्यकता है। निम्नलिखित कोड का प्रयोग करें:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

यहां हम तालिका में प्रत्येक सेल के माध्यम से लूप करते हैं और तालिका में अंतिम पंक्ति के अंतिम पैराग्राफ को छोड़कर सेल में प्रत्येक पैराग्राफ के लिए "KeepWithNext" विकल्प को सक्षम करते हैं।

## चरण 4: संशोधित दस्तावेज़ को सहेजना
अंत में, हमें संशोधित दस्तावेज़ को तालिका के साथ सहेजने की आवश्यकता है। निम्नलिखित कोड का प्रयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके टेबल को एक साथ रखें के लिए नमूना स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// हमें तालिका के प्रत्येक अनुच्छेद को पृष्ठ पर टूटने से बचाने के लिए KeepWithNext को सक्षम करने की आवश्यकता है,
	// तालिका की अंतिम पंक्ति के अंतिम पैराग्राफ को छोड़कर।
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका को एक साथ कैसे रखा जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप एक तालिका को बरकरार रख सकते हैं और इसे अपने दस्तावेज़ों में कई पृष्ठों में विभाजित होने से रोक सकते हैं। यह सुविधा आपको अपने दस्तावेज़ों में तालिकाओं के स्वरूप और लेआउट पर अधिक नियंत्रण प्रदान करती है।