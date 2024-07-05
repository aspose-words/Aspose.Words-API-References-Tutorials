---
title: वर्ड दस्तावेज़ में बुकमार्क बनाएँ
linktitle: वर्ड दस्तावेज़ में बुकमार्क बनाएँ
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में बुकमार्क बनाना और PDF में बुकमार्क पूर्वावलोकन स्तर निर्दिष्ट करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-bookmarks/create-bookmark/
---

इस लेख में, हम ऊपर दिए गए C# स्रोत कोड का पता लगाएंगे ताकि यह समझा जा सके कि Aspose.Words for .NET लाइब्रेरी में बुकमार्क बनाएँ फ़ंक्शन का उपयोग कैसे करें। यह सुविधा आपको दस्तावेज़ में बुकमार्क बनाने और आउटपुट PDF फ़ाइल में बुकमार्क पूर्वावलोकन स्तर निर्दिष्ट करने की अनुमति देती है।

## आवश्यक शर्तें

- C# भाषा का मूलभूत ज्ञान.
- Aspose.Words लाइब्रेरी के साथ .NET विकास वातावरण स्थापित।

## चरण 1: दस्तावेज़ और जनरेटर बनाना

 बुकमार्क बनाने से पहले, हमें एक दस्तावेज़ और दस्तावेज़ बिल्डर बनाने की आवश्यकता है`Document` और`DocumentBuilder` वस्तुएं:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: मुख्य बुकमार्क बनाना

 हम उपयोग करते हैं`StartBookmark` मुख्य बुकमार्क शुरू करने की विधि और`EndBookmark` इसे समाप्त करने की विधि। बीच में, हम पाठ और अन्य बुकमार्क जोड़ सकते हैं:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// यहां अधिक बुकमार्क या पाठ जोड़ें.

