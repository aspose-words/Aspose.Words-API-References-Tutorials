---
title: वर्ड दस्तावेज़ में बुकमार्क किए गए टेक्स्ट को कॉपी करें
linktitle: वर्ड दस्तावेज़ में बुकमार्क किए गए टेक्स्ट को कॉपी करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके वर्ड दस्तावेज़ में बुकमार्क टेक्स्ट को दूसरे दस्तावेज़ में कॉपी करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-bookmarks/copy-bookmarked-text/
---

इस लेख में, हम .NET लाइब्रेरी के लिए Aspose.Words में कॉपी बुकमार्क किए गए टेक्स्ट फ़ंक्शन का उपयोग करने के तरीके को समझने के लिए उपरोक्त C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको किसी विशिष्ट बुकमार्क की सामग्री को स्रोत दस्तावेज़ से दूसरे दस्तावेज़ में कॉपी करने की अनुमति देती है।

## आवश्यक शर्तें

- C# भाषा का बुनियादी ज्ञान।
- Aspose.Words लाइब्रेरी के साथ .NET विकास वातावरण स्थापित।

## चरण 1: स्रोत दस्तावेज़ लोड हो रहा है

 बुकमार्क टेक्स्ट को कॉपी करने से पहले, हमें स्रोत दस्तावेज़ को इसमें लोड करना होगा`Document` फ़ाइल पथ का उपयोग कर ऑब्जेक्ट:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## चरण 2: स्रोत बुकमार्क प्राप्त करना

 हम उपयोग करते हैं`Bookmarks` उस विशिष्ट बुकमार्क को प्राप्त करने के लिए स्रोत दस्तावेज़ श्रेणी की संपत्ति जिसे हम कॉपी करना चाहते हैं:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## चरण 3: गंतव्य दस्तावेज़ बनाना

हम एक नया दस्तावेज़ बनाते हैं जो बुकमार्क सामग्री की प्रतिलिपि बनाने के लिए गंतव्य दस्तावेज़ के रूप में काम करेगा:

```csharp
Document dstDoc = new Document();
```

## चरण 4: कॉपी स्थान निर्दिष्ट करना

हम वह स्थान निर्दिष्ट करते हैं जहां हम कॉपी किया गया टेक्स्ट जोड़ना चाहते हैं। हमारे उदाहरण में, हम गंतव्य दस्तावेज़ के अंतिम भाग के मुख्य भाग के अंत में पाठ जोड़ते हैं:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## चरण 5: बुकमार्क टेक्स्ट को आयात और कॉपी करें

 हम एक का उपयोग करते हैं`NodeImporter`किसी स्रोत दस्तावेज़ से बुकमार्क टेक्स्ट को गंतव्य दस्तावेज़ में आयात और कॉपी करने पर आपत्ति:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके बुकमार्क किए गए टेक्स्ट को कॉपी करने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके बुकमार्क से टेक्स्ट कॉपी करना प्रदर्शित करने के लिए यहां पूर्ण उदाहरण स्रोत कोड दिया गया है:

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// यह वह बुकमार्क है जिसकी सामग्री हम कॉपी करना चाहते हैं।
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// हम इस दस्तावेज़ में जोड़ देंगे.
	Document dstDoc = new Document();

	// मान लीजिए कि हमें अंतिम खंड के मुख्य भाग के अंत में जोड़ा जाएगा।
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// यदि आप एक ही संदर्भ के बिना कई बार आयात करते हैं, तो इसके परिणामस्वरूप कई शैलियाँ निर्मित होंगी।
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### बुकमार्क टेक्स्ट स्रोत कोड संलग्न करें

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
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
        }

