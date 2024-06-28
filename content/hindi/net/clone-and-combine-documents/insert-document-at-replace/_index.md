---
title: प्रतिस्थापित पर दस्तावेज़ सम्मिलित करें
linktitle: प्रतिस्थापित पर दस्तावेज़ सम्मिलित करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: हमारे विस्तृत, चरण-दर-चरण गाइड के साथ .NET के लिए Aspose.Words का उपयोग करके एक Word दस्तावेज़ को दूसरे में सहजता से सम्मिलित करना सीखें। दस्तावेज़ प्रसंस्करण को सुव्यवस्थित करने के इच्छुक डेवलपर्स के लिए बिल्कुल सही।
type: docs
weight: 10
url: /hi/net/clone-and-combine-documents/insert-document-at-replace/
---
## परिचय

अरे, दस्तावेज़ विशेषज्ञ! क्या आपने कभी यह जानने की कोशिश में खुद को घुटने तक कोड में डूबा हुआ पाया है कि एक वर्ड दस्तावेज़ को दूसरे में सहजता से कैसे डाला जाए? डरें नहीं, क्योंकि आज हम उस कार्य को आसान बनाने के लिए .NET के लिए Aspose.Words की दुनिया में उतर रहे हैं। हम ढूंढने और बदलने की कार्रवाई के दौरान विशिष्ट बिंदुओं पर दस्तावेज़ सम्मिलित करने के लिए इस शक्तिशाली लाइब्रेरी का उपयोग करने के तरीके के बारे में एक विस्तृत, चरण-दर-चरण मार्गदर्शिका पढ़ेंगे। Aspose.Words विज़ार्ड बनने के लिए तैयार हैं? आएँ शुरू करें!

## आवश्यक शर्तें

इससे पहले कि हम कोड में उतरें, कुछ चीज़ें आपके पास होनी चाहिए:

-  विजुअल स्टूडियो: सुनिश्चित करें कि आपकी मशीन पर विजुअल स्टूडियो स्थापित है। यदि आपके पास यह अभी तक नहीं है, तो आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://visualstudio.microsoft.com/).
-  .NET के लिए Aspose.Words: आपको Aspose.Words लाइब्रेरी की आवश्यकता होगी। आप इसे यहां से प्राप्त कर सकते हैं[Aspose वेबसाइट](https://releases.aspose.com/words/net/).
- बुनियादी सी# ज्ञान: सी# और .NET की बुनियादी समझ आपको इस ट्यूटोरियल का अनुसरण करने में मदद करेगी।

ठीक है, जो रास्ते से हट गए हैं, आइए कुछ कोड से अपने हाथ गंदे कर लें!

## नामस्थान आयात करें

सबसे पहली बात, हमें Aspose.Words के साथ काम करने के लिए आवश्यक नामस्थान आयात करने की आवश्यकता है। यह किसी प्रोजेक्ट को शुरू करने से पहले अपने सभी उपकरण इकट्ठा करने जैसा है। इन्हें अपनी C# फ़ाइल के शीर्ष पर निर्देशों का उपयोग करके जोड़ें:

```csharp
using System;
using System.Text.RegularExpressions;
using Aspose.Words;
using Aspose.Words.Replacing;
using Aspose.Words.Tables;
```

अब जबकि हमारे पास अपनी पूर्वापेक्षाएँ हैं, आइए इस प्रक्रिया को छोटे-छोटे चरणों में विभाजित करें। प्रत्येक कदम महत्वपूर्ण है और हमें अपने लक्ष्य के करीब लाएगा।

## चरण 1: दस्तावेज़ निर्देशिका स्थापित करना

सबसे पहले, हमें वह निर्देशिका निर्दिष्ट करनी होगी जहां हमारे दस्तावेज़ संग्रहीत हैं। यह बड़े प्रदर्शन से पहले मंच तैयार करने जैसा है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपकी निर्देशिका के पथ के साथ। यह वह जगह है जहां आपके दस्तावेज़ जीवित रहेंगे और सांस लेंगे।

## चरण 2: मुख्य दस्तावेज़ लोड करें

इसके बाद, हम मुख्य दस्तावेज़ लोड करते हैं जिसमें हम दूसरा दस्तावेज़ सम्मिलित करना चाहते हैं। इसे हमारा मुख्य मंच समझें जहां सारी कार्रवाई होगी।

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

यह कोड मुख्य दस्तावेज़ को निर्दिष्ट निर्देशिका से लोड करता है।

## चरण 3: ढूँढें और बदलें विकल्प सेट करें

उस विशिष्ट स्थान को खोजने के लिए जहां हम अपना दस्तावेज़ सम्मिलित करना चाहते हैं, हम ढूंढें और बदलें कार्यक्षमता का उपयोग करते हैं। यह हमारे नए जुड़ाव के लिए सटीक स्थान खोजने के लिए मानचित्र का उपयोग करने जैसा है।

```csharp
FindReplaceOptions options = new FindReplaceOptions
{
    Direction = FindReplaceDirection.Backward,
    ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

यहां, हम दिशा को बैकवर्ड पर सेट कर रहे हैं और एक कस्टम कॉलबैक हैंडलर निर्दिष्ट कर रहे हैं जिसे हम आगे परिभाषित करेंगे।

## चरण 4: रिप्लेस ऑपरेशन करें

अब, हम अपने मुख्य दस्तावेज़ को एक विशिष्ट प्लेसहोल्डर टेक्स्ट को देखने और उसे किसी भी चीज़ से बदलने के लिए कहते हैं, जबकि दूसरे दस्तावेज़ को सम्मिलित करने के लिए अपने कस्टम कॉलबैक का उपयोग करते हैं।

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

यह कोड ढूंढने और बदलने का ऑपरेशन करता है, और फिर अपडेट किए गए दस्तावेज़ को सहेजता है।

## चरण 5: एक कस्टम रिप्लेसिंग कॉलबैक हैंडलर बनाएं

हमारा कस्टम कॉलबैक हैंडलर वह जगह है जहां जादू होता है। यह हैंडलर परिभाषित करेगा कि ढूंढने और बदलने के ऑपरेशन के दौरान दस्तावेज़ प्रविष्टि कैसे की जाती है।

```csharp
private class InsertDocumentAtReplaceHandler : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs args)
    {
        Document subDoc = new Document(dataDir + "Document insertion 2.docx");

        // मिलान पाठ वाले पैराग्राफ के बाद एक दस्तावेज़ डालें।
        Paragraph para = (Paragraph)args.MatchNode.ParentNode;
        InsertDocument(para, subDoc);

        // मेल खाने वाले टेक्स्ट वाला पैराग्राफ़ हटा दें.
        para.Remove();
        return ReplaceAction.Skip;
    }
}
```

यहां, हम सम्मिलित किए जाने वाले दस्तावेज़ को लोड करते हैं और फिर प्रविष्टि करने के लिए एक सहायक विधि को कॉल करते हैं।

## चरण 6: दस्तावेज़ सम्मिलित करने की विधि को परिभाषित करें

हमारी पहेली का अंतिम भाग वह विधि है जो वास्तव में दस्तावेज़ को निर्दिष्ट स्थान पर सम्मिलित करती है।

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
	if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
	{
		CompositeNode destinationParent = insertionDestination.ParentNode;

		NodeImporter importer =
			new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

		// अनुभाग के मुख्य भाग में सभी ब्लॉक-स्तरीय नोड्स के माध्यम से लूप करें,
		// फिर प्रत्येक नोड को क्लोन करें और डालें जो किसी अनुभाग का अंतिम खाली पैराग्राफ नहीं है।
		foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
		foreach (Node srcNode in srcSection.Body)
		{
			if (srcNode.NodeType == NodeType.Paragraph)
			{
				Paragraph para = (Paragraph)srcNode;
				if (para.IsEndOfSection && !para.HasChildNodes)
					continue;
			}

			Node newNode = importer.ImportNode(srcNode, true);

			destinationParent.InsertAfter(newNode, insertionDestination);
			insertionDestination = newNode;
		}
	}
	else
	{
		throw new ArgumentException("The destination node should be either a paragraph or table.");
	}
}
```

