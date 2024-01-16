---
title: हेडर फूटर बनाएं
linktitle: हेडर फूटर बनाएं
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ अपने Word दस्तावेज़ों में शीर्षलेख और पादलेख बनाना सीखें। प्रत्येक पृष्ठ के लिए शीर्षलेख और पादलेख अनुकूलित करें।
type: docs
weight: 10
url: /hi/net/working-with-headers-and-footers/create-header-footer/
---

.NET कार्यक्षमता के लिए Aspose.Words का उपयोग करके हेडर और फ़ुटर बनाने के लिए निम्नलिखित C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका यहां दी गई है। सुनिश्चित करें कि आपने इस कोड का उपयोग करने से पहले Aspose.Words लाइब्रेरी को अपने प्रोजेक्ट में शामिल कर लिया है।

## चरण 1: दस्तावेज़ निर्देशिका पथ सेट करें

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

अपनी दस्तावेज़ निर्देशिका के लिए सही पथ निर्दिष्ट करना सुनिश्चित करें जहां संपादित दस्तावेज़ सहेजा जाएगा।

## चरण 2: एक दस्तावेज़ और एक दस्तावेज़ जनरेटर बनाएं

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 यहां हम इसका एक उदाहरण बनाते हैं`Document` वर्ग और इसका एक उदाहरण`DocumentBuilder` वर्ग जो हमें दस्तावेज़ में हेरफेर करने और तत्व जोड़ने की अनुमति देगा।

## चरण 3: पेज पैरामीटर और पहला हेडर सेट करें

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// निर्दिष्ट करें कि क्या हम चाहते हैं कि पहले पृष्ठ के शीर्षलेख/पादलेख अन्य पृष्ठों से भिन्न हों।
// निर्दिष्ट करने के लिए आप PageSetup.OddAndEvenPagesHeaderFooter प्रॉपर्टी का भी उपयोग कर सकते हैं
// विषम और सम पृष्ठों के लिए अलग-अलग शीर्षलेख/पादलेख।
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

हम हेडर दूरी सहित पेज पैरामीटर सेट करते हैं, और फिर मुख्य हेडर पर जाते हैं (`HeaderPrimary`). हम टेक्स्ट जोड़ने और हेडर को फ़ॉर्मेट करने के लिए दस्तावेज़ जनरेटर का उपयोग करते हैं।

## चरण 4: मुख्य हेडर में एक छवि और टेक्स्ट डालें

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

हम मुख्य हेडर के ऊपरी बाएँ कोने में एक छवि डालने के लिए दस्तावेज़ जनरेटर का उपयोग करते हैं, फिर हम कुछ दाएँ-संरेखित पाठ जोड़ते हैं।