```
## निष्कर्ष

इस लेख में, हमने .NET के लिए Aspose.Words से बुकमार्क किए गए टेक्स्ट को कॉपी करें फ़ंक्शन का उपयोग करने के तरीके को समझने के लिए C# स्रोत कोड की खोज की। हमने बुकमार्क की सामग्री को स्रोत दस्तावेज़ से दूसरे दस्तावेज़ में कॉपी करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन किया।

### वर्ड दस्तावेज़ में बुकमार्क किए गए टेक्स्ट की प्रतिलिपि बनाने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में "बुकमार्क के साथ टेक्स्ट कॉपी करें" सुविधा का उपयोग करने की क्या आवश्यकताएं हैं?

उ: .NET के लिए Aspose.Words में "बुकमार्क के साथ टेक्स्ट कॉपी करें" सुविधा का उपयोग करने के लिए, आपको C# भाषा का बुनियादी ज्ञान होना चाहिए। आपको Aspose.Words लाइब्रेरी स्थापित करने के साथ एक .NET विकास परिवेश की भी आवश्यकता है।

#### प्रश्न: मैं .NET के लिए Aspose.Words में स्रोत दस्तावेज़ कैसे लोड करूं?

 उ: .NET के लिए Aspose.Words में स्रोत दस्तावेज़ लोड करने के लिए, आप इसका उपयोग कर सकते हैं`Document` दस्तावेज़ का फ़ाइल पथ निर्दिष्ट करके क्लास। यहाँ एक नमूना कोड है:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके स्रोत दस्तावेज़ में किसी विशिष्ट बुकमार्क की सामग्री कैसे प्राप्त करें?

 उ: .NET के लिए Aspose.Words का उपयोग करके स्रोत दस्तावेज़ में किसी विशिष्ट बुकमार्क की सामग्री प्राप्त करने के लिए, आप इसका उपयोग कर सकते हैं`Bookmarks` स्रोत दस्तावेज़ श्रेणी की संपत्ति और विशिष्ट बुकमार्क को पुनः प्राप्त करने के लिए बुकमार्क नाम का उपयोग करें। यहाँ एक नमूना कोड है:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके किसी गंतव्य दस्तावेज़ में बुकमार्क टेक्स्ट कॉपी का स्थान कैसे निर्दिष्ट करें?

 उ: यह निर्दिष्ट करने के लिए कि आप .NET के लिए Aspose.Words का उपयोग करके गंतव्य दस्तावेज़ में कॉपी किए गए बुकमार्क टेक्स्ट को कहां जोड़ना चाहते हैं, आप गंतव्य दस्तावेज़ के अंतिम अनुभाग के मुख्य भाग पर नेविगेट कर सकते हैं। आप इसका उपयोग कर सकते हैं`LastSection` अंतिम अनुभाग और तक पहुंचने के लिए संपत्ति`Body` उस अनुभाग के मुख्य भाग तक पहुँचने के लिए संपत्ति। यहाँ एक नमूना कोड है:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके स्रोत दस्तावेज़ से गंतव्य दस्तावेज़ में बुकमार्क टेक्स्ट को कैसे आयात और कॉपी करें?

 उ: .NET के लिए Aspose.Words का उपयोग करके स्रोत दस्तावेज़ से बुकमार्क टेक्स्ट को गंतव्य दस्तावेज़ में आयात और कॉपी करने के लिए, आप इसका उपयोग कर सकते हैं`NodeImporter` स्रोत दस्तावेज़, गंतव्य दस्तावेज़ और रखने के लिए फ़ॉर्मेटिंग मोड को निर्दिष्ट करने वाला वर्ग। तो आप इसका उपयोग कर सकते हैं`AppendBookmarkedText` गंतव्य दस्तावेज़ में बुकमार्क टेक्स्ट जोड़ने की विधि। यहाँ एक नमूना कोड है:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके बुकमार्क टेक्स्ट की प्रतिलिपि बनाने के बाद गंतव्य दस्तावेज़ को कैसे सहेजें?

उ: .NET के लिए Aspose.Words का उपयोग करके बुकमार्क से टेक्स्ट कॉपी करने के बाद गंतव्य दस्तावेज़ को सहेजने के लिए, आप इसका उपयोग कर सकते हैं`Save` की विधि`Document` गंतव्य फ़ाइल पथ निर्दिष्ट करने वाली वस्तु। यहाँ एक नमूना कोड है:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```