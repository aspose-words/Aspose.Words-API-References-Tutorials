---
title: Word दस्तावेज़ में सामग्री तालिका सम्मिलित करें
linktitle: Word दस्तावेज़ में सामग्री तालिका सम्मिलित करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में सामग्री तालिका सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/add-content-using-documentbuilder/insert-table-of-contents/
---
इस व्यापक ट्यूटोरियल में, आप सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में सामग्री तालिका कैसे सम्मिलित करें। हम प्रक्रिया में आपका मार्गदर्शन करेंगे और आपको आवश्यक C# कोड स्निपेट प्रदान करेंगे। इस गाइड के अंत तक, आप उपयुक्त शीर्षकों और पृष्ठ संख्याओं के साथ सामग्री की एक तालिका तैयार करने में सक्षम होंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- आपके सिस्टम पर .NET लाइब्रेरी के लिए Aspose.Words इंस्टॉल किया गया है।

## चरण 1: एक नया दस्तावेज़ और दस्तावेज़बिल्डर बनाएँ
आरंभ करने के लिए, दस्तावेज़ वर्ग का उपयोग करके एक नया दस्तावेज़ बनाएं और एक दस्तावेज़बिल्डर ऑब्जेक्ट प्रारंभ करें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: सामग्री तालिका सम्मिलित करें
इसके बाद, सामग्री की तालिका सम्मिलित करने के लिए DocumentBuilder वर्ग की InsertTableOfContents विधि का उपयोग करें। विधि के भीतर आवश्यक स्वरूपण विकल्प निर्दिष्ट करें:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## चरण 3: दस्तावेज़ सामग्री जोड़ें
सामग्री तालिका सम्मिलित करने के बाद, वास्तविक दस्तावेज़ सामग्री जोड़ें। StyleIdentifier का उपयोग करके उचित शीर्षक शैलियाँ सेट करें:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## चरण 4: विषय-सूची अद्यतन करें
नई सम्मिलित सामग्री तालिका प्रारंभ में खाली होगी। इसे भरने के लिए, दस्तावेज़ में फ़ील्ड अपडेट करें:

```csharp
doc.UpdateFields();
```

## चरण 5: दस्तावेज़ सहेजें
सामग्री तालिका सम्मिलित करने और फ़ील्ड अपडेट करने के बाद, दस्तावेज़ वर्ग की सेव विधि का उपयोग करके दस्तावेज़ को एक फ़ाइल में सहेजें:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके सामग्री तालिका सम्मिलित करने के लिए उदाहरण स्रोत कोड
.NET के लिए Aspose.Words का उपयोग करके सामग्री तालिका सम्मिलित करने का संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ ऑब्जेक्ट के साथ दस्तावेज़बिल्डर प्रारंभ करें
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// सामग्री की तालिका सम्मिलित करें
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// वास्तविक दस्तावेज़ सामग्री को दूसरे पृष्ठ पर प्रारंभ करें।
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// नई सम्मिलित सामग्री तालिका प्रारंभ में खाली होगी।
// दस्तावेज़ में फ़ील्ड्स को अद्यतन करके इसे भरने की आवश्यकता है।
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में सामग्री तालिका सम्मिलित करना सफलतापूर्वक सीख लिया है। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए स्रोत कोड का उपयोग करके, अब आप अपने दस्तावेज़ों के लिए उपयुक्त शीर्षकों और पृष्ठ संख्याओं के साथ सामग्री की एक तालिका तैयार कर सकते हैं।

### वर्ड दस्तावेज़ में सामग्री तालिका सम्मिलित करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं विषय-सूची के स्वरूप को अनुकूलित कर सकता हूँ?

 उ: हां, आप इसमें निर्दिष्ट फ़ॉर्मेटिंग विकल्पों को संशोधित करके सामग्री तालिका के स्वरूप को अनुकूलित कर सकते हैं`InsertTableOfContents` तरीका। पैरामीटर आपको पृष्ठ संख्या, इंडेंटेशन और अन्य शैलियों को नियंत्रित करने की अनुमति देते हैं।

#### प्रश्न: यदि मैं विषय-सूची में विशिष्ट शीर्षक स्तर शामिल करना चाहूँ तो क्या होगा?

 ए: आप सामग्री की तालिका में शामिल किए जाने वाले वांछित शीर्षक स्तरों को इसके भीतर मूल्य को समायोजित करके निर्दिष्ट कर सकते हैं`InsertTableOfContents` तरीका। उदाहरण के लिए, का उपयोग करना`"\\o \"1-3\""` इसमें शीर्षक स्तर 1 से 3 शामिल होंगे।

#### प्रश्न: यदि मैं दस्तावेज़ की सामग्री में परिवर्तन करता हूँ तो क्या मैं सामग्री तालिका को स्वचालित रूप से अपडेट कर सकता हूँ?

 उत्तर: हां, आप कॉल करके सामग्री तालिका को स्वचालित रूप से अपडेट कर सकते हैं`UpdateFields` दस्तावेज़ पर विधि. इससे यह सुनिश्चित हो जाएगा कि दस्तावेज़ की सामग्री में किए गए कोई भी बदलाव, जैसे शीर्षक जोड़ना या हटाना, सामग्री की तालिका में प्रतिबिंबित होंगे।

#### प्रश्न: मैं विषय-सूची में शीर्षक स्तरों को अलग ढंग से कैसे शैलीबद्ध कर सकता हूँ?

 उ: आप प्रत्येक शीर्षक स्तर के लिए अलग-अलग अनुच्छेद शैलियों का उपयोग करके शीर्षक स्तरों को अलग-अलग शैली दे सकते हैं। अलग-अलग नियुक्त करके`StyleIdentifier` मूल्यों को`ParagraphFormat` की`DocumentBuilder`, आप प्रत्येक शीर्षक स्तर के लिए अलग-अलग शैलियाँ बना सकते हैं।

#### प्रश्न: क्या विषय-सूची में शीर्षकों में अतिरिक्त स्वरूपण जोड़ना संभव है?

 उ: हां, आप सामग्री तालिका में शीर्षकों में अतिरिक्त स्वरूपण जोड़ सकते हैं, जैसे फ़ॉन्ट शैली, रंग, या अन्य गुण। का समायोजन करके`Font` के गुण`DocumentBuilder`, आप शीर्षकों पर कस्टम फ़ॉर्मेटिंग लागू कर सकते हैं।