## चरण 5: मुख्य पाद लेख में एक तालिका डालें

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();
```

## चरण 6: एक नया पृष्ठ जोड़ें और शीर्षलेख/पादलेख सेट करें

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// इस अनुभाग को पहले पृष्ठ के लिए किसी भिन्न शीर्षलेख/पादलेख की आवश्यकता नहीं है, हमें दस्तावेज़ में केवल एक शीर्षक पृष्ठ की आवश्यकता है,
//और इस पृष्ठ के लिए शीर्ष लेख/पाद लेख को पिछले अनुभाग में पहले ही परिभाषित किया जा चुका है।
pageSetup.DifferentFirstPageHeaderFooter = false;

// यह अनुभाग डिफ़ॉल्ट रूप से पिछले अनुभाग के शीर्षलेख/पादलेख प्रदर्शित करता है, इस लिंक को तोड़ने के लिए currentSection.HeadersFooters.LinkToPrevious(false) पर कॉल करें,
// नए अनुभाग के लिए पृष्ठ की चौड़ाई अलग है, इसलिए हमें पादलेख तालिका के लिए अलग-अलग सेल चौड़ाई निर्धारित करने की आवश्यकता है।
currentSection.HeadersFooters.LinkToPrevious(false);

// यदि हम इस अनुभाग के लिए पहले से मौजूद शीर्षलेख/पादलेख का उपयोग करना चाहते हैं,
//लेकिन कुछ छोटे बदलावों के साथ, हेडर/फुटर को कॉपी करना समझदारी भरा हो सकता है
// पिछले अनुभाग से और आवश्यक परिवर्तन वहां लागू करें जहां हम उन्हें चाहते हैं।
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// दस्तावेज़ सहेजें
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 हम एक नया पेज बनाने के लिए एक पेज ब्रेक और एक सेक्शन ब्रेक जोड़ते हैं जहां प्राथमिक हेडर/फुटर दिखाई देंगे। हम नए अनुभाग के लिए पैरामीटर सेट करते हैं, फिर हम इसका उपयोग करते हैं`CopyHeadersFootersFromPreviousSection` पिछले अनुभाग से शीर्ष लेख/पाद लेख कॉपी करने की विधि। अंत में, हम मुख्य पाद लेख तालिका के लिए उपयुक्त सेल चौड़ाई निर्धारित करते हैं और दस्तावेज़ को सहेजते हैं।

### .NET के लिए Aspose.Words के साथ हेडर और फ़ूटर बनाने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// निर्दिष्ट करें कि क्या हम चाहते हैं कि पहले पृष्ठ के शीर्षलेख/पादलेख अन्य पृष्ठों से भिन्न हों।
// निर्दिष्ट करने के लिए आप PageSetup.OddAndEvenPagesHeaderFooter प्रॉपर्टी का भी उपयोग कर सकते हैं
// विषम और सम पृष्ठों के लिए अलग-अलग शीर्षलेख/पादलेख।
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

pageSetup.HeaderDistance = 20;
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// हेडर के ऊपरी/बाएँ कोने में एक स्थित छवि डालें।
// पृष्ठ के शीर्ष/बाएँ किनारों से दूरी 10 अंक पर सेट है।
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// हम पंक्ति पर पाठ का एक भाग (पृष्ठ क्रमांकन के साथ) बनाने के लिए दो कक्षों वाली एक तालिका का उपयोग करते हैं।
// बाईं ओर संरेखित किया जाना है, और पाठ का दूसरा भाग (कॉपीराइट के साथ) दाईं ओर संरेखित किया जाना है।
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// यह वर्तमान पृष्ठ संख्या और कई पृष्ठों की स्वतः गणना करने के लिए PAGE और NUMPAGES फ़ील्ड का उपयोग करता है।
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();

// दूसरा पृष्ठ बनाने के लिए एक पृष्ठ विराम बनाएं जिस पर प्राथमिक शीर्षलेख/पादलेख दिखाई देंगे।
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// इस अनुभाग को किसी भिन्न प्रथम पृष्ठ शीर्षलेख/पाद लेख की आवश्यकता नहीं है, हमें दस्तावेज़ में केवल एक शीर्षक पृष्ठ की आवश्यकता है,
//और इस पृष्ठ के लिए शीर्ष लेख/पाद लेख को पिछले अनुभाग में पहले ही परिभाषित किया जा चुका है।
pageSetup.DifferentFirstPageHeaderFooter = false;

// यह अनुभाग पिछले अनुभाग के शीर्षलेख/पादलेख प्रदर्शित करता है
// इस पृष्ठ की चौड़ाई को रद्द करने के लिए डिफ़ॉल्ट रूप से currentSection.HeadersFooters.LinkToPrevious(false) पर कॉल करें
// नए अनुभाग के लिए अलग है, और इसलिए हमें पादलेख तालिका के लिए अलग-अलग सेल चौड़ाई निर्धारित करने की आवश्यकता है।
currentSection.HeadersFooters.LinkToPrevious(false);

// यदि हम इस सेक्शन के लिए पहले से मौजूद हेडर/फुटर सेट का उपयोग करना चाहते हैं।
// लेकिन कुछ मामूली संशोधनों के साथ, हेडर/फुटर को कॉपी करना समीचीन हो सकता है
// पिछले अनुभाग से और आवश्यक संशोधनों को वहां लागू करें जहां हम उन्हें चाहते हैं।
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words में अपने दस्तावेज़ में हेडर कैसे जोड़ सकता हूँ?

 उ: Aspose.Words में अपने दस्तावेज़ में हेडर जोड़ने के लिए, आप इसका उपयोग कर सकते हैं`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` तरीका। यह विधि आपके दस्तावेज़ के पहले खंड में एक प्राथमिक शीर्षक जोड़ती है।

#### प्रश्न: मैं Aspose.Words में अपने दस्तावेज़ में पादलेख कैसे जोड़ सकता हूँ?

 उ: Aspose.Words में अपने दस्तावेज़ में पाद लेख जोड़ने के लिए, आप इसका उपयोग कर सकते हैं`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)`तरीका। यह विधि आपके दस्तावेज़ के पहले खंड में एक प्राथमिक पाद लेख जोड़ती है।

#### प्रश्न: मैं Aspose.Words में अपने शीर्षलेख या पादलेख में टेक्स्ट कैसे जोड़ सकता हूं?

 उत्तर: Aspose.Words में अपने हेडर या फ़ूटर में टेक्स्ट जोड़ने के लिए, आप इसका उपयोग कर सकते हैं`HeaderFooter.Paragraphs` शीर्ष लेख या पाद लेख का पैराग्राफ संग्रह प्राप्त करने के लिए प्रॉपर्टी, फिर इस संग्रह का उपयोग करके अपने टेक्स्ट वाला एक पैराग्राफ जोड़ें`ParagraphCollection.Add` तरीका।

#### प्रश्न: क्या मैं Aspose.Words में हेडर या फ़ूटर सामग्री को छवियों और पृष्ठ संख्याओं के साथ अनुकूलित कर सकता हूँ?

 उ: हाँ, आप Aspose.Words में छवियों और पृष्ठ संख्याओं के साथ शीर्ष लेख या पाद लेख सामग्री को अनुकूलित कर सकते हैं। आप जैसी वस्तुओं का उपयोग कर सकते हैं`Shape` जैसी छवियाँ और ऑब्जेक्ट जोड़ने के लिए`Field` अपने शीर्षलेख या पादलेख में पृष्ठ क्रमांक जोड़ने के लिए।

#### प्रश्न: क्या मैं Aspose.Words में अपने हेडर या फ़ूटर में टेक्स्ट का फ़ॉन्ट, आकार और रंग बदल सकता हूँ?

 उत्तर: हां, आप Aspose.Words में अपने हेडर या फ़ूटर में टेक्स्ट का फ़ॉन्ट, आकार और रंग बदल सकते हैं। आप टेक्स्ट फ़ॉर्मेटिंग गुणों जैसे कि एक्सेस कर सकते हैं`Font` फ़ॉन्ट बदलने के लिए,`Size` आकार समायोजित करने के लिए, और`Color`टेक्स्ट का रंग सेट करने के लिए.