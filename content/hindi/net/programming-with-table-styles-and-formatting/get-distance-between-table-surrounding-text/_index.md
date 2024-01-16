---
title: टेबल के आसपास के पाठ के बीच दूरी प्राप्त करें
linktitle: टेबल के आसपास के पाठ के बीच दूरी प्राप्त करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में टेक्स्ट और तालिका के बीच की दूरी जानने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words का उपयोग करके तालिका में आसपास के टेक्स्ट के बीच की दूरी प्राप्त करने की चरण-दर-चरण प्रक्रिया के बारे में बताएंगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को समझने और अपनी परियोजनाओं में लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ों में एक तालिका और आसपास के पाठ के बीच विभिन्न दूरियों तक कैसे पहुँचें।

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें
सबसे पहले, आपको अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करना होगा। यह वह जगह है जहां आपका Word दस्तावेज़ स्थित है। "आपकी दस्तावेज़ निर्देशिका" को उचित पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: मौजूदा दस्तावेज़ लोड करें
 इसके बाद, आपको मौजूदा वर्ड दस्तावेज़ को एक उदाहरण में लोड करना होगा`Document` कक्षा।

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## चरण 3: तालिका और आसपास के पाठ के बीच की दूरी ज्ञात करें
 तालिका और आसपास के पाठ के बीच की दूरी जानने के लिए, हमें दस्तावेज़ में तालिका तक पहुंचने की आवश्यकता है`GetChild()` विधि और`NodeType.Table` संपत्ति। फिर हम सरणी गुणों का उपयोग करके विभिन्न दूरियाँ प्रदर्शित कर सकते हैं`DistanceTop`, `DistanceBottom`, `DistanceRight` और`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### .NET के लिए Aspose.Words का उपयोग करके टेबल के आसपास के टेक्स्ट के बीच दूरी प्राप्त करने के लिए नमूना स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके तालिका में आसपास के टेक्स्ट के बीच की दूरी कैसे प्राप्त करें। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने Word दस्तावेज़ों में किसी तालिका और आसपास के पाठ के बीच की विभिन्न दूरियों तक आसानी से पहुंच सकते हैं। Aspose.Words आपके दस्तावेज़ों में तालिकाओं में हेरफेर और फ़ॉर्मेटिंग के लिए एक शक्तिशाली और लचीली API प्रदान करता है। इस ज्ञान के साथ, आप पाठ के संबंध में अपनी तालिकाओं के लेआउट का विश्लेषण कर सकते हैं और विशिष्ट आवश्यकताओं को पूरा कर सकते हैं।