यह विधि सम्मिलित किए जाने वाले दस्तावेज़ से नोड्स को आयात करने और उन्हें मुख्य दस्तावेज़ में सही स्थान पर रखने का ध्यान रखती है।

## निष्कर्ष

आखिर तुमने इसे हासिल कर ही लिया है! .NET के लिए Aspose.Words का उपयोग करके एक दस्तावेज़ को दूसरे दस्तावेज़ में सम्मिलित करने के लिए एक व्यापक मार्गदर्शिका। इन चरणों का पालन करके, आप दस्तावेज़ असेंबली और हेरफेर कार्यों को आसानी से स्वचालित कर सकते हैं। चाहे आप एक दस्तावेज़ प्रबंधन प्रणाली का निर्माण कर रहे हों या बस अपने दस्तावेज़ प्रसंस्करण वर्कफ़्लो को सुव्यवस्थित करने की आवश्यकता हो, Aspose.Words आपका भरोसेमंद साथी है।

## अक्सर पूछे जाने वाले प्रश्न

### .NET के लिए Aspose.Words क्या है?
.NET के लिए Aspose.Words प्रोग्रामेटिक रूप से Word दस्तावेज़ों में हेरफेर करने के लिए एक शक्तिशाली लाइब्रेरी है। यह आपको Word दस्तावेज़ों को आसानी से बनाने, संशोधित करने, परिवर्तित करने और संसाधित करने की अनुमति देता है।

### क्या मैं एक साथ अनेक दस्तावेज़ सम्मिलित कर सकता हूँ?
हां, आप दस्तावेज़ों के संग्रह पर पुनरावृत्ति करके एकाधिक प्रविष्टियों को संभालने के लिए कॉलबैक हैंडलर को संशोधित कर सकते हैं।

### क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 बिल्कुल! आप यहां से नि:शुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).

### मैं Aspose.Words के लिए समर्थन कैसे प्राप्त करूं?
पर जाकर समर्थन प्राप्त कर सकते हैं[Aspose.शब्द मंच](https://forum.aspose.com/c/words/8).

### क्या मैं सम्मिलित दस्तावेज़ का फ़ॉर्मेटिंग रख सकता हूँ?
 हां`NodeImporter`क्लास आपको यह निर्दिष्ट करने की अनुमति देता है कि एक दस्तावेज़ से दूसरे दस्तावेज़ में नोड्स आयात करते समय फ़ॉर्मेटिंग को कैसे नियंत्रित किया जाता है।