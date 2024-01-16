---
title: Word दस्तावेज़ मर्ज करें
linktitle: दस्तावेज़ मर्ज करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके एकाधिक Word दस्तावेज़ों को मर्ज करना सीखें। यह शक्तिशाली एपीआई दस्तावेज़ों को मर्ज करने की प्रक्रिया को सरल बनाता है, जिससे यह कुशल और सरल हो जाती है।
type: docs
weight: 10
url: /hi/net/split-document/merge-documents/
---

इस ट्यूटोरियल में, हम आपको बताएंगे कि .NET के लिए Aspose.Words के मर्ज दस्तावेज़ सुविधा का उपयोग करके एकाधिक Word दस्तावेज़ों को कैसे मर्ज किया जाए। स्रोत कोड को समझने और सभी स्रोत दस्तावेज़ों वाला एक मर्ज किया गया दस्तावेज़ प्राप्त करने के लिए नीचे दिए गए चरणों का पालन करें।

## चरण 1: मर्ज करने के लिए दस्तावेज़ खोजें

दस्तावेज़ों को मर्ज करने से पहले, हमें मर्ज किए जाने वाले स्रोत दस्तावेज़ों का पता लगाना होगा। ऐसे:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// मर्ज करने के लिए दस्तावेज़ खोजें.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## चरण 2: दस्तावेज़ मर्ज करें

अब हम अंतिम मर्ज किए गए दस्तावेज़ बनाने के लिए दस्तावेज़ों को एक-एक करके मर्ज करेंगे। ऐसे:

```csharp
// परिणामी दस्तावेज़ का पहला भाग खोलें.
Document sourceDoc = new Document(sourceDocumentPath);

// एक नया परिणामी दस्तावेज़ बनाएँ।
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// दस्तावेज़ों को एक-एक करके मर्ज करें।
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ों को मर्ज करने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words के मर्ज दस्तावेज़ सुविधा का संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// मर्ज के लिए उपयोग किए जाने वाले दस्तावेज़ ढूंढें।
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// परिणामी दस्तावेज़ का पहला भाग खोलें.
Document sourceDoc = new Document(sourceDocumentPath);

// एक नया परिणामी दस्तावेज़ बनाएँ।
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// दस्तावेज़ के हिस्सों को एक-एक करके मर्ज करें।
foreach (FileSystemInfo documentPath in documentPaths)
{
	if (documentPath.FullName == sourceDocumentPath)
		continue;

	mergedDocBuilder.MoveToDocumentEnd();
	mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
	sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

## निष्कर्ष

बधाई हो! आपने सीखा है कि .NET के लिए Aspose.Words के मर्ज दस्तावेज़ सुविधा का उपयोग करके एकाधिक Word दस्तावेज़ों को कैसे मर्ज किया जाए। दिए गए स्रोत कोड का पालन करके, आप प्रत्येक स्रोत दस्तावेज़ के स्वरूपण को संरक्षित करते हुए अलग-अलग दस्तावेज़ों को एक मर्ज किए गए दस्तावेज़ में जोड़ सकते हैं।

दस्तावेज़ों को मर्ज करना तब उपयोगी हो सकता है जब आप कई स्रोतों से जानकारी को समेकित करना चाहते हैं या अलग-अलग हिस्सों से एक एकीकृत दस्तावेज़ बनाना चाहते हैं। .NET के लिए Aspose.Words एक शक्तिशाली एपीआई प्रदान करता है जो दस्तावेज़ों को मर्ज करने की प्रक्रिया को सरल बनाता है, इसे कुशल और सीधा बनाता है।

अपनी दस्तावेज़ प्रसंस्करण क्षमताओं को बढ़ाने और अपने वर्कफ़्लो को सुव्यवस्थित करने के लिए .NET के लिए Aspose.Words द्वारा दी गई अन्य सुविधाओं का बेझिझक पता लगाएं।

### पूछे जाने वाले प्रश्न

#### मैं भिन्न स्वरूपण वाले दस्तावेज़ों को कैसे मर्ज कर सकता हूँ?

 दस्तावेज़ों को मर्ज करते समय, .NET के लिए Aspose.Words प्रत्येक स्रोत दस्तावेज़ के स्वरूपण को संरक्षित करने का विकल्प प्रदान करता है। का उपयोग करके`ImportFormatMode.KeepSourceFormatting` विकल्प, मर्ज किए गए दस्तावेज़ मूल दस्तावेज़ों के स्वरूपण को बनाए रखेंगे। यदि आप मर्ज किए गए दस्तावेज़ में लगातार फ़ॉर्मेटिंग लागू करना चाहते हैं, तो आप दस्तावेज़ों को मर्ज करने के बाद Aspose.Words API का उपयोग करके फ़ॉर्मेटिंग को संशोधित कर सकते हैं।

#### क्या मैं दस्तावेज़ों को विभिन्न प्रारूपों में मर्ज कर सकता हूँ?

हाँ, .NET के लिए Aspose.Words DOCX, DOC, RTF और अन्य सहित विभिन्न स्वरूपों में दस्तावेज़ों को मर्ज करने का समर्थन करता है। आप विभिन्न प्रारूपों के दस्तावेज़ों को Aspose.Words API में लोड कर सकते हैं और उनके मूल प्रारूपों की परवाह किए बिना उन्हें एक ही दस्तावेज़ में मर्ज कर सकते हैं।

#### क्या मैं दस्तावेज़ों को तालिकाओं और छवियों जैसी जटिल संरचनाओं के साथ मर्ज कर सकता हूँ?

बिल्कुल! .NET के लिए Aspose.Words तालिकाओं, छवियों, शीर्षलेखों, पादलेखों और अन्य सहित जटिल संरचनाओं वाले दस्तावेज़ों को मर्ज करने में सक्षम है। एपीआई प्रत्येक दस्तावेज़ में सामग्री की अखंडता और लेआउट को संरक्षित करते हुए विलय प्रक्रिया को संभालता है।

#### क्या विभिन्न पेज ओरिएंटेशन या आकार वाले दस्तावेज़ों को मर्ज करना संभव है?

हाँ, .NET के लिए Aspose.Words विलय प्रक्रिया के दौरान विभिन्न पेज ओरिएंटेशन या आकार वाले दस्तावेज़ों को संभालता है। परिणामी मर्ज किया गया दस्तावेज़ स्रोत दस्तावेज़ों के अलग-अलग पेज ओरिएंटेशन और आकार को समायोजित करेगा।