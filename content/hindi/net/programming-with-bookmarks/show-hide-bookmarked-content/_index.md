---
title: Word दस्तावेज़ में बुकमार्क की गई सामग्री छिपाएँ दिखाएँ
linktitle: Word दस्तावेज़ में बुकमार्क की गई सामग्री छिपाएँ दिखाएँ
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके वर्ड दस्तावेज़ में बुकमार्क सामग्री को दिखाना या छिपाना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

इस लेख में, हम .NET लाइब्रेरी के लिए Aspose.Words में शो हाइड बुकमार्क कंटेंट फ़ंक्शन का उपयोग करने के तरीके को समझने के लिए उपरोक्त C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको डेटा मर्ज करते समय एक विशिष्ट स्थिति के आधार पर वर्ड दस्तावेज़ में बुकमार्क की सामग्री को दिखाने या छिपाने की अनुमति देती है।

## आवश्यक शर्तें

- C# भाषा का बुनियादी ज्ञान।
- Aspose.Words लाइब्रेरी के साथ .NET विकास वातावरण स्थापित।

## चरण 1: बुकमार्क प्राप्त करना

 हम उपयोग करते हैं`Bookmarks` विशिष्ट बुकमार्क प्राप्त करने के लिए दस्तावेज़ श्रेणी की संपत्ति जिस पर हम सामग्री को दिखाना या छिपाना चाहते हैं:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## चरण 2: मर्ज फ़ील्ड सम्मिलित करना

 हम एक दस्तावेज़ निर्माता का उपयोग करते हैं`DocumentBuilder` आवश्यक मर्ज फ़ील्ड सम्मिलित करने के लिए। ये मर्ज फ़ील्ड के मान के आधार पर बुकमार्क सामग्री को दिखाने या छिपाने के लिए एक शर्त निर्धारित करेंगे`showHide` चर:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## चरण 3: बुकमार्क सामग्री को स्थानांतरित करना

हम बुकमार्क की सामग्री को लूप करते हैं और उसे घुमाते हैं ताकि वह दिखाई दे

बुकमार्क से पहले जारी करें। यह निर्दिष्ट स्थिति के आधार पर सामग्री को दिखाने या छिपाने को नियंत्रित करेगा:

```csharp
Node currentNode = field. Start;
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
```

## चरण 4: शेष बुकमार्क सामग्री को स्थानांतरित करना

हम बुकमार्क के अंतिम नोड को सम्मिलन बिंदु के रूप में उपयोग करते हुए, बुकमार्क के बाद शेष बुकमार्क सामग्री को स्थानांतरित करते हैं:

```csharp
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
```

## चरण 5: मर्ज करना

 हम उपयोग करते हैं`Execute` दस्तावेज़ की विधि`s `मेल मर्ज करें` object to execute the merge using the bookmark name and the value of the `showHide` वैरिएबल:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### .NET के लिए Aspose.Words का उपयोग करके बुकमार्क की गई सामग्री को छुपाने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके बुकमार्क सामग्री को दिखाने या छिपाने के लिए स्रोत कोड का पूरा उदाहरण यहां दिया गया है:

```csharp

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

```

## निष्कर्ष

इस आलेख में, हमने .NET के लिए Aspose.Words की शो हाइड बुकमार्क सामग्री सुविधा का उपयोग करने के तरीके को समझने के लिए C# स्रोत कोड की खोज की। हमने डेटा मर्ज करते समय एक विशिष्ट स्थिति के आधार पर बुकमार्क की सामग्री को दिखाने या छिपाने के लिए चरण-दर-चरण मार्गदर्शिका का पालन किया है।

### वर्ड दस्तावेज़ में बुकमार्क की गई सामग्री को दिखाने, छिपाने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं एक ही दस्तावेज़ में एकाधिक बुकमार्क के लिए एक ही शर्त का उपयोग कर सकता हूँ?

उ: हां, आप एक ही दस्तावेज़ में एकाधिक बुकमार्क के लिए एक ही शर्त का उपयोग कर सकते हैं। बस प्रत्येक बुकमार्क के लिए चरण 2-5 दोहराएँ, बुकमार्क का नाम और वैकल्पिक रूप से उसका मान समायोजित करें`showhide` आवश्यकतानुसार परिवर्तनशील।

#### प्रश्न: मैं बुकमार्क सामग्री को दिखाने या छिपाने के लिए और शर्तें कैसे जोड़ सकता हूं?

 उ: अधिक शर्तें जोड़ने के लिए, आप तार्किक ऑपरेटरों का उपयोग कर सकते हैं जैसे`AND` और`OR` चरण 2 में मर्ज फ़ील्ड डालने के लिए कोड में। अतिरिक्त शर्तें जोड़ने के लिए निम्नलिखित कोड में स्थिति संपादित करें:

```csharp
builder. Write("\" = \"true\" ");
```

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में बुकमार्क कैसे हटा सकता हूं?

 उ: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में बुकमार्क हटाने के लिए, आप इसका उपयोग कर सकते हैं`Remove` से विधि`Bookmarks` दस्तावेज़ श्रेणी का संग्रह. किसी विशिष्ट बुकमार्क को हटाने के लिए नमूना कोड यहां दिया गया है:

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### प्रश्न: क्या Aspose.Words लाइब्रेरी मुफ़्त है?

 उत्तर: Aspose.Words लाइब्रेरी एक व्यावसायिक लाइब्रेरी है और इसे आपके प्रोजेक्ट में उपयोग करने के लिए एक वैध लाइसेंस की आवश्यकता होती है। आप देख सकते हैं[.NET API संदर्भों के लिए Aspose.Words](https://reference.aspose.com/words/net/) लाइसेंसिंग विकल्पों और मूल्य निर्धारण के बारे में अधिक जानने के लिए।

#### प्रश्न: क्या .NET में वर्ड दस्तावेज़ों के साथ वर्ड प्रोसेसिंग के लिए अन्य लाइब्रेरी उपलब्ध हैं?

उ: हां, .NET में वर्ड दस्तावेज़ों के साथ वर्ड प्रोसेसिंग के लिए अन्य लाइब्रेरी उपलब्ध हैं, जैसे ओपन एक्सएमएल एसडीके और जेमबॉक्स.डॉक्यूमेंट। आप अपनी विशिष्ट आवश्यकताओं और प्राथमिकताओं के आधार पर Aspose.Words के विकल्प के रूप में इन पुस्तकालयों का पता लगा सकते हैं।