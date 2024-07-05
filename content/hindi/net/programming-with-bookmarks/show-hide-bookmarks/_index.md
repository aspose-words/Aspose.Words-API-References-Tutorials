---
title: Word दस्तावेज़ में बुकमार्क दिखाएँ छुपाएँ
linktitle: Word दस्तावेज़ में बुकमार्क दिखाएँ छुपाएँ
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में किसी विशिष्ट बुकमार्क को दिखाने या छिपाने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-bookmarks/show-hide-bookmarks/
---

इस लेख में, हम ऊपर दिए गए C# स्रोत कोड का पता लगाएंगे ताकि यह समझा जा सके कि Aspose.Words for .NET लाइब्रेरी में Show Hide Bookmarks फ़ंक्शन का उपयोग कैसे किया जाए। यह सुविधा आपको वर्ड दस्तावेज़ में किसी विशिष्ट बुकमार्क को दिखाने या छिपाने की अनुमति देती है।

## आवश्यक शर्तें

- C# भाषा का मूलभूत ज्ञान.
- Aspose.Words लाइब्रेरी के साथ .NET विकास वातावरण स्थापित।

## चरण 1: दस्तावेज़ लोड करना

 हम उपयोग करते हैं`Document` फ़ाइल से मौजूदा दस्तावेज़ लोड करने के लिए क्लास:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## चरण 2: कोई विशिष्ट बुकमार्क दिखाएँ या छिपाएँ

 हम उपयोग करते हैं`ShowHideBookmarkedContent` दस्तावेज़ में किसी विशिष्ट बुकमार्क को दिखाने या छिपाने के लिए फ़ंक्शन। यह फ़ंक्शन पैरामीटर के रूप में दस्तावेज़, बुकमार्क का नाम और बुकमार्क को दिखाने या छिपाने के लिए बूलियन लेता है:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## चरण 3: संशोधित दस्तावेज़ को सहेजना

 हम उपयोग करते हैं`Save` संशोधित दस्तावेज़ को फ़ाइल में सहेजने की विधि:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके बुकमार्क दिखाएँ छिपाएँ के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके किसी विशिष्ट बुकमार्क को दिखाने या छिपाने के लिए यहां पूर्ण उदाहरण स्रोत कोड दिया गया है:

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### स्रोत कोड दिखाएँछिपाएँबुकमार्क की गईसामग्री

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
            Bookmark bm = doc.Range.Bookmarks[bookmarkName];

            DocumentBuilder builder = new DocumentBuilder(doc);
            builder.MoveToDocumentEnd();

            // {IF "{MERGEFIELD बुकमार्क}" = "सत्य" "" ""}
            Field field = builder.InsertField("IF \"", null);
            builder.MoveTo(field.Start.NextSibling);
            builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
            builder.Write("\" = \"true\" ");
            builder.Write("\"");
            builder.Write("\"");
            builder.Write(" \"\"");

            Node currentNode = field.Start;
            bool flag = true;
            while (currentNode != null && flag)
            {
                if (currentNode.NodeType == NodeType.Run)
                    if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
                        flag = false;

                Node nextNode = currentNode.NextSibling;

                bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
                currentNode = nextNode;
            }

            Node endNode = bm.BookmarkEnd;
            flag = true;
            while (currentNode != null && flag)
            {
                if (currentNode.NodeType == NodeType.FieldEnd)
                    flag = false;

                Node nextNode = currentNode.NextSibling;

                bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
                endNode = currentNode;
                currentNode = nextNode;
            }

            doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });
        }
		
```
## निष्कर्ष

इस लेख में, हमने C# स्रोत कोड का पता लगाया ताकि यह समझा जा सके कि .NET के लिए Aspose.Words की Show Hide Bookmarks सुविधा का उपयोग कैसे किया जाए। हमने दस्तावेज़ में किसी विशिष्ट बुकमार्क को दिखाने या छिपाने के लिए चरण-दर-चरण मार्गदर्शिका का पालन किया।

### वर्ड दस्तावेज़ में बुकमार्क दिखाने/छिपाने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं एक ही दस्तावेज़ में एकाधिक बुकमार्क दिखा या छिपा सकता हूँ?

उत्तर: हां, आप जिस भी बुकमार्क को प्रोसेस करना चाहते हैं उसके लिए चरण 2 और 3 को दोहराकर एक ही दस्तावेज़ में एकाधिक बुकमार्क दिखा या छिपा सकते हैं।

#### प्रश्न: क्या प्रदान किया गया कोड अन्य वर्ड दस्तावेज़ प्रारूपों, जैसे .doc या .docm के साथ काम करता है?

उत्तर: हां, प्रदान किया गया कोड Aspose.Words द्वारा समर्थित विभिन्न Word दस्तावेज़ प्रारूपों, जैसे .doc और .docm के साथ काम करता है। दस्तावेज़ को लोड और सहेजते समय बस सही फ़ाइल नाम और पथ का उपयोग करना सुनिश्चित करें।

#### प्रश्न: मैं छुपे हुए बुकमार्क को पुनः कैसे दिखा सकता हूँ?

 उत्तर: छिपे हुए बुकमार्क को फिर से दिखाने के लिए, आपको उसी का उपयोग करना होगा`ShowHideBookmarkedContent` मान पास करने वाला फ़ंक्शन`true` बूलियन पैरामीटर के लिए जो यह इंगित करता है कि बुकमार्क को दिखाना है या छुपाना है।

#### प्रश्न: क्या मैं दस्तावेज़ में मर्ज फ़ील्ड मानों के आधार पर बुकमार्क दिखाने या छिपाने के लिए शर्तों का उपयोग कर सकता हूँ?

 उत्तर: हां, आप शर्तों और मर्ज फ़ील्ड मानों का उपयोग करके यह निर्धारित कर सकते हैं कि बुकमार्क दिखाया जाना चाहिए या छिपाया जाना चाहिए। आप कोड को कस्टमाइज़ कर सकते हैं`ShowHideBookmarkedContent` उचित परिस्थितियों और मूल्यों को ध्यान में रखते हुए कार्य करें।

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में बुकमार्क कैसे हटा सकता हूं?

 उत्तर: Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में बुकमार्क हटाने के लिए, आप इसका उपयोग कर सकते हैं`RemoveBookmarks` की विधि`Document` क्लास. यहाँ एक नमूना कोड है:

```csharp
doc.RemoveBookmarks("BookmarkName");
```