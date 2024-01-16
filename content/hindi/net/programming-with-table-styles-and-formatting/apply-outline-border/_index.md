---
title: आउटलाइन बॉर्डर लागू करें
linktitle: आउटलाइन बॉर्डर लागू करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके किसी तालिका में आउटलाइन बॉर्डर लागू करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words का उपयोग करके तालिका में आउटलाइन बॉर्डर लागू करने की चरण-दर-चरण प्रक्रिया के बारे में बताएंगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को समझने और अपनी परियोजनाओं में लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत तक, आपको .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ों में तालिका सीमाओं में हेरफेर करने की स्पष्ट समझ हो जाएगी।

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें
सबसे पहले, आपको अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करना होगा। यह वह जगह है जहां आपका Word दस्तावेज़ संग्रहीत है। "आपकी दस्तावेज़ निर्देशिका" को उचित पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ अपलोड करें
 इसके बाद, आपको Word दस्तावेज़ को एक उदाहरण में लोड करना होगा`Document` कक्षा।

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## चरण 3: तालिका तक पहुंचें
 आउटलाइन बॉर्डर लागू करने के लिए, हमें दस्तावेज़ में तालिका तक पहुंचने की आवश्यकता है।`Table` वर्ग Aspose.Words में एक तालिका का प्रतिनिधित्व करता है।

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## चरण 4: तालिका को पृष्ठ के मध्य में संरेखित करें
 अब हम इसका उपयोग करके तालिका को पृष्ठ के मध्य में संरेखित कर सकते हैं`Alignment` तालिका की संपत्ति.

```csharp
table. Alignment = Table Alignment. Center;
```

## चरण 5: मौजूदा टेबल बॉर्डर मिटाएँ
एक नई रूपरेखा सीमा के साथ शुरुआत करने के लिए, हमें सबसे पहले तालिका से सभी मौजूदा सीमाओं को मिटाना होगा। इसका उपयोग करके ऐसा किया जा सकता है`ClearBorders()` तरीका।

```csharp
table. ClearBorders();
```

## चरण 6: मेज़ के चारों ओर हरे रंग का बॉर्डर परिभाषित करें
 अब हम इसका उपयोग करके टेबल के चारों ओर एक हरा बॉर्डर सेट कर सकते हैं`SetBorder()` मेज के प्रत्येक पक्ष के लिए विधि. इस उदाहरण में, हम 1.5 अंक की मोटाई और हरे रंग के साथ "एकल" प्रकार की सीमा का उपयोग कर रहे हैं।

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## चरण 7: कोशिकाओं को पृष्ठभूमि रंग से भरें
तालिका की दृश्य प्रस्तुति को बेहतर बनाने के लिए, हम कक्षों को ग्राउंड पृष्ठभूमि रंग से भर सकते हैं

विचार। इस उदाहरण में, हम हल्के हरे रंग का उपयोग कर रहे हैं।

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## चरण 8: संशोधित दस्तावेज़ सहेजें
अंत में, हम संशोधित दस्तावेज़ को एक फ़ाइल में सहेजते हैं। आप आउटपुट दस्तावेज़ के लिए उपयुक्त नाम और स्थान चुन सकते हैं।

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

बधाई हो! अब आपने .NET के लिए Aspose.Words का उपयोग करके एक तालिका में एक आउटलाइन बॉर्डर लागू कर दिया है।

### .NET के लिए Aspose.Words का उपयोग करके आउटलाइन बॉर्डर लागू करने के लिए नमूना स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// तालिका को पृष्ठ के मध्य में संरेखित करें.
	table.Alignment = TableAlignment.Center;
	//तालिका से कोई भी मौजूदा बॉर्डर साफ़ करें.
	table.ClearBorders();
	// मेज़ के चारों ओर हरे रंग का बॉर्डर लगाएं लेकिन अंदर नहीं।
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// कोशिकाओं को हल्के हरे ठोस रंग से भरें।
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी तालिका में आउटलाइन बॉर्डर कैसे लागू किया जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप इस कार्यक्षमता को अपने C# प्रोजेक्ट में आसानी से एकीकृत कर सकते हैं। तालिका स्वरूपण में हेरफेर दस्तावेज़ प्रसंस्करण का एक अनिवार्य पहलू है, और Aspose.Words इसे प्राप्त करने के लिए एक शक्तिशाली और लचीला एपीआई प्रदान करता है। इस ज्ञान से, आप अपने Word दस्तावेज़ों की दृश्य प्रस्तुति में सुधार कर सकते हैं और विशिष्ट आवश्यकताओं को पूरा कर सकते हैं।