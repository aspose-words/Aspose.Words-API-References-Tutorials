---
title: मेल मर्ज पर दस्तावेज़ डालें
linktitle: मेल मर्ज पर दस्तावेज़ डालें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके मेल मर्ज के दौरान दस्तावेज़ को दूसरे में डालने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
इस ट्यूटोरियल में, हम आपको बताएंगे कि .NET के लिए Aspose.Words के इन्सर्ट डॉक्यूमेंट ड्यूरिंग मेल मर्ज फीचर का उपयोग करके मेल मर्ज के दौरान किसी दस्तावेज़ को दूसरे दस्तावेज़ में कैसे सम्मिलित किया जाए। स्रोत कोड को समझने और दस्तावेज़ प्रविष्टि करने के लिए नीचे दिए गए चरणों का पालन करें।

## चरण 1: मुख्य दस्तावेज़ लोड हो रहा है

आरंभ करने के लिए, अपने दस्तावेज़ों के लिए निर्देशिका निर्दिष्ट करें और मुख्य दस्तावेज़ को दस्तावेज़ ऑब्जेक्ट में लोड करें। ऐसे:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## चरण 2: मेल मर्ज कॉन्फ़िगर करें

अब मेल मर्ज को कॉन्फ़िगर करें और किसी दस्तावेज़ को दूसरे दस्तावेज़ में सम्मिलित करने के लिए फ़ील्ड मर्ज कॉलबैक निर्दिष्ट करें। ऐसे:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## चरण 3: मेल मर्ज चलाना

हम मर्ज फ़ील्ड के नाम और संबंधित डेटा प्रदान करके मेल मर्ज चलाएंगे। ऐसे:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### .NET के लिए Aspose.Words का उपयोग करके मेल मर्ज पर दस्तावेज़ सम्मिलित करने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words के मेल मर्ज सुविधा में दस्तावेज़ सम्मिलित करने का संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// मुख्य दस्तावेज़ में एक मर्ज फ़ील्ड है जिसे "Document_1" कहा जाता है।
// इस फ़ील्ड के संबंधित डेटा में दस्तावेज़ के लिए पूर्णतः योग्य पथ शामिल है।
// उसे इस फ़ील्ड में डाला जाना चाहिए.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

इस कोड के साथ आप .NET के लिए Aspose.Words का उपयोग करके मेल मर्ज के दौरान एक दस्तावेज़ को दूसरे दस्तावेज़ में सम्मिलित करने में सक्षम होंगे। परिणामी दस्तावेज़ एक नए नाम के तहत सहेजा जाएगा


## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया कि .NET के लिए Aspose.Words के इन्सर्ट डॉक्यूमेंट ड्यूरिंग मेल मर्ज फीचर का उपयोग करके मेल मर्ज के दौरान किसी दस्तावेज़ को दूसरे दस्तावेज़ में कैसे सम्मिलित किया जाए। मेल मर्ज को कॉन्फ़िगर करके और आवश्यक डेटा प्रदान करके, आप विभिन्न दस्तावेज़ टेम्पलेट्स या अनुभागों को मर्ज करके दस्तावेजों को गतिशील रूप से इकट्ठा कर सकते हैं। .NET के लिए Aspose.Words जटिल दस्तावेज़ निर्माण परिदृश्यों को प्रबंधित करने का एक लचीला और शक्तिशाली तरीका प्रदान करता है, जो इसे दस्तावेज़ निर्माण और हेरफेर कार्यों को स्वचालित करने के लिए एक मूल्यवान उपकरण बनाता है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मेल मर्ज के दौरान एक दस्तावेज़ को दूसरे दस्तावेज़ में डालने का क्या उद्देश्य है?

उ: मेल मर्ज के दौरान एक दस्तावेज़ को दूसरे दस्तावेज़ में सम्मिलित करने से आप मर्ज प्रक्रिया के दौरान प्रदान किए गए डेटा के आधार पर विभिन्न दस्तावेज़ टेम्पलेट्स या अनुभागों को गतिशील रूप से संयोजित कर सकते हैं। यह सुविधा विशेष रूप से तब उपयोगी होती है जब आप विभिन्न पूर्व-निर्धारित टेम्पलेट्स या अनुभागों को अंतिम दस्तावेज़ में मर्ज करके जटिल दस्तावेज़ों को इकट्ठा करना चाहते हैं।

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके मेल मर्ज के दौरान किसी दस्तावेज़ को दूसरे दस्तावेज़ में कैसे सम्मिलित करूँ?

उ: .NET के लिए Aspose.Words का उपयोग करके मेल मर्ज के दौरान किसी दस्तावेज़ को दूसरे दस्तावेज़ में सम्मिलित करने के लिए, इन चरणों का पालन करें:
1. मुख्य दस्तावेज़ को लोड करें जो आधार के रूप में दस्तावेज़ ऑब्जेक्ट में काम करेगा।
2. मेल मर्ज को कॉन्फ़िगर करें और दस्तावेज़ प्रविष्टि को संभालने के लिए फ़ील्ड मर्ज कॉलबैक निर्दिष्ट करें।
3. मेल मर्ज को मर्ज फ़ील्ड के नाम और संबंधित डेटा (डाले जाने वाले दस्तावेज़ का पथ) के साथ चलाएँ।

#### प्रश्न: मैं मेल मर्ज के दौरान सम्मिलन व्यवहार को कैसे अनुकूलित कर सकता हूँ?

उ: मेल मर्ज के दौरान सम्मिलन व्यवहार को अनुकूलित करने के लिए, आप IFieldMergingCallback इंटरफ़ेस से इनहेरिट करके एक कस्टम फ़ील्डमर्जिंगकॉलबैक लागू कर सकते हैं। यह आपको यह नियंत्रित करने की अनुमति देता है कि आपकी विशिष्ट आवश्यकताओं के आधार पर दस्तावेज़ों को कैसे डाला और मर्ज किया जाए।

#### प्रश्न: क्या मैं मेल मर्ज के दौरान एकाधिक दस्तावेज़ सम्मिलित कर सकता हूँ?

उ: हां, आप प्रत्येक मर्ज फ़ील्ड के लिए उचित डेटा प्रदान करके मेल मर्ज के दौरान एकाधिक दस्तावेज़ सम्मिलित कर सकते हैं। प्रत्येक मर्ज फ़ील्ड के लिए जिसमें दस्तावेज़ प्रविष्टि की आवश्यकता होती है, डेटा के रूप में संबंधित दस्तावेज़ का पथ निर्दिष्ट करें।

