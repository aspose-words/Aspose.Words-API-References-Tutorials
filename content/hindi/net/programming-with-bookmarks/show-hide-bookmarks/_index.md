---
title: Word दस्तावेज़ में बुकमार्क छिपाएँ दिखाएँ
linktitle: Word दस्तावेज़ में बुकमार्क छिपाएँ दिखाएँ
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके वर्ड दस्तावेज़ में किसी विशिष्ट बुकमार्क को दिखाना या छिपाना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-bookmarks/show-hide-bookmarks/
---

इस लेख में, हम .NET लाइब्रेरी के लिए Aspose.Words में शो हाइड बुकमार्क फ़ंक्शन का उपयोग करने के तरीके को समझने के लिए उपरोक्त C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको वर्ड दस्तावेज़ में एक विशिष्ट बुकमार्क दिखाने या छिपाने की अनुमति देती है।

## आवश्यक शर्तें

- C# भाषा का बुनियादी ज्ञान।
- Aspose.Words लाइब्रेरी के साथ .NET विकास वातावरण स्थापित।

## चरण 1: दस्तावेज़ लोड करना

 हम उपयोग करते हैं`Document` किसी फ़ाइल से मौजूदा दस्तावेज़ को लोड करने के लिए क्लास:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## चरण 2: किसी विशिष्ट बुकमार्क को दिखाएँ या छिपाएँ

 हम उपयोग करते हैं`ShowHideBookmarkedContent`दस्तावेज़ में किसी विशिष्ट बुकमार्क को दिखाने या छिपाने का कार्य। यह फ़ंक्शन पैरामीटर के रूप में दस्तावेज़, बुकमार्क का नाम और एक बूलियन लेता है ताकि यह इंगित किया जा सके कि बुकमार्क दिखाना है या छिपाना है:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## चरण 3: संशोधित दस्तावेज़ को सहेजना

 हम उपयोग करते हैं`Save` संशोधित दस्तावेज़ को फ़ाइल में सहेजने की विधि:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके बुकमार्क छुपाएँ दिखाने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके किसी विशिष्ट बुकमार्क को दिखाना या छिपाना प्रदर्शित करने के लिए यहां पूर्ण उदाहरण स्रोत कोड दिया गया है:

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### शोहाइडबुकमार्कडकंटेंट स्रोत कोड

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
            Bookmark bm = doc.Range.Bookmarks[bookmarkName];

            DocumentBuilder builder = new DocumentBuilder(doc);
            builder.MoveToDocumentEnd();

            // {IF "{MERGEFIELD बुकमार्क}" = "सही" "" ""}
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

इस लेख में, हमने .NET के लिए Aspose.Words के शो हाईड बुकमार्क फीचर का उपयोग करने के तरीके को समझने के लिए C# स्रोत कोड की खोज की। किसी दस्तावेज़ में किसी विशिष्ट बुकमार्क को दिखाने या छिपाने के लिए हमने चरण-दर-चरण मार्गदर्शिका का पालन किया।

### वर्ड दस्तावेज़ में बुकमार्क दिखाने और छिपाने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं एक ही दस्तावेज़ में एकाधिक बुकमार्क दिखा या छिपा सकता हूँ?

उ: हाँ, आप जिस बुकमार्क को संसाधित करना चाहते हैं उसके लिए चरण 2 और 3 को दोहराकर आप एक ही दस्तावेज़ में एकाधिक बुकमार्क दिखा या छिपा सकते हैं।

#### प्रश्न: क्या प्रदान किया गया कोड अन्य वर्ड दस्तावेज़ प्रारूपों, जैसे .doc या .docm, के साथ काम करता है?

उ: हाँ, प्रदान किया गया कोड Aspose.Words द्वारा समर्थित विभिन्न Word दस्तावेज़ स्वरूपों, जैसे .doc और .docm, के साथ काम करता है। दस्तावेज़ को लोड और सहेजते समय बस सही फ़ाइल नाम और पथ का उपयोग करना सुनिश्चित करें।

#### प्रश्न: मैं छुपे हुए बुकमार्क को दोबारा कैसे दिखा सकता हूँ?

 उ: किसी छिपे हुए बुकमार्क को दोबारा दिखाने के लिए, आपको उसी का उपयोग करना होगा`ShowHideBookmarkedContent` मान पारित करने वाला फ़ंक्शन`true` बूलियन पैरामीटर के लिए जो इंगित करता है कि बुकमार्क दिखाना है या छिपाना है।

#### प्रश्न: क्या मैं दस्तावेज़ में मर्ज फ़ील्ड मानों के आधार पर बुकमार्क दिखाने या छिपाने के लिए शर्तों का उपयोग कर सकता हूँ?

 उ: हाँ, आप यह निर्धारित करने के लिए शर्तों का उपयोग कर सकते हैं और फ़ील्ड मानों को मर्ज कर सकते हैं कि कोई बुकमार्क दिखाया जाना चाहिए या छिपाया जाना चाहिए। आप के कोड को कस्टमाइज़ कर सकते हैं`ShowHideBookmarkedContent` उपयुक्त परिस्थितियों और मूल्यों को ध्यान में रखने का कार्य।

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में बुकमार्क कैसे हटा सकता हूं?

 उ: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में बुकमार्क हटाने के लिए, आप इसका उपयोग कर सकते हैं`RemoveBookmarks` की विधि`Document` कक्षा। यहाँ एक नमूना कोड है:

```csharp
doc.RemoveBookmarks("BookmarkName");
```