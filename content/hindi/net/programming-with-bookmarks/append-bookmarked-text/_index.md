---
title: वर्ड दस्तावेज़ में बुकमार्क किया गया टेक्स्ट जोड़ें
linktitle: वर्ड दस्तावेज़ में बुकमार्क किया गया टेक्स्ट जोड़ें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में बुकमार्क से पाठ जोड़ना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-bookmarks/append-bookmarked-text/
---

इस लेख में, हम ऊपर दिए गए C# स्रोत कोड का पता लगाएंगे ताकि यह समझ सकें कि Aspose.Words for .NET लाइब्रेरी में Append Bookmarked Text फ़ंक्शन का उपयोग कैसे करें। यह सुविधा आपको Word दस्तावेज़ के किसी विशिष्ट बुकमार्क में मौजूद टेक्स्ट को दूसरे दस्तावेज़ में जोड़ने की अनुमति देती है।

## आवश्यक शर्तें

- C# भाषा का मूलभूत ज्ञान.
- Aspose.Words लाइब्रेरी के साथ .NET विकास वातावरण स्थापित।

## चरण 1: बुकमार्क से पैराग्राफ़ प्राप्त करना

 बुकमार्क टेक्स्ट जोड़ना शुरू करने से पहले, हमें उन पैराग्राफ को प्राप्त करने की आवश्यकता है जिसमें बुकमार्क की शुरुआत और अंत शामिल है। यह एक्सेस करके किया जा सकता है`BookmarkStart` और`BookmarkEnd` बुकमार्क के गुण:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## चरण 2: मूल पैराग्राफ़ की जाँच करें

हम जाँचते हैं कि क्या आरंभिक और अंतिम पैराग्राफ़ के वैध पैरेंट हैं, यानी कि क्या वे वास्तव में पैराग्राफ़ से संबंधित हैं। यदि नहीं, तो हम अपवाद उत्पन्न करते हैं:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## चरण 3: पैराग्राफ के पैरेंट्स की जाँच करें

हम जाँचते हैं कि क्या आरंभिक और अंतिम पैराग्राफ़ का पैरेंट एक ही है। यदि नहीं, तो इसका मतलब है कि पैराग्राफ़ एक ही अनुभाग या दस्तावेज़ में शामिल नहीं हैं, और हम अपवाद फेंक रहे हैं:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## चरण 4: पैराग्राफ़ कॉपी करें

हम आरंभिक पैराग्राफ से लेकर अंतिम पैराग्राफ तक नोड्स (पैराग्राफ) के माध्यम से पुनरावृत्ति करते हैं। प्रत्येक नोड के लिए, हम एक प्रतिलिपि बनाते हैं और इसे गंतव्य दस्तावेज़ के संदर्भ में आयात करते हैं:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### .NET के लिए Aspose.Words का उपयोग करके बुकमार्क किए गए टेक्स्ट को जोड़ने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके बुकमार्क से पाठ जोड़ने का प्रदर्शन करने के लिए यहां पूर्ण उदाहरण स्रोत कोड दिया गया है:

```csharp

	// यह वह पैराग्राफ है जिसमें बुकमार्क की शुरुआत होती है।
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// यह वह पैराग्राफ है जिसमें बुकमार्क का अंत होता है।
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// अपने आप को एक सरल परिदृश्य तक सीमित रखें।
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// हम आरंभिक पैराग्राफ से लेकर अंतिम पैराग्राफ तक (और उसमें सम्मिलित) सभी पैराग्राफों को कॉपी करना चाहते हैं,
	// इसलिए जिस नोड पर हम रुकते हैं वह अंतिम पैराग्राफ के बाद एक है।
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//यह वर्तमान नोड की एक प्रतिलिपि बनाता है और उसे संदर्भ में आयात करता है (इसे वैध बनाता है)
		// गंतव्य दस्तावेज़ का। आयात करने का अर्थ है शैलियों और सूची पहचानकर्ताओं को सही ढंग से समायोजित करना।
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## निष्कर्ष

इस लेख में, हमने .NET के लिए Aspose.Words के Append Bookmarked Text फ़ंक्शन का उपयोग करने के तरीके को समझने के लिए C# स्रोत कोड का पता लगाया। हमने बुकमार्क से पैराग्राफ़ प्राप्त करने, पैरेंट्स को सत्यापित करने और पैराग्राफ़ को दूसरे दस्तावेज़ में कॉपी करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन किया है।

### वर्ड दस्तावेज़ में बुकमार्क किए गए पाठ को जोड़ने के लिए अक्सर पूछे जाने वाले प्रश्न

#### Q1: Aspose.Words for .NET में "बुकमार्क के साथ टेक्स्ट जोड़ें" सुविधा का उपयोग करने के लिए क्या पूर्वापेक्षाएँ हैं?

उत्तर: Aspose.Words for .NET में "बुकमार्क के साथ टेक्स्ट जोड़ें" फ़ंक्शन का उपयोग करने के लिए, आपको C# भाषा का बुनियादी ज्ञान होना चाहिए। आपको Aspose.Words लाइब्रेरी इंस्टॉल किए गए .NET डेवलपमेंट एनवायरनमेंट की भी आवश्यकता है।

#### प्रश्न 2: वर्ड दस्तावेज़ में बुकमार्क के आरंभ और अंत वाले पैराग्राफ कैसे प्राप्त करें?

उत्तर: वर्ड डॉक्यूमेंट में बुकमार्क के आरंभ और अंत वाले पैराग्राफ प्राप्त करने के लिए, आप इसका उपयोग कर सकते हैं`BookmarkStart` और`BookmarkEnd` बुकमार्क के गुणधर्म। यहाँ एक नमूना कोड है:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### प्रश्न 3: यदि आरंभिक और अंतिम पैराग्राफ के कोई वैध पैरेंट न हों तो क्या होगा?

उत्तर: यदि आरंभ और अंत पैराग्राफ़ में वैध पैरेंट नहीं हैं, यानी वे वास्तव में पैराग्राफ़ नहीं हैं, तो अपवाद फेंक दिया जाएगा। इस स्थिति को इस समय प्रबंधित नहीं किया जा सकता है।
