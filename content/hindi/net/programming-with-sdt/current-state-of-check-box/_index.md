---
title: चेक बॉक्स की वर्तमान स्थिति
linktitle: चेक बॉक्स की वर्तमान स्थिति
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में चेक बॉक्स सामग्री नियंत्रण की वर्तमान स्थिति को पुनर्प्राप्त और सेट करने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/current-state-of-check-box/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में चेक बॉक्स सामग्री नियंत्रण की वर्तमान स्थिति को कैसे पुनर्प्राप्त और सेट किया जाए। आप चेक बॉक्स को उसकी वर्तमान स्थिति के आधार पर चेक या अनचेक कर सकते हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, आपके पास निम्नलिखित होना चाहिए:

- .NET लाइब्रेरी के लिए Aspose.Words स्थापित।
- वर्ड दस्तावेजों के साथ सी# और वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करके प्रारंभ करें। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आपका दस्तावेज़ स्थित है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ लोड करें और चेक बॉक्स सामग्री नियंत्रण पुनः प्राप्त करें
 का उपयोग करके Word दस्तावेज़ लोड करें`Document` कंस्ट्रक्टर, एक पैरामीटर के रूप में दस्तावेज़ का पथ पास कर रहा है। फिर, दस्तावेज़ से वांछित चेक बॉक्स सामग्री नियंत्रण पुनः प्राप्त करें। इस उदाहरण में, हम मानते हैं कि चेक बॉक्स दस्तावेज़ में पहला संरचित दस्तावेज़ टैग है।

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## चरण 3: चेक बॉक्स को उसकी वर्तमान स्थिति के आधार पर चेक या अनचेक करें
 जांचें कि पुनर्प्राप्त संरचित दस्तावेज़ टैग प्रकार का है या नहीं`SdtType.Checkbox` . यदि ऐसा है, तो सेट करें`Checked` सामग्री नियंत्रण की संपत्ति`true` बॉक्स को चेक करने के लिए. अन्यथा, आप इसे अनियंत्रित छोड़ सकते हैं.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## चरण 4: दस्तावेज़ सहेजें
 का उपयोग करके संशोधित दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save`तरीका। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.CurrentStateOfCheckBox.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके चेक बॉक्स की वर्तमान स्थिति के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// दस्तावेज़ से पहला सामग्री नियंत्रण प्राप्त करें.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ में चेक बॉक्स सामग्री नियंत्रण की वर्तमान स्थिति को सफलतापूर्वक पुनर्प्राप्त और सेट कर लिया है।