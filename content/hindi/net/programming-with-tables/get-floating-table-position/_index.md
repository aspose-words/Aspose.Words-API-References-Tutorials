---
title: फ़्लोटिंग टेबल स्थिति प्राप्त करें
linktitle: फ़्लोटिंग टेबल स्थिति प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में फ़्लोटिंग तालिकाओं की स्थिति प्राप्त करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/get-floating-table-position/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में फ़्लोटिंग टेबल की स्थिति कैसे प्राप्त करें। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत में, आप अपने Word दस्तावेज़ों में फ़्लोटिंग टेबल की स्थिति गुणों को प्रोग्रामेटिक रूप से प्राप्त करने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. Visual Studio लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. Aspose.Words for .NET लाइब्रेरी में संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ लोड करना और तालिकाओं तक पहुँचना
तालिकाओं के साथ वर्ड प्रोसेसिंग शुरू करने के लिए, हमें उस दस्तावेज़ को लोड करना होगा जिसमें वे शामिल हैं और उन्हें एक्सेस करना होगा। इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

"आपकी दस्तावेज़ निर्देशिका" को अपने दस्तावेज़ निर्देशिका के वास्तविक पथ से बदलना सुनिश्चित करें। साथ ही, सुनिश्चित करें कि दस्तावेज़ में फ़्लोटिंग टेबल शामिल हैं।

## चरण 3: फ्लोटिंग टेबल पोजिशनिंग गुण प्राप्त करना
इसके बाद, हम दस्तावेज़ में सभी तालिकाओं को लूप करेंगे और फ़्लोटिंग टेबल पोजिशनिंग गुण प्राप्त करेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// यदि सरणी फ़्लोटिंग प्रकार की है, तो उसके स्थिति निर्धारण गुणों को प्रिंट करें।
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

 यहाँ हम एक का उपयोग कर रहे हैं`foreach` दस्तावेज़ में सभी सरणियों के माध्यम से लूप करने के लिए लूप। हम जाँच करके जाँचते हैं कि क्या सरणी फ़्लोट प्रकार की है`TextWrapping` संपत्ति। यदि ऐसा है, तो हम तालिका की स्थिति गुणों को प्रिंट करते हैं, जैसे क्षैतिज एंकर, ऊर्ध्वाधर एंकर, पूर्ण क्षैतिज और ऊर्ध्वाधर दूरी, ओवरलैपिंग अनुमति, पूर्ण क्षैतिज दूरी और ऊर्ध्वाधर संरेखण सापेक्ष।
 
### .NET के लिए Aspose.Words का उपयोग करके फ्लोटिंग टेबल स्थिति प्राप्त करने के लिए नमूना स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// यदि तालिका फ़्लोटिंग प्रकार की है, तो उसके स्थिति निर्धारण गुणों को प्रिंट करें।
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
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में फ़्लोटिंग टेबल की स्थिति कैसे प्राप्त करें। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और प्रदान किए गए C# कोड को लागू करके, आप अपने Word दस्तावेज़ों में फ़्लोटिंग टेबल की स्थिति गुणधर्मों को प्रोग्रामेटिक रूप से प्राप्त कर सकते हैं। यह सुविधा आपको अपनी विशिष्ट आवश्यकताओं के अनुसार फ़्लोटिंग टेबल का विश्लेषण और हेरफेर करने की अनुमति देती है।