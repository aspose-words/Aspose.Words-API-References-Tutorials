---
title: सरल तालिका बनाएं
linktitle: सरल तालिका बनाएं
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में एक सरल तालिका बनाने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/create-simple-table/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में एक सरल तालिका कैसे बनाई जाए। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत में, आप अपने Word दस्तावेज़ों में प्रोग्रामेटिक रूप से कस्टम टेबल बनाने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. Visual Studio लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. Aspose.Words for .NET लाइब्रेरी में संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ बनाना और दस्तावेज़ जनरेटर को आरंभ करना
तालिका बनाना शुरू करने के लिए, हमें एक नया दस्तावेज़ बनाना होगा और दस्तावेज़ बिल्डर को आरंभ करना होगा। इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ बनाएँ और दस्तावेज़ जनरेटर आरंभ करें
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

"आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से प्रतिस्थापित करना सुनिश्चित करें।

## चरण 3: सरणी का निर्माण
इसके बाद, हम दस्तावेज़ बिल्डर द्वारा प्रदान की गई विधियों का उपयोग करके तालिका का निर्माण करेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
// सरणी निर्माण शुरू करें
builder. StartTable();

// पहली पंक्ति के पहले सेल का निर्माण
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// पहली पंक्ति के दूसरे कक्ष का निर्माण
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//पहली पंक्ति को समाप्त करने और नई पंक्ति शुरू करने के लिए निम्नलिखित विधि को कॉल करें
builder. EndRow();

// दूसरी पंक्ति के पहले सेल का निर्माण
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// दूसरी पंक्ति के दूसरे कक्ष का निर्माण
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// दूसरी पंक्ति को समाप्त करने के लिए next विधि को कॉल करें
builder. EndRow();

// संकेत कि तालिका का निर्माण पूरा हो गया है
builder. EndTable();
```

 यहाँ हम टेबल को चरण दर चरण बनाने के लिए डॉक्यूमेंट बिल्डर का उपयोग करते हैं। हम कॉल करके शुरू करते हैं`StartTable()` तालिका को आरंभ करने के लिए, फिर उपयोग करें`InsertCell()` कोशिकाओं को सम्मिलित करने के लिए और`Write()` प्रत्येक सेल में सामग्री जोड़ने के लिए। हम इसका भी उपयोग करते हैं`EndRow()` एक पंक्ति समाप्त करने और एक नई पंक्ति शुरू करने के लिए। अंत में, हम कॉल करते हैं`EndTable()` यह इंगित करने के लिए कि तालिका निर्माण पूरा हो गया है।

## चरण 4: दस्तावेज़ सहेजें
अंततः, हमें बचाने की जरूरत है

  बनाए गए टेबल वाला दस्तावेज़। निम्नलिखित कोड का उपयोग करें:

```csharp
// दस्तावेज़ सहेजें
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके सरल तालिका बनाने के लिए नमूना स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// तालिका बनाना शुरू करें.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// दूसरा कक्ष बनाएं.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// पंक्ति समाप्त करने और नई पंक्ति शुरू करने के लिए निम्नलिखित विधि को कॉल करें।
	builder.EndRow();
	// दूसरी पंक्ति का पहला कक्ष बनाएं।
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// दूसरा कक्ष बनाएं.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//संकेत दें कि हमने तालिका का निर्माण पूरा कर लिया है।
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में एक सरल तालिका कैसे बनाई जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और प्रदान किए गए C# कोड को लागू करके, आप अपने Word दस्तावेज़ों में प्रोग्रामेटिक रूप से कस्टम टेबल बना सकते हैं। यह सुविधा आपको अपने डेटा को संरचित और स्पष्ट तरीके से प्रारूपित और व्यवस्थित करने की अनुमति देती है।