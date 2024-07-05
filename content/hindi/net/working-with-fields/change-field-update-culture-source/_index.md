---
title: फ़ील्ड बदलें संस्कृति स्रोत अपडेट करें
linktitle: फ़ील्ड बदलें संस्कृति स्रोत अपडेट करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: फ़ील्ड अपडेट संस्कृति स्रोत बदलें, .NET के लिए Aspose.Words में संस्कृति स्रोत को संशोधित करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/working-with-fields/change-field-update-culture-source/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में फ़ील्ड अपडेट कल्चर स्रोत को बदलने की प्रक्रिया के माध्यम से मार्गदर्शन करेंगे। कल्चर स्रोत को संशोधित करके, आप फ़ील्ड अपडेट और मेल मर्ज ऑपरेशन के दौरान दिनांक स्वरूपण को नियंत्रित कर सकते हैं। हम आपको इसे प्राप्त करने के लिए आवश्यक C# स्रोत कोड और चरण-दर-चरण निर्देश प्रदान करेंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- आपके सिस्टम पर Aspose.Words for .NET लाइब्रेरी स्थापित है।

## चरण 1: दस्तावेज़ और दस्तावेज़बिल्डर बनाएँ
आरंभ करने के लिए, Document वर्ग और DocumentBuilder ऑब्जेक्ट का एक उदाहरण बनाएं:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: विशिष्ट स्थान के साथ सामग्री सम्मिलित करें
इसके बाद, स्थानीय भाषा को जर्मन पर सेट करें और दिनांक स्वरूपण के साथ फ़ील्ड डालें:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

उपरोक्त कोड में, हमने फ़ॉन्ट लोकेल को जर्मन (लोकेल आईडी 1031) पर सेट किया है और विशिष्ट दिनांक स्वरूपण के साथ दो फ़ील्ड सम्मिलित किए हैं।

## चरण 3: फ़ील्ड अपडेट संस्कृति स्रोत बदलें
फ़ील्ड अपडेट कल्चर स्रोत को बदलने के लिए, FieldOptions वर्ग का उपयोग करें:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

इस उदाहरण में, हमने फ़ील्ड अद्यतन के दौरान प्रयुक्त संस्कृति को फ़ील्ड द्वारा प्रयुक्त संस्कृति में से चुनने के लिए सेट किया है।

## चरण 4: मेल मर्ज करें
मेल मर्ज ऑपरेशन निष्पादित करें और "Date2" फ़ील्ड के लिए दिनांक मान निर्दिष्ट करें:

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

इस कोड स्निपेट में, हम मेल मर्ज ऑपरेशन निष्पादित करते हैं और "Date2" फ़ील्ड के लिए DateTime मान प्रदान करते हैं।

## चरण 5: दस्तावेज़ सहेजें
Document वर्ग की Save विधि का उपयोग करके संशोधित दस्तावेज़ को फ़ाइल में सहेजें:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके फ़ील्ड अपडेट कल्चर स्रोत बदलने के लिए उदाहरण स्रोत कोड
.NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में फ़ील्ड अपडेट कल्चर स्रोत को बदलने के लिए यहां पूर्ण स्रोत कोड दिया गया है:

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
बधाई हो! आपने सफलतापूर्वक सीख लिया है कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ों में फ़ील्ड अपडेट कल्चर स्रोत को कैसे बदला जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और प्रदान किए गए स्रोत कोड का उपयोग करके, अब आप फ़ील्ड अपडेट और मेल मर्ज संचालन के दौरान दिनांक स्वरूपण के लिए उपयोग की जाने वाली संस्कृति को नियंत्रित कर सकते हैं। सटीक और सुसंगत तिथि सुनिश्चित करने के लिए अपनी आवश्यकताओं के अनुसार संस्कृति स्रोत को अनुकूलित करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words for .NET में फ़ील्ड अपडेट कल्चर स्रोत को कैसे बदल सकता हूँ?

 A: Aspose.Words for .NET में फ़ील्ड अपडेट कल्चर स्रोत को बदलने के लिए, आप इसका उपयोग कर सकते हैं`Document.FieldOptions.CultureSource` संपत्ति और उसका मूल्य निर्धारित करें`FieldCultureSource.FieldCode` या`FieldCultureSource.CurrentThread` उदाहरण के लिए, आप उपयोग कर सकते हैं`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` क्षेत्र कोड में परिभाषित संस्कृति का उपयोग करने के लिए।

#### प्रश्न: मैं .NET के लिए Aspose.Words में फ़ील्ड्स को अपडेट करने के लिए एक विशिष्ट संस्कृति कैसे निर्दिष्ट कर सकता हूं?

 A: Aspose.Words for .NET में फ़ील्ड्स को अपडेट करने के लिए एक विशिष्ट संस्कृति निर्दिष्ट करने के लिए, आप इसका उपयोग कर सकते हैं`Document.FieldOptions.FieldUpdateCultureInfo` संपत्ति और सेट करें`CultureInfo` वांछित संस्कृति के अनुरूप वस्तु। उदाहरण के लिए, आप उपयोग कर सकते हैं`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` फ्रांसीसी (फ्रांस) संस्कृति को निर्दिष्ट करने के लिए।

#### प्रश्न: क्या .NET के लिए Aspose.Words में स्वचालित फ़ील्ड अद्यतन को अक्षम करना संभव है?

 उत्तर: हाँ, .NET के लिए Aspose.Words में स्वचालित फ़ील्ड अपडेटिंग को अक्षम करना संभव है। आप इसका उपयोग कर सकते हैं`Document.FieldOptions.UpdateFields` संपत्ति और इसे सेट करें`false` फ़ील्ड को स्वचालित रूप से अपडेट होने से रोकने के लिए। यह आपको आवश्यकतानुसार फ़ील्ड के अपडेट को मैन्युअल रूप से नियंत्रित करने की अनुमति देता है।

#### प्रश्न: मैं .NET के लिए Aspose.Words में दस्तावेज़ फ़ील्ड को मैन्युअल रूप से कैसे अपडेट कर सकता हूं?

 A: Aspose.Words for .NET में किसी दस्तावेज़ में फ़ील्ड को मैन्युअल रूप से अपडेट करने के लिए, आप इसका उपयोग कर सकते हैं`Field.Update` प्रत्येक फ़ील्ड के लिए अलग-अलग विधि। उदाहरण के लिए, आप उपयोग कर सकते हैं`field.Update()` विशिष्ट फ़ील्ड को अद्यतन करने के लिए.