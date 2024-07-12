---
title: आउटलाइन बॉर्डर लागू करें
linktitle: आउटलाइन बॉर्डर लागू करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके किसी तालिका पर आउटलाइन बॉर्डर लागू करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

इस ट्यूटोरियल में, हम आपको Aspose.Words for .NET का उपयोग करके टेबल पर आउटलाइन बॉर्डर लगाने की चरण-दर-चरण प्रक्रिया से अवगत कराएँगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को अपने स्वयं के प्रोजेक्ट में समझने और लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत तक, आपको Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ों में टेबल बॉर्डर को कैसे हेरफेर करना है, इसकी स्पष्ट समझ होगी।

## चरण 1: दस्तावेज़ निर्देशिका निर्धारित करें
सबसे पहले, आपको अपने दस्तावेज़ निर्देशिका का पथ सेट करना होगा। यह वह जगह है जहाँ आपका Word दस्तावेज़ संग्रहीत है। "आपके दस्तावेज़ निर्देशिका" को उचित पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ अपलोड करें
 इसके बाद, आपको Word दस्तावेज़ को एक इंस्टेंस में लोड करना होगा`Document` कक्षा।

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## चरण 3: तालिका तक पहुंचें
 आउटलाइन बॉर्डर लगाने के लिए, हमें दस्तावेज़ में तालिका तक पहुंचने की आवश्यकता है।`Table` क्लास Aspose.Words में एक तालिका का प्रतिनिधित्व करता है।

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## चरण 4: तालिका को पृष्ठ के केंद्र में संरेखित करें
 अब हम तालिका को पृष्ठ के केंद्र में संरेखित कर सकते हैं`Alignment` तालिका की संपत्ति.

```csharp
table. Alignment = Table Alignment. Center;
```

## चरण 5: मौजूदा तालिका बॉर्डर मिटाएँ
एक नई आउटलाइन बॉर्डर के साथ शुरू करने के लिए, हमें सबसे पहले टेबल से सभी मौजूदा बॉर्डर मिटाने होंगे। यह का उपयोग करके किया जा सकता है`ClearBorders()` तरीका।

```csharp
table. ClearBorders();
```

## चरण 6: टेबल के चारों ओर हरे रंग की बॉर्डर निर्धारित करें
 अब हम टेबल के चारों ओर हरे रंग का बॉर्डर सेट कर सकते हैं`SetBorder()` तालिका के प्रत्येक पक्ष के लिए विधि। इस उदाहरण में, हम 1.5 पॉइंट की मोटाई और हरे रंग के साथ "सिंगल" प्रकार की सीमा का उपयोग कर रहे हैं।

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## चरण 7: कोशिकाओं को पृष्ठभूमि रंग से भरें
तालिका की दृश्य प्रस्तुति को बेहतर बनाने के लिए, हम कोशिकाओं को ग्राउंड पृष्ठभूमि रंग से भर सकते हैं

इस उदाहरण में, हम हल्के हरे रंग का उपयोग कर रहे हैं।

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## चरण 8: संशोधित दस्तावेज़ को सहेजें
अंत में, हम संशोधित दस्तावेज़ को एक फ़ाइल में सहेजते हैं। आप आउटपुट दस्तावेज़ के लिए एक उपयुक्त नाम और स्थान चुन सकते हैं।

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

बधाई हो! आपने अब .NET के लिए Aspose.Words का उपयोग करके एक तालिका पर एक आउटलाइन बॉर्डर लागू कर दिया है।

### .NET के लिए Aspose.Words का उपयोग करके आउटलाइन बॉर्डर लागू करने के लिए नमूना स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// तालिका को पृष्ठ के केंद्र में संरेखित करें.
	table.Alignment = TableAlignment.Center;
	//तालिका से किसी भी मौजूदा बॉर्डर को साफ़ करें.
	table.ClearBorders();
	// मेज के चारों ओर हरे रंग का बॉर्डर लगाएं, परंतु अंदर नहीं।
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// कोशिकाओं को हल्के हरे ठोस रंग से भरें।
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी टेबल पर आउटलाइन बॉर्डर कैसे लगाया जाता है। इस चरण-दर-चरण गाइड का पालन करके, आप आसानी से इस कार्यक्षमता को अपने C# प्रोजेक्ट में एकीकृत कर सकते हैं। टेबल फ़ॉर्मेटिंग में हेरफेर करना दस्तावेज़ प्रसंस्करण का एक अनिवार्य पहलू है, और Aspose.Words इसे प्राप्त करने के लिए एक शक्तिशाली और लचीला API प्रदान करता है। इस ज्ञान के साथ, आप अपने Word दस्तावेज़ों की दृश्य प्रस्तुति में सुधार कर सकते हैं और विशिष्ट आवश्यकताओं को पूरा कर सकते हैं।