---
title: वर्ड डॉक्यूमेंट में बुकमार्क बनाएं
linktitle: वर्ड डॉक्यूमेंट में बुकमार्क बनाएं
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि वर्ड दस्तावेज़ में बुकमार्क कैसे बनाएं और .NET के लिए Aspose.Words का उपयोग करके पीडीएफ में बुकमार्क पूर्वावलोकन स्तर निर्दिष्ट करें।
type: docs
weight: 10
url: /hi/net/programming-with-bookmarks/create-bookmark/
---

इस लेख में, हम .NET लाइब्रेरी के लिए Aspose.Words में Create Bookmark फ़ंक्शन का उपयोग करने के तरीके को समझने के लिए उपरोक्त C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको किसी दस्तावेज़ में बुकमार्क बनाने और आउटपुट पीडीएफ फ़ाइल में बुकमार्क पूर्वावलोकन स्तर निर्दिष्ट करने की अनुमति देती है।

## आवश्यक शर्तें

- C# भाषा का बुनियादी ज्ञान।
- Aspose.Words लाइब्रेरी के साथ .NET विकास वातावरण स्थापित।

## चरण 1: दस्तावेज़ और जेनरेटर बनाना

 बुकमार्क बनाने से पहले, हमें इसका उपयोग करके एक दस्तावेज़ और एक दस्तावेज़ बिल्डर बनाना होगा`Document` और`DocumentBuilder` वस्तुएं:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: मुख्य बुकमार्क बनाना

 हम उपयोग करते हैं`StartBookmark` मुख्य बुकमार्क प्रारंभ करने की विधि और`EndBookmark` इसे ख़त्म करने की विधि. बीच में, हम टेक्स्ट और अन्य बुकमार्क जोड़ सकते हैं:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// यहां अधिक बुकमार्क या टेक्स्ट जोड़ें.