builder. EndBookmark("My Bookmark");
```

## चरण 3: नेस्टेड बुकमार्क बनाना

 हम मुख्य बुकमार्क के अंदर नेस्टेड बुकमार्क भी बना सकते हैं। हम उसी का उपयोग करते हैं`StartBookmark` और`EndBookmark` नेस्टेड बुकमार्क बनाने और समाप्त करने के तरीके:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## चरण 4: आउटपुट PDF फ़ाइल में बुकमार्क पूर्वावलोकन स्तर निर्दिष्ट करना

 हम उपयोग करते हैं`PdfSaveOptions` आउटपुट पीडीएफ फाइल में बुकमार्क पूर्वावलोकन स्तर निर्दिष्ट करने के लिए ऑब्जेक्ट। हम इसका उपयोग करते हैं`BookmarksOutlineLevels` संपत्ति

  मुख्य बुकमार्क और नेस्टेड बुकमार्क को उनके संबंधित स्तरों के साथ जोड़ने के लिए:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### .NET के लिए Aspose.Words का उपयोग करके बुकमार्क बनाने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके बुकमार्क बनाने का प्रदर्शन करने के लिए यहां पूर्ण उदाहरण स्रोत कोड दिया गया है:

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## निष्कर्ष

इस लेख में, हमने .NET के लिए Aspose.Words के बुकमार्क बनाएँ फ़ंक्शन का उपयोग करने के तरीके को समझने के लिए C# स्रोत कोड का पता लगाया। हमने दस्तावेज़ में बुकमार्क बनाने और आउटपुट PDF फ़ाइल में बुकमार्क पूर्वावलोकन स्तर निर्दिष्ट करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन किया है।

### पूछे जाने वाले प्रश्न

#### प्रश्न: Aspose.Words for .NET में "बुकमार्क बनाएँ" फ़ंक्शन का उपयोग करने के लिए क्या पूर्वापेक्षाएँ हैं?

उत्तर: Aspose.Words for .NET में "बुकमार्क बनाएँ" फ़ंक्शन का उपयोग करने के लिए, आपको C# भाषा का बुनियादी ज्ञान होना चाहिए। आपको Aspose.Words लाइब्रेरी इंस्टॉल किए गए .NET डेवलपमेंट एनवायरनमेंट की भी आवश्यकता है।

#### प्रश्न: .NET के लिए Aspose.Words में दस्तावेज़ कैसे बनाएं?

 A: .NET के लिए Aspose.Words में एक दस्तावेज़ बनाने के लिए, आप इसका उपयोग कर सकते हैं`Document` क्लास. यहाँ एक नमूना कोड है:

```csharp
Document doc = new Document();
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में मास्टर बुकमार्क कैसे बनाएं?

 A: .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में मुख्य बुकमार्क बनाने के लिए, आप इसका उपयोग कर सकते हैं`StartBookmark` बुकमार्क शुरू करने के लिए विधि, अंदर पाठ या अन्य बुकमार्क जोड़ें, फिर उपयोग करें` EndBookmark` इसे समाप्त करने के लिए यहाँ एक नमूना कोड है:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके मुख्य बुकमार्क के अंदर नेस्टेड बुकमार्क कैसे बनाएं?

 उत्तर: .NET के लिए Aspose.Words का उपयोग करके मुख्य बुकमार्क के अंदर एक नेस्टेड बुकमार्क बनाने के लिए, आप उसी का उपयोग कर सकते हैं`StartBookmark` और`EndBookmark` नेस्टेड बुकमार्क को शुरू करने और समाप्त करने के तरीके। यहाँ एक नमूना कोड है:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके आउटपुट PDF में बुकमार्क पूर्वावलोकन स्तर कैसे निर्दिष्ट करें?

 उत्तर: .NET के लिए Aspose.Words का उपयोग करके आउटपुट PDF में बुकमार्क पूर्वावलोकन स्तर निर्दिष्ट करने के लिए, आप इसका उपयोग कर सकते हैं`PdfSaveOptions` वर्ग और`BookmarksOutlineLevels` प्रॉपर्टी। आप मुख्य बुकमार्क और नेस्टेड बुकमार्क को उनके संबंधित स्तरों के साथ जोड़ सकते हैं। यहाँ एक नमूना कोड है:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके बुकमार्क बनाने के बाद दस्तावेज़ को कैसे सहेजा जाए?

 A: .NET के लिए Aspose.Words का उपयोग करके बुकमार्क बनाने के बाद दस्तावेज़ को सहेजने के लिए, आप इसका उपयोग कर सकते हैं`Save` की विधि`Document` गंतव्य फ़ाइल पथ निर्दिष्ट करने वाला ऑब्जेक्ट। यहाँ एक नमूना कोड है:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके आउटपुट PDF में बुकमार्क पूर्वावलोकन स्तर कैसे निर्दिष्ट करें?

 उत्तर: .NET के लिए Aspose.Words का उपयोग करके आउटपुट PDF में बुकमार्क पूर्वावलोकन स्तर निर्दिष्ट करने के लिए, आप इसका उपयोग कर सकते हैं`PdfSaveOptions` वर्ग और`BookmarksOutlineLevels` प्रॉपर्टी। आप मुख्य बुकमार्क और नेस्टेड बुकमार्क को उनके संबंधित स्तरों के साथ जोड़ सकते हैं। यहाँ एक नमूना कोड है:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके मुख्य बुकमार्क के अंदर नेस्टेड बुकमार्क कैसे बनाएं?

 उत्तर: .NET के लिए Aspose.Words का उपयोग करके मुख्य बुकमार्क के अंदर नेस्टेड बुकमार्क बनाने के लिए, आप उसी का उपयोग कर सकते हैं`StartBookmark` और`EndBookmark` नेस्टेड बुकमार्क शुरू करने और खत्म करने के तरीके। कॉल करते समय पैरेंट बुकमार्क को पैरामीटर के रूप में निर्दिष्ट करना सुनिश्चित करें`StartBookmark` विधि। यहाँ एक नमूना कोड है:

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके बुकमार्क के अंदर टेक्स्ट कैसे जोड़ें?

 A: .NET के लिए Aspose.Words का उपयोग करके बुकमार्क के अंदर पाठ जोड़ने के लिए, आप इसका उपयोग कर सकते हैं`Write` की विधि`DocumentBuilder`जोड़ने के लिए पाठ निर्दिष्ट करने वाला ऑब्जेक्ट। यहाँ एक नमूना कोड है:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में मास्टर बुकमार्क कैसे बनाएं?

 A: .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में मुख्य बुकमार्क बनाने के लिए, आप इसका उपयोग कर सकते हैं`StartBookmark` बुकमार्क शुरू करने की विधि और`EndBookmark` इसे समाप्त करने की विधि। यहाँ एक नमूना कोड है:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```