---
title: सापेक्ष क्षैतिज या ऊर्ध्वाधर स्थिति निर्धारित करें
linktitle: सापेक्ष क्षैतिज या ऊर्ध्वाधर स्थिति निर्धारित करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में तालिका की सापेक्ष क्षैतिज या ऊर्ध्वाधर स्थिति कैसे सेट करें, सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका की सापेक्ष क्षैतिज या ऊर्ध्वाधर स्थिति कैसे सेट करें। हम कोड को समझने और इस सुविधा को लागू करने के लिए चरण दर चरण मार्गदर्शिका का पालन करेंगे। इस ट्यूटोरियल के अंत तक, आप अपने Word दस्तावेज़ों में अपनी तालिका की सापेक्ष क्षैतिज या ऊर्ध्वाधर स्थिति निर्धारित करने में सक्षम होंगे।

## चरण 1: प्रोजेक्ट सेटअप
1. विज़ुअल स्टूडियो लॉन्च करें और एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ जोड़ें।

## चरण 2: दस्तावेज़ लोड करना
दस्तावेज़ के साथ वर्ड प्रोसेसिंग प्रारंभ करने के लिए, इन चरणों का पालन करें:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

अपने दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ "आपकी दस्तावेज़ निर्देशिका" को बदलना सुनिश्चित करें और सही फ़ाइल नाम प्रदान करें।

## चरण 3: तालिका की सापेक्ष स्थिति निर्धारित करना
इसके बाद, हम तालिका की सापेक्ष क्षैतिज या ऊर्ध्वाधर स्थिति निर्धारित करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
// तालिका पुनः प्राप्त करें
Table table = doc.FirstSection.Body.Tables[0];

//तालिका की सापेक्ष क्षैतिज स्थिति की परिभाषा
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// तालिका की सापेक्ष ऊर्ध्वाधर स्थिति को परिभाषित करें
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 यहां हम पहले खंड के मुख्य भाग से पहली तालिका को पुनः प्राप्त करने के लिए दस्तावेज़ का उपयोग करते हैं। इसके बाद, हम तालिका की सापेक्ष क्षैतिज स्थिति निर्धारित करते हैं`HorizontalAnchor` संपत्ति का उपयोग कर`RelativeHorizontalPosition.Column` कीमत। इसी प्रकार, हम तालिका की सापेक्ष ऊर्ध्वाधर स्थिति निर्धारित करते हैं`VerticalAnchor` संपत्ति का उपयोग कर`RelativeVerticalPosition.Page` कीमत।

## चरण 4: संशोधित दस्तावेज़ को सहेजना
अंत में, हमें संशोधित दस्तावेज़ को परिभाषित तालिका की सापेक्ष स्थिति के साथ सहेजने की आवश्यकता है। निम्नलिखित कोड का प्रयोग करें:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

आउटपुट दस्तावेज़ के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके सापेक्ष क्षैतिज या लंबवत स्थिति सेट करने के लिए नमूना स्रोत कोड 

```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में किसी तालिका की सापेक्ष क्षैतिज या ऊर्ध्वाधर स्थिति कैसे सेट की जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को लागू करके, आप इस सापेक्ष स्थिति को अपने Word दस्तावेज़ों में अपनी तालिकाओं पर लागू कर सकते हैं।