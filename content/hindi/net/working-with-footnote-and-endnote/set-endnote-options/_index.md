---
title: एंडनोट विकल्प सेट करें
linktitle: एंडनोट विकल्प सेट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में एंडनोट विकल्प सेट करना सीखें। उदाहरण स्रोत कोड के साथ चरण-दर-चरण ट्यूटोरियल।
type: docs
weight: 10
url: /hi/net/working-with-footnote-and-endnote/set-endnote-options/
---

इस चरण-दर-चरण ट्यूटोरियल में, हम आपको Word दस्तावेज़ में एंडनोट विकल्प सेट करने के लिए .NET के लिए Aspose.Words का उपयोग करने के तरीके के बारे में मार्गदर्शन करेंगे। हम दिए गए C# स्रोत कोड की व्याख्या करेंगे और आपको दिखाएंगे कि इसे अपनी परियोजनाओं में कैसे लागू किया जाए।

 आरंभ करने के लिए, सुनिश्चित करें कि आपके पास .NET के लिए Aspose.Words स्थापित है और आपके विकास परिवेश में स्थापित है। यदि आपने ऐसा नहीं किया है, तो यहां से लाइब्रेरी डाउनलोड और इंस्टॉल करें[Aspose.Releases]https://releases.aspose.com/words/net/।

## चरण 1: दस्तावेज़ ऑब्जेक्ट को प्रारंभ करना

 सबसे पहले, आरंभ करें`Document` अपने स्रोत दस्तावेज़ को पथ प्रदान करके ऑब्जेक्ट करें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## चरण 2: डॉक्यूमेंटबिल्डर ऑब्जेक्ट को प्रारंभ करना

 इसके बाद, इनिशियलाइज़ करें`DocumentBuilder` दस्तावेज़ पर कार्रवाई करने के लिए ऑब्जेक्ट:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: टेक्स्ट और एंडनोट जोड़ना

 उपयोग`Write` की विधि`DocumentBuilder` दस्तावेज़ में टेक्स्ट जोड़ने के लिए ऑब्जेक्ट, और`InsertFootnote` एंडनोट डालने की विधि:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## चरण 4: एंडनोट विकल्प सेट करना

 तक पहुंच`EndnoteOptions` एंडनोट विकल्पों को संशोधित करने के लिए दस्तावेज़ की संपत्ति। इस उदाहरण में, हम प्रत्येक पृष्ठ पर पुनरारंभ नियम और अनुभाग के अंत तक की स्थिति निर्धारित करते हैं:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## चरण 5: दस्तावेज़ सहेजना

अंत में, संशोधित दस्तावेज़ सहेजें:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में एंडनोट विकल्प सफलतापूर्वक सेट कर लिया है।

### .NET के लिए Aspose.Words का उपयोग करके सेट एंडनोट विकल्प के लिए उदाहरण स्रोत कोड

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

बेझिझक इस कोड को अपनी परियोजनाओं में उपयोग करें और इसे अपनी विशिष्ट आवश्यकताओं के अनुसार संशोधित करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words में एंडनोट्स को कैसे स्टाइल कर सकता हूं?

उत्तर: Aspose.Words में एंडनोट्स को स्टाइल करने के लिए, आप इसका उपयोग कर सकते हैं`EndnoteOptions` कक्षा और`SeparatorNoteTextStyle` संपत्ति। आप इस प्रॉपर्टी का उपयोग करके एंडनोट्स के लिए फ़ॉन्ट शैली, आकार, रंग आदि निर्दिष्ट कर सकते हैं।

#### प्रश्न: क्या किसी दस्तावेज़ में एंडनोट्स की संख्या को अनुकूलित करना संभव है?

 उ: हाँ, किसी दस्तावेज़ में एंडनोट्स की संख्या को अनुकूलित करना संभव है। आप इसका उपयोग कर सकते हैं`RestartRule` और`NumberStyle` के गुण`EndnoteOptions` विशिष्ट पुनरारंभ नियमों और क्रमांकन शैलियों को परिभाषित करने के लिए कक्षा।

#### प्रश्न: मैं किसी दस्तावेज़ में एंडनोट्स कैसे रख सकता हूँ?

 उ: किसी दस्तावेज़ में एंडनोट्स को स्थान देने के लिए, आप इसका उपयोग कर सकते हैं`Position` की संपत्ति`EndnoteOptions` कक्षा। आप निर्दिष्ट कर सकते हैं कि एंडनोट्स को प्रत्येक पृष्ठ के नीचे, प्रत्येक अनुभाग के अंत में, या दस्तावेज़ के अंत में रखा जाना चाहिए।

#### प्रश्न: क्या मैं एंडनोट नंबरिंग प्रारूप को अनुकूलित कर सकता हूं?

 उ: हां, आप Aspose.Words में एंडनोट नंबरिंग के प्रारूप को अनुकूलित कर सकते हैं। उपयोग`NumberFormat` की संपत्ति`EndnoteOptions` वांछित प्रारूप सेट करने के लिए क्लास, जैसे अरबी अंक, रोमन अंक, अक्षर इत्यादि।

#### प्रश्न: क्या दस्तावेज़ के अनुभागों के बीच एंडनोट नंबरिंग जारी रखना संभव है?

उ: हां, किसी दस्तावेज़ के अनुभागों के बीच एंडनोट नंबरिंग जारी रखना संभव है। उपयोग`RestartRule` की संपत्ति`EndnoteOptions` क्लास करें और इसे सेट करें`RestartContinuous` अनुभागों के बीच क्रमांकन जारी रखने की अनुमति देने के लिए।