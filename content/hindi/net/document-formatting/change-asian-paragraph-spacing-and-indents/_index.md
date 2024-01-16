---
title: वर्ड दस्तावेज़ में एशियाई पैराग्राफ रिक्ति और इंडेंट बदलें
linktitle: वर्ड दस्तावेज़ में एशियाई पैराग्राफ रिक्ति और इंडेंट बदलें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ वर्ड दस्तावेज़ में एशियाई पैराग्राफ रिक्ति और इंडेंट को बदलना सीखें।
type: docs
weight: 10
url: /hi/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
इस ट्यूटोरियल में, हम आपको बताएंगे कि .NET के लिए Aspose.Words का उपयोग करके एशियाई पैराग्राफ की रिक्ति और इंडेंट को कैसे बदला जाए। स्रोत कोड को समझने और परिवर्तन लागू करने के लिए नीचे दिए गए चरणों का पालन करें।

## चरण 1: दस्तावेज़ लोड करना

आरंभ करने के लिए, अपने दस्तावेज़ों के लिए निर्देशिका निर्दिष्ट करें और एशियाई टाइपोग्राफी वाले दस्तावेज़ को दस्तावेज़ ऑब्जेक्ट में लोड करें। ऐसे:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## चरण 2: पैराग्राफ रिक्ति और इंडेंट बदलना

अब हम एशियाई दस्तावेज़ के पहले पैराग्राफ की रिक्ति और इंडेंट को संशोधित करेंगे। ऐसे:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // पैराग्राफफॉर्मेट.लेफ्टइंडेंट को अपडेट करें
format.CharacterUnitRightIndent = 10; // पैराग्राफफॉर्मेट.राइटइंडेंट को अपडेट करें
format.CharacterUnitFirstLineIndent = 20; //पैराग्राफफॉर्मेट.फर्स्टलाइनइंडेंट को अपडेट करें
format.LineUnitBefore = 5; // ParagraphFormat.SpaceBefore अपडेट करें
format.LineUnitAfter = 10; // पैराग्राफफॉर्मेट.स्पेसआफ्टर को अपडेट करें
```

## चरण 3: दस्तावेज़ सहेजना

 टेक्स्ट इनपुट फॉर्म फ़ील्ड डालने के बाद, दस्तावेज़ को वांछित स्थान पर सहेजें`Save` तरीका। उचित फ़ाइल पथ प्रदान करना सुनिश्चित करें:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### .NET के लिए Aspose.Words का उपयोग करके एशियन पैराग्राफ स्पेसिंग और इंडेंट बदलने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words के साथ एशियाई पैराग्राफ स्पेसिंग और इंडेंट संपादित करें सुविधा के लिए संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent को अपडेट किया जाएगा
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent को अपडेट किया जाएगा
	format.CharacterUnitFirstLineIndent = 20;  // ParagraphFormat.FirstLineIndent को अपडेट किया जाएगा
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore अपडेट किया जाएगा
	format.LineUnitAfter = 10;                 // पैराग्राफफॉर्मेट.स्पेसआफ्टर अपडेट किया जाएगा

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

इस कोड की मदद से आप .NET के लिए Aspose.Words का उपयोग करके एशियाई पैराग्राफ की रिक्ति और इंडेंट को बदलने में सक्षम होंगे।

## निष्कर्ष

 इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके एशियाई पैराग्राफ की रिक्ति और इंडेंट को कैसे बदला जाए। के प्रासंगिक गुणों को संशोधित करके`ParagraphFormat`हम किसी Word दस्तावेज़ में एशियाई पैराग्राफ़ों के लेआउट और स्वरूप को नियंत्रित कर सकते हैं। यह सुविधा एशियाई अक्षरों के साथ पाठ के स्वरूपण को अनुकूलित करने और मिश्रित भाषा सामग्री वाले दस्तावेज़ों में वांछित दृश्य प्रस्तुति प्राप्त करने के लिए उपयोगी है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में "चेंज एशियन पैराग्राफ स्पेसिंग एंड इंडेंट" फीचर क्या करता है?

उ: .NET के लिए Aspose.Words में "एशियन पैराग्राफ स्पेसिंग और इंडेंट बदलें" सुविधा आपको वर्ड दस्तावेज़ में एशियन पैराग्राफ के स्पेसिंग और इंडेंटेशन गुणों को संशोधित करने की अनुमति देती है। आप पैराग्राफ के लेआउट और स्वरूप को नियंत्रित करने के लिए बाएँ और दाएँ इंडेंट, पहली पंक्ति के इंडेंट, पहले स्थान और मानों के बाद स्थान को समायोजित कर सकते हैं।

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके एशियाई पैराग्राफ की रिक्ति और इंडेंट कैसे बदलूं?

 उ: किसी एशियाई पैराग्राफ की रिक्ति और इंडेंट को बदलने के लिए, आपको इसका उपयोग करना होगा`ParagraphFormat`लक्ष्य पैराग्राफ का और उसके प्रासंगिक गुणों को संशोधित करें। प्रदान किए गए उदाहरण कोड में, हम दस्तावेज़ के पहले पैराग्राफ तक पहुंचते हैं और सेट करते हैं`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , और`LineUnitAfter` रिक्ति और इंडेंट को समायोजित करने के लिए गुण।

#### प्रश्न: क्या मैं इन परिवर्तनों को दस्तावेज़ के अन्य अनुच्छेदों पर लागू कर सकता हूँ?

 उत्तर: हाँ, आप इन परिवर्तनों को दस्तावेज़ के अन्य अनुच्छेदों तक पहुँचकर उन पर लागू कर सकते हैं`ParagraphFormat` वस्तुएं. उदाहरण कोड दस्तावेज़ के पहले पैराग्राफ को लक्षित करता है, लेकिन आप इसमें अनुक्रमणिका को समायोजित करके अन्य पैराग्राफ को संशोधित कर सकते हैं`Paragraphs` वांछित अनुच्छेदों का चयन करने के लिए संग्रह करना या अन्य मानदंडों का उपयोग करना।