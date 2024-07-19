---
title: टेबल को एक साथ रखें
linktitle: टेबल को एक साथ रखें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में तालिका को एक साथ रखना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/keep-table-together/
---

इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में टेबल को एक साथ कैसे रखा जाए। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत तक, आप अपने Word दस्तावेज़ों में कई पृष्ठों में विभाजित किए बिना टेबल को बरकरार रखने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. Visual Studio लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. Aspose.Words for .NET लाइब्रेरी में संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ लोड करना और तालिका पुनर्प्राप्त करना
टेबल के साथ वर्ड प्रोसेसिंग शुरू करने के लिए, हमें दस्तावेज़ लोड करना होगा और वह टेबल लाना होगा जिसे हम साथ रखना चाहते हैं। इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// तालिका पुनः प्राप्त करें
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

"आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से प्रतिस्थापित करना सुनिश्चित करें।

## चरण 3: "KeepWithNext" विकल्प सक्षम करें
तालिका को एक साथ रखने और इसे कई पृष्ठों में विभाजित होने से रोकने के लिए, हमें तालिका की अंतिम पंक्ति के अंतिम पैराग्राफ को छोड़कर तालिका में प्रत्येक पैराग्राफ के लिए "KeepWithNext" विकल्प को सक्षम करने की आवश्यकता है। निम्नलिखित कोड का उपयोग करें:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

यहां हम तालिका के प्रत्येक कक्ष में लूप करते हैं और तालिका की अंतिम पंक्ति के अंतिम पैराग्राफ को छोड़कर कक्ष के प्रत्येक पैराग्राफ के लिए "KeepWithNext" विकल्प को सक्षम करते हैं।

## चरण 4: संशोधित दस्तावेज़ को सहेजना
अंत में, हमें संशोधित दस्तावेज़ को तालिका के साथ सहेजना होगा। निम्नलिखित कोड का उपयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके Keep Table Together के लिए नमूना स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// हमें तालिका में प्रत्येक पैराग्राफ के लिए KeepWithNext को सक्षम करने की आवश्यकता है ताकि इसे पृष्ठ पर विभाजित होने से बचाया जा सके,
	//तालिका की अंतिम पंक्ति के अंतिम पैराग्राफ को छोड़कर।
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
इस ट्यूटोरियल में, हमने सीखा कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में टेबल को एक साथ कैसे रखा जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप टेबल को बरकरार रख सकते हैं और इसे अपने दस्तावेज़ों में कई पृष्ठों में विभाजित होने से रोक सकते हैं। यह सुविधा आपको अपने दस्तावेज़ों में अपनी तालिकाओं की उपस्थिति और लेआउट पर अधिक नियंत्रण देती है।