---
title: DOM का उपयोग करके मर्ज फ़ील्ड डालें
linktitle: DOM का उपयोग करके मर्ज फ़ील्ड डालें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ अपने Word दस्तावेज़ों में कस्टम फ़ील्ड मर्ज फ़ील्ड सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-fields/insert-merge-field-using-dom/
---

नीचे C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है जो .NET के लिए Aspose.Words की "इन्सर्ट फ़ील्ड मर्ज फ़ील्ड" सुविधा का उपयोग करती है। वांछित परिणाम प्राप्त करने के लिए प्रत्येक चरण का सावधानीपूर्वक पालन करना सुनिश्चित करें।

## चरण 1: दस्तावेज़ निर्देशिका सेटअप

दिए गए कोड में, आपको अपने दस्तावेज़ों की निर्देशिका निर्दिष्ट करनी होगी। अपने दस्तावेज़ निर्देशिका के लिए उचित पथ के साथ "आपकी दस्तावेज़ निर्देशिका" मान को बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ और दस्तावेज़बिल्डर बनाना

हम एक नया दस्तावेज़ बनाकर और एक DocumentBuilder प्रारंभ करके शुरुआत करते हैं।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: कर्सर को पैराग्राफ़ पर ले जाना

 हम उपयोग करते हैं`MoveTo()` कर्सर को उस पैराग्राफ पर ले जाने के लिए DocumentBuilder की विधि जहां हम फ़ील्ड मर्ज फ़ील्ड सम्मिलित करना चाहते हैं।

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## चरण 4: फ़ील्ड मर्ज फ़ील्ड सम्मिलित करना

 हम DocumentBuilder का उपयोग करते हैं`InsertField()` पैराग्राफ में फ़ील्ड मर्ज फ़ील्ड सम्मिलित करने की विधि।

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

फिर हम उपयुक्त विकल्पों, जैसे फ़ील्ड का नाम, फ़ील्ड के पहले और बाद का टेक्स्ट और वर्टिकल फ़ॉर्मेटिंग विकल्पों को निर्दिष्ट करके फ़ील्ड मर्ज फ़ील्ड गुणों को कॉन्फ़िगर करते हैं।

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 अंत में, हम कॉल करते हैं`Update()` फ़ील्ड को अद्यतन करने की विधि.

```csharp
field. Update();
```

### .NET के लिए Aspose.Words के साथ फ़ील्ड मर्ज फ़ील्ड सम्मिलित करने के लिए नमूना स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ और DocumentBuilder बनाएँ।
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// कर्सर को पैराग्राफ़ पर ले जाएँ.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// फ़ील्ड मर्ज फ़ील्ड सम्मिलित करें.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// फ़ील्ड अद्यतन करें.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

इस उदाहरण में, हमने एक नया दस्तावेज़ बनाया, कर्सर को वांछित पैराग्राफ पर ले जाया, और फिर दस्तावेज़ में एक फ़ील्ड मर्ज फ़ील्ड डाला।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं DOM के साथ .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में मर्ज फ़ील्ड कैसे सम्मिलित कर सकता हूँ?

उ: DOM के साथ .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में मर्ज फ़ील्ड सम्मिलित करने के लिए, आप इन चरणों का पालन कर सकते हैं:

1. उस अनुच्छेद पर जाएँ जहाँ आप मर्ज फ़ील्ड सम्मिलित करना चाहते हैं।
2.  एक बनाने के`FieldMergeField` वस्तु।
3. मर्ज फ़ील्ड गुण सेट करें, जैसे फ़ील्ड नाम और फ़ॉर्मेटिंग विकल्प।
4.  का उपयोग करके पैराग्राफ में मर्ज फ़ील्ड जोड़ें`Paragraph.AppendChild` तरीका।

#### प्रश्न: मैं .NET के लिए Aspose.Words में मर्ज फ़ील्ड के लिए स्रोत डेटा कैसे निर्दिष्ट कर सकता हूं?

ए: .NET के लिए Aspose.Words में मर्ज फ़ील्ड के लिए स्रोत डेटा निर्दिष्ट करने के लिए, आप इसका उपयोग कर सकते हैं`FieldMergeField.FieldName` मर्ज फ़ील्ड नाम सेट करने की विधि, जो बाहरी डेटा स्रोत जैसे सीएसवी फ़ाइल, डेटाबेस इत्यादि में फ़ील्ड का नाम है। आप इसका भी उपयोग कर सकते हैं`FieldMergeField.Text` मर्ज फ़ील्ड मान को सीधे सेट करने की विधि।

#### प्रश्न: क्या मैं .NET के लिए Aspose.Words के साथ किसी Word दस्तावेज़ में मर्ज फ़ील्ड की उपस्थिति को अनुकूलित कर सकता हूँ?

 उ: हाँ, आप .NET के लिए Aspose.Words के साथ किसी Word दस्तावेज़ में मर्ज फ़ील्ड की उपस्थिति को अनुकूलित कर सकते हैं। आप के गुणों का उपयोग करके फ़ॉर्मेटिंग विकल्प जैसे केस, फ़ॉन्ट, रंग इत्यादि सेट कर सकते हैं`FieldMergeField` वस्तु।

#### प्रश्न: मैं कैसे जांच सकता हूं कि .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में मर्ज फ़ील्ड सफलतापूर्वक डाला गया था या नहीं?

 उ: यह जांचने के लिए कि क्या मर्ज फ़ील्ड सफलतापूर्वक डाला गया था, आप दस्तावेज़ सामग्री ब्राउज़ कर सकते हैं और मर्ज फ़ील्ड उदाहरण खोज सकते हैं। आप की विधियों और गुणों का उपयोग कर सकते हैं`Document` पैराग्राफ, फ़ील्ड और दस्तावेज़ के अन्य तत्वों तक पहुँचने के लिए ऑब्जेक्ट।

#### प्रश्न: क्या DOM का उपयोग करके मर्ज फ़ील्ड डालने से .NET के लिए Aspose.Words के साथ Word दस्तावेज़ संरचना प्रभावित होती है?

उ: DOM का उपयोग करके मर्ज फ़ील्ड सम्मिलित करना सीधे Word दस्तावेज़ की संरचना को प्रभावित नहीं करता है। हालाँकि, यह दस्तावेज़ सामग्री में एक नया फ़ील्ड तत्व जोड़ता है। आप अपनी आवश्यकताओं के अनुसार मौजूदा तत्वों को जोड़कर, हटाकर या संशोधित करके दस्तावेज़ संरचना में हेरफेर कर सकते हैं।