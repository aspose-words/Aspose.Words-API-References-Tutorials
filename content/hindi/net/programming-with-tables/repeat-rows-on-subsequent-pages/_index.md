---
title: अगले पृष्ठों पर पंक्तियाँ दोहराएँ
linktitle: अगले पृष्ठों पर पंक्तियाँ दोहराएँ
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में बाद के पृष्ठों पर तालिका पंक्तियों को दोहराना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ के बाद के पृष्ठों पर तालिका की पंक्तियों को कैसे दोहराया जाए। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण दर चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत तक, आप अपने Word दस्तावेज़ों में अपनी तालिका के बाद के पृष्ठों पर दोहराने के लिए पंक्तियाँ निर्दिष्ट करने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. विज़ुअल स्टूडियो लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ बनाना और दस्तावेज़ जनरेटर प्रारंभ करना
दस्तावेज़ और दस्तावेज़ जनरेटर के साथ वर्ड प्रोसेसिंग शुरू करने के लिए, इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ निर्माण
Document doc = new Document();

// दस्तावेज़ जेनरेटर प्रारंभ करें
DocumentBuilder builder = new DocumentBuilder(doc);
```

अपने दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ "आपकी दस्तावेज़ निर्देशिका" को बदलना सुनिश्चित करें।

## चरण 3: बार-बार पंक्तियों के साथ तालिका बनाना
इसके बाद, हम अगले पृष्ठों पर दोहराई गई पंक्तियों वाली एक तालिका बनाएंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
// तालिका की शुरुआत
builder. StartTable();

// पहली पंक्ति के मापदंडों का विन्यास (हेडर लाइनें)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

// पहली पंक्ति का पहला सेल डालें
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// पहली पंक्ति का दूसरा सेल डालें
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// निम्नलिखित पंक्तियों के पैरामीटर कॉन्फ़िगर करें
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// निम्नलिखित पंक्तियों में सेलों को सम्मिलित करने के लिए लूप करें
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// तालिका का अंत
builder. EndTable();
```

 यहां हम दो हेडर पंक्तियों और एकाधिक डेटा पंक्तियों वाली तालिका बनाने के लिए दस्तावेज़ बिल्डर का उपयोग करते हैं।`RowFormat.HeadingFormat`पैरामीटर का उपयोग हेडर पंक्तियों को चिह्नित करने के लिए किया जाता है जिन्हें बाद के पृष्ठों पर दोहराया जाना चाहिए।

## चरण 4: संशोधित दस्तावेज़ को सहेजना
अंततः यू.एस

  तालिका के बाद के पृष्ठों पर दोहराई गई हेडर पंक्तियों के साथ संशोधित दस्तावेज़ को सहेजने की आवश्यकता है। निम्नलिखित कोड का प्रयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके बाद के पृष्ठों पर दोहराई जाने वाली पंक्तियों के लिए नमूना स्रोत कोड 

```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ के बाद के पृष्ठों पर तालिका की पंक्तियों को कैसे दोहराया जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप निर्दिष्ट कर सकते हैं कि आपके Word दस्तावेज़ों में आपकी विशिष्ट आवश्यकताओं के अनुसार कौन सी पंक्तियों को दोहराना है।