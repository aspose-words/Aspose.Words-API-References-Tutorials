---
title: तालिका सामग्री संरेखण के साथ मार्कडाउन में निर्यात करें
linktitle: तालिका सामग्री संरेखण के साथ मार्कडाउन में निर्यात करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके विभिन्न संरेखण वाली तालिका सामग्री को मार्कडाउन फ़ाइलों में निर्यात करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
यहाँ निम्नलिखित C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है जो .NET के लिए Aspose.Words लाइब्रेरी का उपयोग करके टेबल सामग्री संरेखण के साथ मार्कडाउन फ़ाइल में सामग्री निर्यात करने में मदद करती है। सुनिश्चित करें कि आपने इस कोड का उपयोग करने से पहले अपने प्रोजेक्ट में Aspose.Words लाइब्रेरी को शामिल किया है।

## चरण 1: दस्तावेज़ निर्देशिका पथ सेट करें

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

अपने दस्तावेज़ निर्देशिका का सही पथ निर्दिष्ट करना सुनिश्चित करें जहां संपादित दस्तावेज़ सहेजा जाएगा।

## चरण 2: एक दस्तावेज़ और एक दस्तावेज़ जनरेटर बनाएँ

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 यहाँ हम इसका एक उदाहरण बनाते हैं`Document` वर्ग और इसका एक उदाहरण`DocumentBuilder` क्लास जो हमें दस्तावेज़ में हेरफेर करने और तत्व जोड़ने की अनुमति देगा।

## चरण 3: तालिका में अलग-अलग पैराग्राफ संरेखण वाले कक्ष सम्मिलित करें

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

हम तालिका में कक्षों को सम्मिलित करने और प्रत्येक कक्ष के लिए अलग-अलग पैराग्राफ संरेखण सेट करने के लिए दस्तावेज़ बिल्डर का उपयोग करते हैं।

## चरण 4: मार्कडाउन निर्यात विकल्प सेट करें और संशोधित दस्तावेज़ सहेजें

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

हम विभिन्न तालिका सामग्री संरेखण के साथ मार्कडाउन निर्यात विकल्प सेट करते हैं, फिर प्रत्येक संरेखण विकल्प का उपयोग करके संशोधित दस्तावेज़ को सहेजते हैं।

### .NET के लिए Aspose.Words का उपयोग करके तालिका सामग्री संरेखण के साथ मार्कडाउन में निर्यात करने के लिए उदाहरण स्रोत कोड

```csharp

            
	// दस्तावेज़ निर्देशिका का पथ.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// तालिका के अंदर सभी पैराग्राफों को संरेखित करता है।
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// इस मामले में संरेखण संबंधित तालिका कॉलम के पहले पैराग्राफ से लिया जाएगा।
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// संशोधित दस्तावेज़ सहेजें
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
