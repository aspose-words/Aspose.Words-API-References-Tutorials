---
title: जावा के लिए Aspose.Words में दस्तावेज़ों की क्लोनिंग और संयोजन
linktitle: दस्तावेज़ों की क्लोनिंग और संयोजन
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words में दस्तावेज़ों को क्लोन और संयोजित करना सीखें। स्रोत कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 27
url: /hi/java/document-manipulation/cloning-and-combining-documents/
---

## जावा के लिए Aspose.Words में दस्तावेज़ों की क्लोनिंग और संयोजन का परिचय

इस ट्यूटोरियल में, हम देखेंगे कि Java के लिए Aspose.Words का उपयोग करके दस्तावेज़ों को कैसे क्लोन और संयोजित किया जाए। हम विभिन्न परिदृश्यों को कवर करेंगे, जिसमें दस्तावेज़ की क्लोनिंग, प्रतिस्थापन बिंदुओं, बुकमार्क पर दस्तावेज़ सम्मिलित करना और मेल मर्ज ऑपरेशन के दौरान शामिल हैं।

## चरण 1: किसी दस्तावेज़ की क्लोनिंग करना

 जावा के लिए Aspose.Words में किसी दस्तावेज़ को क्लोन करने के लिए, आप इसका उपयोग कर सकते हैं`deepClone()` तरीका। यहाँ एक सरल उदाहरण है:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "CloneAndCombineDocuments.CloningDocument.docx");
```

यह कोड मूल दस्तावेज़ का एक गहरा क्लोन बनाएगा और इसे एक नई फ़ाइल के रूप में सहेजेगा।

## चरण 2: प्रतिस्थापन बिंदुओं पर दस्तावेज़ सम्मिलित करना

आप किसी अन्य दस्तावेज़ में विशिष्ट प्रतिस्थापन बिंदुओं पर दस्तावेज़ सम्मिलित कर सकते हैं। यहां बताया गया है कि आप यह कैसे कर सकते हैं:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
FindReplaceOptions options = new FindReplaceOptions();
options.setDirection(FindReplaceDirection.BACKWARD);
options.setReplacingCallback(new InsertDocumentAtReplaceHandler());
mainDoc.getRange().replace(Pattern.compile("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

 इस उदाहरण में, हम a का उपयोग करते हैं`FindReplaceOptions` प्रतिस्थापन के लिए कॉलबैक हैंडलर निर्दिष्ट करने के लिए ऑब्जेक्ट।`InsertDocumentAtReplaceHandler` क्लास सम्मिलन तर्क को संभालता है।

## चरण 3: बुकमार्क पर दस्तावेज़ सम्मिलित करना

किसी दस्तावेज़ को किसी अन्य दस्तावेज़ में किसी विशिष्ट बुकमार्क पर सम्मिलित करने के लिए, आप निम्नलिखित कोड का उपयोग कर सकते हैं:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
Document subDoc = new Document("Your Directory Path" + "Document insertion 2.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("insertionPlace");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtBookmark.docx");
```

 यहां, हम नाम से बुकमार्क ढूंढते हैं और उसका उपयोग करते हैं`insertDocument` की सामग्री सम्मिलित करने की विधि`subDoc` बुकमार्क स्थान पर दस्तावेज़.

## चरण 4: मेल मर्ज के दौरान दस्तावेज़ सम्मिलित करना

आप जावा के लिए Aspose.Words में मेल मर्ज ऑपरेशन के दौरान दस्तावेज़ सम्मिलित कर सकते हैं। ऐसे:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "Document_1" }, new Object[] { "Your Directory Path" + "Document insertion 2.docx" });
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

 इस उदाहरण में, हम का उपयोग करके एक फ़ील्ड मर्जिंग कॉलबैक सेट करते हैं`InsertDocumentAtMailMergeHandler` "Document_1" फ़ील्ड द्वारा निर्दिष्ट दस्तावेज़ के सम्मिलन को संभालने के लिए क्लास।

## निष्कर्ष

जावा के लिए Aspose.Words में दस्तावेज़ों की क्लोनिंग और संयोजन विभिन्न तकनीकों का उपयोग करके पूरा किया जा सकता है। चाहे आपको किसी दस्तावेज़ को क्लोन करने की आवश्यकता हो, प्रतिस्थापन बिंदुओं, बुकमार्क पर या मेल मर्ज के दौरान सामग्री डालने की आवश्यकता हो, Aspose.Words दस्तावेज़ों में निर्बाध रूप से हेरफेर करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Java के लिए Aspose.Words में किसी दस्तावेज़ का क्लोन कैसे बनाऊं?

 आप इसका उपयोग करके जावा के लिए Aspose.Words में किसी दस्तावेज़ को क्लोन कर सकते हैं`deepClone()` तरीका। यहाँ एक उदाहरण है:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "ClonedDocument.docx");
```

### मैं किसी बुकमार्क पर कोई दस्तावेज़ कैसे सम्मिलित कर सकता हूँ?

 जावा के लिए Aspose.Words में बुकमार्क पर एक दस्तावेज़ सम्मिलित करने के लिए, आप बुकमार्क को नाम से ढूंढ सकते हैं और फिर इसका उपयोग कर सकते हैं`insertDocument` सामग्री सम्मिलित करने की विधि. यहाँ एक उदाहरण है:

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
Document subDoc = new Document("Your Directory Path" + "SubDocument.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("MyBookmark");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CombinedDocument.docx");
```

### मैं Java के लिए Aspose.Words में मेल मर्ज के दौरान दस्तावेज़ कैसे सम्मिलित करूँ?

आप जावा के लिए Aspose.Words में मेल मर्ज के दौरान एक फ़ील्ड मर्जिंग कॉलबैक सेट करके और सम्मिलित किए जाने वाले दस्तावेज़ को निर्दिष्ट करके दस्तावेज़ सम्मिलित कर सकते हैं। यहाँ एक उदाहरण है:

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "DocumentField" }, new Object[] { "Your Directory Path" + "DocumentToInsert.docx" });
mainDoc.save("Your Directory Path" + "MergedDocument.docx");
```

 इस उदाहरण में,`InsertDocumentAtMailMergeHandler`मेल मर्ज के दौरान क्लास "डॉक्यूमेंटफ़ील्ड" के लिए सम्मिलन तर्क को संभालता है।