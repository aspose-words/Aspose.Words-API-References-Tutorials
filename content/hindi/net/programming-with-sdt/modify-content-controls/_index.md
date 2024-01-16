---
title: सामग्री नियंत्रण संशोधित करें
linktitle: सामग्री नियंत्रण संशोधित करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में सामग्री नियंत्रण के भीतर टेक्स्ट, ड्रॉपडाउन सूचियों और छवियों को संशोधित करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/modify-content-controls/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में विभिन्न प्रकार के सामग्री नियंत्रणों को कैसे संशोधित किया जाए। आप टेक्स्ट को अपडेट कर सकते हैं, ड्रॉपडाउन सूची का चयनित मान, या सामग्री नियंत्रण के भीतर एक छवि को बदल सकते हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, आपके पास निम्नलिखित होना चाहिए:

- .NET लाइब्रेरी के लिए Aspose.Words स्थापित।
- वर्ड दस्तावेजों के साथ सी# और वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करके प्रारंभ करें। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आपका दस्तावेज़ स्थित है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ लोड करें और सामग्री नियंत्रणों पर पुनरावृति करें
 का उपयोग करके Word दस्तावेज़ लोड करें`Document`कंस्ट्रक्टर, एक पैरामीटर के रूप में दस्तावेज़ का पथ पास कर रहा है। का उपयोग करके दस्तावेज़ में सभी संरचित दस्तावेज़ टैग पर पुनरावृति करें`foreach` कुंडली।

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // सामग्री नियंत्रण के प्रकार के आधार पर क्रियाएँ करें
}
```

## चरण 3: सादा पाठ सामग्री नियंत्रण को संशोधित करें
 प्रकार के सामग्री नियंत्रण के लिए`SdtType.PlainText`, सभी मौजूदा बच्चों को हटाएं, एक नया पैराग्राफ बनाएं और वांछित टेक्स्ट के साथ एक रन जोड़ें।

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## चरण 4: ड्रॉप-डाउन सूची सामग्री नियंत्रण को संशोधित करें
 प्रकार के सामग्री नियंत्रण के लिए`SdtType.DropDownList` , चयनित मान को किसी विशिष्ट पर सेट करके अद्यतन करें`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## चरण 5: चित्र सामग्री नियंत्रण को संशोधित करें
 प्रकार के सामग्री नियंत्रण के लिए`SdtType.Picture`, सामग्री नियंत्रण के भीतर आकृति को पुनः प्राप्त करें और उसकी छवि को एक नई छवि से बदलें।

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## चरण 6: संशोधित दस्तावेज़ सहेजें
 का उपयोग करके संशोधित दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` तरीका। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.ModifyContentControls.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके सामग्री नियंत्रण को संशोधित करने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ में विभिन्न प्रकार के सामग्री नियंत्रणों को सफलतापूर्वक संशोधित किया है।