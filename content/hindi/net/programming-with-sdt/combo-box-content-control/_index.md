---
title: कॉम्बो बॉक्स सामग्री नियंत्रण
linktitle: कॉम्बो बॉक्स सामग्री नियंत्रण
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में कॉम्बो बॉक्स सामग्री नियंत्रण बनाना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/combo-box-content-control/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में कॉम्बो बॉक्स कंटेंट कंट्रोल कैसे बनाया जाता है। कॉम्बो बॉक्स कंटेंट कंट्रोल उपयोगकर्ताओं को ड्रॉपडाउन सूची से कोई आइटम चुनने की अनुमति देता है।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए आपके पास निम्नलिखित चीजें होनी चाहिए:

- Aspose.Words for .NET लाइब्रेरी स्थापित की गई।
- C# और वर्ड दस्तावेजों के साथ वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपने दस्तावेज़ निर्देशिका का पथ सेट करके आरंभ करें।`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहाँ आप दस्तावेज़ को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक दस्तावेज़ और संरचित दस्तावेज़ टैग बनाएँ
 एक नया उदाहरण बनाएँ`Document` कक्षा और एक`StructuredDocumentTag` कॉम्बो बॉक्स सामग्री नियंत्रण का प्रतिनिधित्व करने के लिए। निर्दिष्ट करें`SdtType.ComboBox` प्रकार और`MarkupLevel.Block` ब्लॉक-स्तरीय कॉम्बो बॉक्स बनाने के लिए मार्कअप स्तर के रूप में।

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## चरण 3: कॉम्बो बॉक्स में आइटम जोड़ें
 का उपयोग करके कॉम्बो बॉक्स में आइटम जोड़ें`ListItems` की संपत्ति`StructuredDocumentTag` प्रत्येक आइटम को एक द्वारा दर्शाया गया है`SdtListItem` ऑब्जेक्ट, जो एक डिस्प्ले टेक्स्ट और एक मान लेता है। इस उदाहरण में, हम कॉम्बो बॉक्स में तीन आइटम जोड़ते हैं।

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## चरण 4: दस्तावेज़ में StructuredDocumentTag जोड़ें
 का उपयोग करके दस्तावेज़ के मुख्य भाग में कॉम्बो बॉक्स सामग्री नियंत्रण जोड़ें`AppendChild` दस्तावेज़ के प्रथम भाग के मुख्य भाग की विधि।

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## चरण 5: दस्तावेज़ सहेजें
 दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.ComboBoxContentControl.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके कॉम्बो बॉक्स सामग्री नियंत्रण के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

बस! आपने .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ में सफलतापूर्वक कॉम्बो बॉक्स सामग्री नियंत्रण बना लिया है।