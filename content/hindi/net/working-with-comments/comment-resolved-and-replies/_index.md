---
title: टिप्पणी समाधान और उत्तर
linktitle: टिप्पणी समाधान और उत्तर
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में टिप्पणियों और उनके उत्तरों को हल करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-comments/comment-resolved-and-replies/
---

इस व्यापक ट्यूटोरियल में, आप सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में टिप्पणियों और उनके उत्तरों को कैसे हल किया जाए। हम आपको इस प्रक्रिया के माध्यम से मार्गदर्शन करेंगे और आपको आवश्यक C# कोड स्निपेट प्रदान करेंगे। इस गाइड के अंत तक, आप टिप्पणी समाधान का प्रबंधन करने और टिप्पणियों और उनके उत्तरों की स्थिति को अपडेट करने में सक्षम होंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- आपके सिस्टम पर Aspose.Words for .NET लाइब्रेरी स्थापित है।

## चरण 1: दस्तावेज़ लोड करें और टिप्पणियाँ एक्सेस करें
आरंभ करने के लिए, Document वर्ग का उपयोग करके टिप्पणियाँ युक्त दस्तावेज़ लोड करें और टिप्पणी संग्रह तक पहुँचें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## चरण 2: टिप्पणियों और उनके उत्तरों का समाधान करें
इसके बाद, टिप्पणियों और उनके उत्तरों को दोबारा देखें और उन्हें हल किया गया चिह्नित करें:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

उपरोक्त कोड में, हम मूल टिप्पणी तक पहुँचते हैं और उसके उत्तरों के माध्यम से पुनरावृति करते हैं। हम मूल टिप्पणी आईडी और उसके समाधान की स्थिति को पुनः प्राप्त कर सकते हैं। फिर, हम समाधान को इंगित करने के लिए प्रत्येक टिप्पणी उत्तर के "पूर्ण" चिह्न को अपडेट करते हैं।

## चरण 3: दस्तावेज़ सहेजें
टिप्पणियों का समाधान करने और उनकी स्थिति को अद्यतन करने के बाद, Document वर्ग की Save विधि का उपयोग करके संशोधित दस्तावेज़ को फ़ाइल में सहेजें:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके टिप्पणियों और उनके उत्तरों को हल करने के लिए उदाहरण स्रोत कोड
.NET के लिए Aspose.Words का उपयोग करके टिप्पणियों और उनके उत्तरों को हल करने के लिए पूरा स्रोत कोड यहां दिया गया है:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
दस्तावेज़ फ़ाइल पथ और अतिरिक्त अनुकूलन सहित अपनी विशिष्ट आवश्यकताओं के अनुसार कोड को समायोजित करना याद रखें

## निष्कर्ष
बधाई हो! आपने सफलतापूर्वक सीख लिया है कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में टिप्पणियों और उनके उत्तरों को कैसे हल किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और प्रदान किए गए स्रोत कोड का उपयोग करके, अब आप टिप्पणी समाधान प्रबंधित कर सकते हैं और अपनी आवश्यकताओं के अनुसार टिप्पणियों और उनके उत्तरों की स्थिति को अपडेट कर सकते हैं।

टिप्पणी समाधान दस्तावेज़ के भीतर फ़ीडबैक को ट्रैक करने और प्रबंधित करने में मदद करता है। अलग-अलग टिप्पणी स्थितियों के साथ प्रयोग करें और अपने दस्तावेज़ों में सहयोग और समीक्षा प्रक्रियाओं को बेहतर बनाने के लिए उन्हें अनुकूलित करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words for .NET में किसी टिप्पणी का समाधान कैसे करूँ?

 A: Aspose.Words for .NET में किसी टिप्पणी को हल करने के लिए, आप इसका उपयोग कर सकते हैं`Comment.Resolve` विधि निर्दिष्ट करना`Comment` वह ऑब्जेक्ट चुनें जिसे आप हल करना चाहते हैं। यह टिप्पणी को हल किए गए के रूप में चिह्नित करेगा और इसे अंतिम दस्तावेज़ में छिपा देगा।

#### प्रश्न: मैं Aspose.Words for .NET में हल की गई टिप्पणी पर उत्तर कैसे जोड़ सकता हूँ?

 उत्तर: हालाँकि अंतिम दस्तावेज़ में हल की गई टिप्पणियाँ डिफ़ॉल्ट रूप से छिपी होती हैं, फिर भी आप इसका उपयोग करके हल की गई टिप्पणी पर उत्तर जोड़ सकते हैं`Comment.AddReply`उत्तर पाठ निर्दिष्ट करने वाली विधि और आप इसे कहाँ जोड़ना चाहते हैं।

#### प्रश्न: मैं Aspose.Words for .NET में हल की गई टिप्पणियाँ कैसे देख सकता हूँ?

 उत्तर: डिफ़ॉल्ट रूप से, हल की गई टिप्पणियाँ अंतिम दस्तावेज़ में छिपी होती हैं। हालाँकि, आप उन्हें दिखा सकते हैं`CommentOptions.ShowResolvedComments` की संपत्ति`Document` ऑब्जेक्ट और इसे सेट करना`true`.

#### प्रश्न: मैं Aspose.Words for .NET में उत्तरों सहित सभी टिप्पणियाँ कैसे छिपा सकता हूँ?

 उत्तर: Aspose.Words for .NET में उत्तरों सहित सभी टिप्पणियों को छिपाने के लिए, आप इसका उपयोग कर सकते हैं`CommentOptions.CommentDisplayMode` की संपत्ति`Document` ऑब्जेक्ट और इसे सेट करें`CommentDisplayMode.None`.

#### प्रश्न: क्या मैं .NET के लिए Aspose.Words में हल की गई टिप्पणी का पाठ संपादित कर सकता हूँ?

 उत्तर: हां, आप Aspose.Words for .NET में हल की गई टिप्पणी के पाठ को संपादित कर सकते हैं।`Comment.Text` संबंधित संपत्ति`Comment` वस्तु का चयन करना तथा आवश्यकतानुसार पाठ को संशोधित करना।