---
title: तालिका स्थिति प्राप्त करें
linktitle: तालिका स्थिति प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि .NET के लिए Aspose.Words के साथ किसी Word दस्तावेज़ में तालिका की स्थिति कैसे प्राप्त करें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/get-table-position/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका की स्थिति कैसे प्राप्त करें। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण दर चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत में, आप प्रोग्रामेटिक रूप से अपने वर्ड दस्तावेज़ों में टेबल पोजिशनिंग गुण प्राप्त करने में सक्षम होंगे।

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

अपने दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ "आपकी दस्तावेज़ निर्देशिका" को बदलना सुनिश्चित करें। साथ ही, सुनिश्चित करें कि दस्तावेज़ में वह तालिका शामिल है जिसका स्थान आप प्राप्त करना चाहते हैं।

## चरण 3: ऐरे पोजिशनिंग गुण प्राप्त करना
इसके बाद, हम सरणी के पोजिशनिंग प्रकार की जांच करेंगे और उचित पोजिशनिंग गुण प्राप्त करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 यहां हम यह जांचने के लिए एक शर्त का उपयोग करते हैं कि सरणी फ्लोट प्रकार की है या नहीं। यदि हां, तो हम इसे प्रिंट करते हैं`RelativeHorizontalAlignment` और`RelativeVerticalAlignment` तालिका के सापेक्ष क्षैतिज और ऊर्ध्वाधर संरेखण प्राप्त करने के लिए गुण। अन्यथा, हम प्रिंट करते हैं`Alignment` सरणी संरेखण प्राप्त करने के लिए संपत्ति।

### .NET के लिए Aspose.Words का उपयोग करके तालिका स्थिति प्राप्त करने के लिए नमूना स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका की स्थिति कैसे प्राप्त करें। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप प्रोग्रामेटिक रूप से अपने Word दस्तावेज़ों में तालिका स्थिति गुण प्राप्त कर सकते हैं। यह सुविधा आपको उनकी विशिष्ट स्थिति के अनुसार सरणियों का विश्लेषण और हेरफेर करने की अनुमति देती है।