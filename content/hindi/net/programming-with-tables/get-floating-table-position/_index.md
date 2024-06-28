---
title: फ़्लोटिंग टेबल स्थिति प्राप्त करें
linktitle: फ़्लोटिंग टेबल स्थिति प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि .NET के लिए Aspose.Words के साथ किसी Word दस्तावेज़ में फ़्लोटिंग तालिकाओं की स्थिति कैसे प्राप्त करें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/get-floating-table-position/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में फ़्लोटिंग टेबल की स्थिति कैसे प्राप्त करें। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण दर चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत में, आप प्रोग्रामेटिक रूप से अपने वर्ड दस्तावेज़ों में एक फ्लोटिंग टेबल की पोजिशनिंग गुण प्राप्त करने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. विज़ुअल स्टूडियो लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ लोड करना और तालिकाओं तक पहुंचना
तालिकाओं के साथ वर्ड प्रोसेसिंग शुरू करने के लिए, हमें उस दस्तावेज़ को लोड करना होगा जिसमें वे शामिल हैं और उन तक पहुंचें। इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

अपने दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ "आपकी दस्तावेज़ निर्देशिका" को बदलना सुनिश्चित करें। साथ ही, सुनिश्चित करें कि दस्तावेज़ में फ़्लोटिंग टेबल शामिल हैं।

## चरण 3: फ़्लोटिंग टेबल पोजिशनिंग गुण प्राप्त करना
इसके बाद, हम दस्तावेज़ में सभी तालिकाओं के माध्यम से लूप करेंगे और फ़्लोटिंग टेबल पोजिशनिंग गुण प्राप्त करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// यदि ऐरे एक फ़्लोटिंग प्रकार है, तो उसके पोजिशनिंग गुणों को प्रिंट करें।
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 यहां हम a का प्रयोग कर रहे हैं`foreach` दस्तावेज़ में सभी सरणियों के माध्यम से लूप टू लूप। हम जाँच कर जाँचते हैं कि सरणी फ़्लोट प्रकार की है या नहीं`TextWrapping` संपत्ति। यदि ऐसा है, तो हम तालिका के पोजिशनिंग गुणों को प्रिंट करते हैं, जैसे क्षैतिज एंकर, ऊर्ध्वाधर एंकर, पूर्ण क्षैतिज और ऊर्ध्वाधर दूरी, ओवरलैपिंग अनुमति, पूर्ण क्षैतिज दूरी और लंबवत संरेखण सापेक्ष।
 
### .NET के लिए Aspose.Words का उपयोग करके फ़्लोटिंग टेबल स्थिति प्राप्त करने के लिए नमूना स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// यदि तालिका फ़्लोटिंग प्रकार की है, तो उसके पोजिशनिंग गुणों को प्रिंट करें।
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में फ़्लोटिंग टेबल की स्थिति कैसे प्राप्त करें। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप प्रोग्रामेटिक रूप से अपने Word दस्तावेज़ों में फ़्लोटिंग टेबल की स्थिति गुण प्राप्त कर सकते हैं। यह सुविधा आपको अपनी विशिष्ट आवश्यकताओं के अनुसार फ़्लोटिंग तालिकाओं का विश्लेषण और हेरफेर करने की अनुमति देती है।