---
title: Word दस्तावेज़ में बुकमार्क किए गए टेक्स्ट को जोड़ें
linktitle: Word दस्तावेज़ में बुकमार्क किए गए टेक्स्ट को जोड़ें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में बुकमार्क से टेक्स्ट जोड़ने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-bookmarks/append-bookmarked-text/
---

इस लेख में, हम .NET लाइब्रेरी के लिए Aspose.Words में एपेंड बुकमार्क टेक्स्ट फ़ंक्शन का उपयोग करने के तरीके को समझने के लिए उपरोक्त C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको किसी Word दस्तावेज़ के विशिष्ट बुकमार्क में मौजूद टेक्स्ट को किसी अन्य दस्तावेज़ में जोड़ने की अनुमति देती है।

## आवश्यक शर्तें

- C# भाषा का बुनियादी ज्ञान।
- Aspose.Words लाइब्रेरी के साथ .NET विकास वातावरण स्थापित।

## चरण 1: बुकमार्क से पैराग्राफ प्राप्त करना

 इससे पहले कि हम बुकमार्क टेक्स्ट जोड़ना शुरू करें, हमें उन पैराग्राफों को प्राप्त करना होगा जिनमें बुकमार्क की शुरुआत और अंत शामिल है। इसे एक्सेस करके किया जा सकता है`BookmarkStart` और`BookmarkEnd` बुकमार्क के गुण:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## चरण 2: मूल पैराग्राफ की जाँच करें

हम जांचते हैं कि क्या आरंभ और अंतिम पैराग्राफ में वैध माता-पिता हैं, यानी, क्या वे वास्तव में एक पैराग्राफ से संबंधित हैं। यदि नहीं, तो हम एक अपवाद उत्पन्न करते हैं:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## चरण 3: पैराग्राफ के माता-पिता की जाँच करें

हम जाँचते हैं कि क्या आरंभ और अंतिम पैराग्राफ का मूल भाग एक ही है। यदि नहीं, तो इसका मतलब है कि पैराग्राफ एक ही अनुभाग या दस्तावेज़ में शामिल नहीं हैं, और हम एक अपवाद फेंक रहे हैं:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## चरण 4: पैराग्राफ कॉपी करें

हम प्रारंभ पैराग्राफ से अंतिम पैराग्राफ तक नोड्स (पैराग्राफ) के माध्यम से पुनरावृति करते हैं। प्रत्येक नोड के लिए, हम एक प्रतिलिपि बनाते हैं और इसे गंतव्य दस्तावेज़ के संदर्भ में आयात करते हैं:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### .NET के लिए Aspose.Words का उपयोग करके बुकमार्क किए गए टेक्स्ट को जोड़ने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके बुकमार्क से टेक्स्ट जोड़ने का प्रदर्शन करने के लिए यहां पूर्ण उदाहरण स्रोत कोड दिया गया है:

```csharp

	// यह वह पैराग्राफ है जिसमें बुकमार्क की शुरुआत होती है।
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// यह वह पैराग्राफ है जिसमें बुकमार्क का अंत होता है।
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// अपने आप को एक यथोचित सरल परिदृश्य तक सीमित रखें।
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// हम आरंभ पैराग्राफ से लेकर अंतिम पैराग्राफ तक (और इसमें शामिल हैं) सभी पैराग्राफों की प्रतिलिपि बनाना चाहते हैं,
	// इसलिए जिस नोड पर हम रुकते हैं वह अंतिम पैराग्राफ के बाद का एक नोड है।
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//यह वर्तमान नोड की एक प्रति बनाता है और इसे संदर्भ में आयात करता है (इसे वैध बनाता है)।
		// गंतव्य दस्तावेज़ का. आयात करने का अर्थ है शैलियों और सूची पहचानकर्ताओं को सही ढंग से समायोजित करना।
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## निष्कर्ष

इस लेख में, हमने .NET के लिए Aspose.Words के अपेंड बुकमार्क टेक्स्ट फ़ंक्शन का उपयोग करने के तरीके को समझने के लिए C# स्रोत कोड की खोज की। हमने बुकमार्क से पैराग्राफ प्राप्त करने, माता-पिता का सत्यापन करने और पैराग्राफ को दूसरे दस्तावेज़ में कॉपी करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन किया है।

### वर्ड दस्तावेज़ में बुकमार्क किए गए टेक्स्ट को जोड़ने के लिए अक्सर पूछे जाने वाले प्रश्न

#### Q1: .NET के लिए Aspose.Words में "बुकमार्क के साथ टेक्स्ट जोड़ें" सुविधा का उपयोग करने के लिए क्या शर्तें हैं?

उ: .NET के लिए Aspose.Words में "बुकमार्क के साथ टेक्स्ट जोड़ें" फ़ंक्शन का उपयोग करने के लिए, आपको C# भाषा का बुनियादी ज्ञान होना चाहिए। आपको Aspose.Words लाइब्रेरी स्थापित करने के साथ एक .NET विकास परिवेश की भी आवश्यकता है।

#### Q2: किसी Word दस्तावेज़ में बुकमार्क की शुरुआत और अंत वाले पैराग्राफ कैसे प्राप्त करें?

उ: किसी Word दस्तावेज़ में बुकमार्क के प्रारंभ और अंत वाले पैराग्राफ़ प्राप्त करने के लिए, आप इसका उपयोग कर सकते हैं`BookmarkStart` और`BookmarkEnd` बुकमार्क के गुण. यहाँ एक नमूना कोड है:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Q3: यदि आरंभ और अंतिम पैराग्राफ में वैध माता-पिता नहीं हैं तो क्या होगा?

उ: यदि आरंभ और अंत पैराग्राफ में वैध माता-पिता नहीं हैं, यानी वे वास्तव में पैराग्राफ नहीं हैं, तो एक अपवाद फेंक दिया जाएगा। इस स्थिति को इस समय नियंत्रित नहीं किया जा सकता.
