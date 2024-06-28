---
title: हेडर फूटर बनाएं
linktitle: हेडर फूटर बनाएं
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में शीर्षलेख और पादलेख जोड़ने और अनुकूलित करने का तरीका जानें। यह चरण-दर-चरण मार्गदर्शिका पेशेवर दस्तावेज़ स्वरूपण सुनिश्चित करती है।
type: docs
weight: 10
url: /hi/net/working-with-headers-and-footers/create-header-footer/
---

अपने दस्तावेज़ों में शीर्षलेख और पादलेख जोड़ने से उनकी व्यावसायिकता और पठनीयता बढ़ सकती है। .NET के लिए Aspose.Words के साथ, आप अपने Word दस्तावेज़ों के लिए हेडर और फ़ुटर आसानी से बना और अनुकूलित कर सकते हैं। इस ट्यूटोरियल में, हम आपको चरण दर चरण प्रक्रिया के बारे में बताएंगे, यह सुनिश्चित करते हुए कि आप इन सुविधाओं को निर्बाध रूप से लागू कर सकते हैं।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

-  .NET के लिए Aspose.Words: से डाउनलोड और इंस्टॉल करें[लिंक को डाउनलोड करें](https://releases.aspose.com/words/net/).
- विकास परिवेश: जैसे कि विज़ुअल स्टूडियो, अपना कोड लिखने और चलाने के लिए।
- C# का बुनियादी ज्ञान: C# और .NET ढांचे की समझ।
- नमूना दस्तावेज़: शीर्षलेख और पादलेख लागू करने या एक नया दस्तावेज़ बनाने के लिए एक नमूना दस्तावेज़, जैसा कि ट्यूटोरियल में दिखाया गया है।

## नामस्थान आयात करें

सबसे पहले, आपको Aspose.Words कक्षाओं और विधियों तक पहुंचने के लिए आवश्यक नामस्थान आयात करने की आवश्यकता है।

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using System;
```

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें

उस निर्देशिका को परिभाषित करें जहां आपका दस्तावेज़ सहेजा जाएगा। इससे पथ को प्रभावी ढंग से प्रबंधित करने में मदद मिलती है.

```csharp
// दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

## चरण 2: एक नया दस्तावेज़ बनाएँ

 एक नया दस्तावेज़ बनाएं और a`DocumentBuilder` सामग्री जोड़ने की सुविधा के लिए.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: पेज सेटअप कॉन्फ़िगर करें

पेज सेटिंग सेट करें, जिसमें यह भी शामिल है कि क्या पहले पेज पर अलग हेडर/फुटर होगा।

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;
```

## चरण 4: प्रथम पृष्ठ पर एक शीर्षलेख जोड़ें

पहले पृष्ठ के हेडर अनुभाग पर जाएँ और हेडर टेक्स्ट को कॉन्फ़िगर करें।

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

## चरण 5: एक प्राथमिक शीर्षलेख जोड़ें

प्राथमिक हेडर अनुभाग पर जाएँ और एक छवि और टेक्स्ट डालें।

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// हेडर में एक छवि डालें
builder.InsertImage(dataDir + "Graphics Interchange Format.gif", 
    RelativeHorizontalPosition.Page, 10, RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Aspose.Words Header/Footer Creation Primer.");
```

## चरण 6: एक प्राथमिक पादलेख जोड़ें

प्राथमिक पाद लेख अनुभाग पर जाएँ और पाद लेख सामग्री को प्रारूपित करने के लिए एक तालिका बनाएँ।

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

builder.StartTable();
builder.CellFormat.ClearFormatting();
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// पृष्ठ क्रमांकन जोड़ें
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
```

## चरण 7: सामग्री और पेज ब्रेक जोड़ें

दस्तावेज़ के अंत में जाएँ, एक पृष्ठ विराम जोड़ें, और विभिन्न पृष्ठ सेटिंग्स के साथ एक नया अनुभाग बनाएँ।

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
pageSetup.DifferentFirstPageHeaderFooter = false;

currentSection.HeadersFooters.LinkToPrevious(false);
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];
Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

## चरण 8: पिछले अनुभाग से शीर्षलेख और पाद लेख कॉपी करें

यदि आप पिछले अनुभाग से शीर्षलेख और पादलेख का पुन: उपयोग करना चाहते हैं, तो उन्हें कॉपी करें और आवश्यक संशोधन लागू करें।

```csharp
private static void CopyHeadersFootersFromPreviousSection(Section section)
{
    Section previousSection = (Section)section.PreviousSibling;
    if (previousSection == null) return;

    section.HeadersFooters.Clear();

    foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    {
        section.HeadersFooters.Add(headerFooter.Clone(true));
    }
}
```

## निष्कर्ष

इन चरणों का पालन करके, आप .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ों में हेडर और फ़ुटर को प्रभावी ढंग से जोड़ और अनुकूलित कर सकते हैं। यह आपके दस्तावेज़ की उपस्थिति और व्यावसायिकता को बढ़ाता है, जिससे यह अधिक पठनीय और आकर्षक बन जाता है।

## पूछे जाने वाले प्रश्न

### Q1: .NET के लिए Aspose.Words क्या है?

.NET के लिए Aspose.Words एक लाइब्रेरी है जो डेवलपर्स को .NET अनुप्रयोगों के भीतर प्रोग्रामेटिक रूप से Word दस्तावेज़ बनाने, संपादित करने और परिवर्तित करने में सक्षम बनाती है।

### Q2: क्या मैं शीर्षलेख या पादलेख में छवियाँ जोड़ सकता हूँ?

 हां, आप इसका उपयोग करके आसानी से हेडर या फ़ूटर में छवियां जोड़ सकते हैं`DocumentBuilder.InsertImage` तरीका।

### Q3: मैं पहले पृष्ठ के लिए अलग-अलग शीर्षलेख और पादलेख कैसे सेट करूं?

 आप इसका उपयोग करके पहले पृष्ठ के लिए अलग-अलग शीर्षलेख और पादलेख सेट कर सकते हैं`DifferentFirstPageHeaderFooter` की संपत्ति`PageSetup` कक्षा।

### Q4: मुझे Aspose.Words पर अधिक दस्तावेज़ कहां मिल सकते हैं?

 आप इस पर व्यापक दस्तावेज़ पा सकते हैं[Aspose.Words API दस्तावेज़ीकरण पृष्ठ](https://reference.aspose.com/words/net/).

### Q5: क्या Aspose.Words के लिए समर्थन उपलब्ध है?

 हाँ, Aspose उनके माध्यम से सहायता प्रदान करता है[सहयता मंच](https://forum.aspose.com/c/words/8).