builder. EndBookmark("My Bookmark");
```

## चरण 3: नेस्टेड बुकमार्क बनाना

हम मुख्य बुकमार्क के अंदर नेस्टेड बुकमार्क भी बना सकते हैं। हम उसी का प्रयोग करते हैं`StartBookmark` और`EndBookmark` नेस्टेड बुकमार्क बनाने और समाप्त करने की विधियाँ:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## चरण 4: आउटपुट पीडीएफ फ़ाइल में बुकमार्क पूर्वावलोकन स्तर निर्दिष्ट करना

 हम उपयोग करते हैं`PdfSaveOptions` आउटपुट पीडीएफ फ़ाइल में बुकमार्क पूर्वावलोकन स्तर निर्दिष्ट करने के लिए ऑब्जेक्ट। हम उपयोग करते हैं`BookmarksOutlineLevels` संपत्ति

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

इस लेख में, हमने .NET के लिए Aspose.Words के क्रिएट बुकमार्क फ़ंक्शन का उपयोग करने के तरीके को समझने के लिए C# स्रोत कोड की खोज की। हमने दस्तावेज़ में बुकमार्क बनाने और आउटपुट पीडीएफ फ़ाइल में बुकमार्क पूर्वावलोकन स्तर निर्दिष्ट करने के लिए चरण-दर-चरण मार्गदर्शिका का पालन किया है।

### पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में "बुकमार्क बनाएं" फ़ंक्शन का उपयोग करने के लिए क्या शर्तें हैं?

उ: .NET के लिए Aspose.Words में "बुकमार्क बनाएं" फ़ंक्शन का उपयोग करने के लिए, आपको C# भाषा का बुनियादी ज्ञान होना चाहिए। आपको Aspose.Words लाइब्रेरी स्थापित करने के साथ एक .NET विकास परिवेश की भी आवश्यकता है।

#### प्रश्न: .NET के लिए Aspose.Words में दस्तावेज़ कैसे बनाएं?

 उ: .NET के लिए Aspose.Words में एक दस्तावेज़ बनाने के लिए, आप इसका उपयोग कर सकते हैं`Document` कक्षा। यहाँ एक नमूना कोड है:

```csharp
Document doc = new Document();
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में मास्टर बुकमार्क कैसे बनाएं?

 उ: .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में एक मुख्य बुकमार्क बनाने के लिए, आप इसका उपयोग कर सकते हैं`StartBookmark` बुकमार्क शुरू करने की विधि, अंदर टेक्स्ट या अन्य बुकमार्क जोड़ें, फिर इसका उपयोग करें` EndBookmark` इसे ख़त्म करने के लिए. यहाँ एक नमूना कोड है:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके मुख्य बुकमार्क के अंदर नेस्टेड बुकमार्क कैसे बनाएं?

 उ: .NET के लिए Aspose.Words का उपयोग करके मुख्य बुकमार्क के अंदर एक नेस्टेड बुकमार्क बनाने के लिए, आप इसका उपयोग कर सकते हैं`StartBookmark` और`EndBookmark` नेस्टेड बुकमार्क को प्रारंभ और समाप्त करने की विधियाँ। यहाँ एक नमूना कोड है:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके आउटपुट पीडीएफ में बुकमार्क पूर्वावलोकन स्तर कैसे निर्दिष्ट करें?

 उ: .NET के लिए Aspose.Words का उपयोग करके आउटपुट पीडीएफ में बुकमार्क पूर्वावलोकन स्तर निर्दिष्ट करने के लिए, आप इसका उपयोग कर सकते हैं`PdfSaveOptions` कक्षा और`BookmarksOutlineLevels` संपत्ति। आप मुख्य बुकमार्क और नेस्टेड बुकमार्क को उनके संबंधित स्तरों के साथ जोड़ सकते हैं। यहाँ एक नमूना कोड है:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके बुकमार्क बनाने के बाद दस्तावेज़ को कैसे सहेजें?

 उ: .NET के लिए Aspose.Words का उपयोग करके बुकमार्क बनाने के बाद किसी दस्तावेज़ को सहेजने के लिए, आप इसका उपयोग कर सकते हैं`Save` की विधि`Document` गंतव्य फ़ाइल पथ निर्दिष्ट करने वाली वस्तु। यहाँ एक नमूना कोड है:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके आउटपुट पीडीएफ में बुकमार्क पूर्वावलोकन स्तर कैसे निर्दिष्ट करें?

 उ: .NET के लिए Aspose.Words का उपयोग करके आउटपुट पीडीएफ में बुकमार्क पूर्वावलोकन स्तर निर्दिष्ट करने के लिए, आप इसका उपयोग कर सकते हैं`PdfSaveOptions` कक्षा और`BookmarksOutlineLevels` संपत्ति। आप मुख्य बुकमार्क और नेस्टेड बुकमार्क को उनके संबंधित स्तरों के साथ जोड़ सकते हैं। यहाँ एक नमूना कोड है:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके मुख्य बुकमार्क के अंदर नेस्टेड बुकमार्क कैसे बनाएं?

 उ: .NET के लिए Aspose.Words का उपयोग करके मुख्य बुकमार्क के अंदर नेस्टेड बुकमार्क बनाने के लिए, आप इसका उपयोग कर सकते हैं`StartBookmark` और`EndBookmark` नेस्टेड बुकमार्क प्रारंभ और समाप्त करने की विधियाँ। कॉल करते समय पैरेंट बुकमार्क को एक पैरामीटर के रूप में निर्दिष्ट करना सुनिश्चित करें`StartBookmark` तरीका। यहाँ एक नमूना कोड है:

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

 उ: .NET के लिए Aspose.Words का उपयोग करके बुकमार्क के अंदर टेक्स्ट जोड़ने के लिए, आप इसका उपयोग कर सकते हैं`Write` की विधि`DocumentBuilder`जोड़ने के लिए पाठ को निर्दिष्ट करने वाली वस्तु। यहाँ एक नमूना कोड है:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में मास्टर बुकमार्क कैसे बनाएं?

 उ: .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में एक मुख्य बुकमार्क बनाने के लिए, आप इसका उपयोग कर सकते हैं`StartBookmark` बुकमार्क प्रारंभ करने की विधि और`EndBookmark` इसे ख़त्म करने की विधि. यहाँ एक नमूना कोड है:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```