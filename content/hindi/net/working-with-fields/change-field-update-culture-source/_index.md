---
title: फ़ील्ड बदलें अद्यतन संस्कृति स्रोत
linktitle: फ़ील्ड बदलें अद्यतन संस्कृति स्रोत
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: फील्ड अपडेट संस्कृति स्रोत बदलें, .NET के लिए Aspose.Words में संस्कृति स्रोत को संशोधित करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/working-with-fields/change-field-update-culture-source/
---

इस ट्यूटोरियल में, हम .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में फ़ील्ड अपडेट कल्चर स्रोत को बदलने की प्रक्रिया में आपका मार्गदर्शन करेंगे। संस्कृति स्रोत को संशोधित करके, आप फ़ील्ड अद्यतन और मेल मर्ज संचालन के दौरान दिनांक स्वरूपण को नियंत्रित कर सकते हैं। इसे प्राप्त करने के लिए हम आपको आवश्यक C# स्रोत कोड और चरण-दर-चरण निर्देश प्रदान करेंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- आपके सिस्टम पर .NET लाइब्रेरी के लिए Aspose.Words इंस्टॉल किया गया है।

## चरण 1: एक दस्तावेज़ और दस्तावेज़बिल्डर बनाएँ
आरंभ करने के लिए, दस्तावेज़ वर्ग और दस्तावेज़बिल्डर ऑब्जेक्ट का एक उदाहरण बनाएं:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: विशिष्ट स्थान के साथ सामग्री सम्मिलित करें
इसके बाद, स्थान को जर्मन में सेट करें और दिनांक स्वरूपण के साथ फ़ील्ड डालें:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

उपरोक्त कोड में, हम फ़ॉन्ट लोकेल को जर्मन (लोकेल आईडी 1031) पर सेट करते हैं और विशिष्ट दिनांक स्वरूपण के साथ दो फ़ील्ड सम्मिलित करते हैं।

## चरण 3: फ़ील्ड अपडेट संस्कृति स्रोत बदलें
फ़ील्ड अद्यतन संस्कृति स्रोत को बदलने के लिए, फ़ील्डऑप्शन क्लास का उपयोग करें:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

इस उदाहरण में, हम फ़ील्ड अपडेट के दौरान उपयोग की जाने वाली संस्कृति को फ़ील्ड द्वारा उपयोग की जाने वाली संस्कृति से चुनने के लिए सेट करते हैं।

## चरण 4: मेल मर्ज करें
मेल मर्ज ऑपरेशन करें और "दिनांक2" फ़ील्ड के लिए दिनांक मान निर्दिष्ट करें:

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

इस कोड स्निपेट में, हम मेल मर्ज ऑपरेशन निष्पादित करते हैं और "Date2" फ़ील्ड के लिए DateTime मान प्रदान करते हैं।

## चरण 5: दस्तावेज़ सहेजें
दस्तावेज़ वर्ग की सेव विधि का उपयोग करके संशोधित दस्तावेज़ को फ़ाइल में सहेजें:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके फ़ील्ड अपडेट संस्कृति स्रोत को बदलने के लिए उदाहरण स्रोत कोड
.NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में फ़ील्ड अपडेट संस्कृति स्रोत को बदलने के लिए संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## निष्कर्ष
बधाई हो! आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में फ़ील्ड अपडेट कल्चर स्रोत को कैसे बदला जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए स्रोत कोड का उपयोग करके, अब आप फ़ील्ड अपडेट और मेल मर्ज संचालन के दौरान दिनांक स्वरूपण के लिए उपयोग की जाने वाली संस्कृति को नियंत्रित कर सकते हैं। सटीक और सुसंगत तिथि सुनिश्चित करने के लिए संस्कृति स्रोत को अपनी आवश्यकताओं के अनुसार अनुकूलित करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं .NET के लिए Aspose.Words में फ़ील्ड अपडेट कल्चर स्रोत को कैसे बदल सकता हूँ?

 उ: .NET के लिए Aspose.Words में फ़ील्ड अपडेट कल्चर स्रोत को बदलने के लिए, आप इसका उपयोग कर सकते हैं`Document.FieldOptions.CultureSource` संपत्ति और उसका मूल्य निर्धारित करें`FieldCultureSource.FieldCode` या`FieldCultureSource.CurrentThread` . उदाहरण के लिए, आप उपयोग कर सकते हैं`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` फ़ील्ड कोड में परिभाषित संस्कृति का उपयोग करना।

#### प्रश्न: मैं .NET के लिए Aspose.Words में फ़ील्ड अपडेट करने के लिए एक विशिष्ट संस्कृति कैसे निर्दिष्ट कर सकता हूं?

 उ: .NET के लिए Aspose.Words में फ़ील्ड अपडेट करने के लिए एक विशिष्ट संस्कृति निर्दिष्ट करने के लिए, आप इसका उपयोग कर सकते हैं`Document.FieldOptions.FieldUpdateCultureInfo` संपत्ति और सेट करें`CultureInfo` वांछित संस्कृति के अनुरूप वस्तु। उदाहरण के लिए, आप उपयोग कर सकते हैं`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` फ़्रेंच (फ्रांस) संस्कृति को निर्दिष्ट करने के लिए।

#### प्रश्न: क्या .NET के लिए Aspose.Words में स्वचालित फ़ील्ड अपडेट को अक्षम करना संभव है?

 उत्तर: हां, .NET के लिए Aspose.Words में स्वचालित फ़ील्ड अपडेट को अक्षम करना संभव है। आप इसका उपयोग कर सकते हैं`Document.FieldOptions.UpdateFields` संपत्ति और इसे सेट करें`false` फ़ील्ड्स को स्वतः अपडेट होने से रोकने के लिए। यह आपको आवश्यकतानुसार फ़ील्ड के अद्यतन को मैन्युअल रूप से नियंत्रित करने की अनुमति देता है।

#### प्रश्न: मैं .NET के लिए Aspose.Words में दस्तावेज़ फ़ील्ड को मैन्युअल रूप से कैसे अपडेट कर सकता हूं?

 उ: .NET के लिए Aspose.Words में किसी दस्तावेज़ में फ़ील्ड को मैन्युअल रूप से अपडेट करने के लिए, आप इसका उपयोग कर सकते हैं`Field.Update` प्रत्येक क्षेत्र के लिए अलग-अलग विधि। उदाहरण के लिए, आप उपयोग कर सकते हैं`field.Update()` विशिष्ट फ़ील्ड को अद्यतन करने के लिए.