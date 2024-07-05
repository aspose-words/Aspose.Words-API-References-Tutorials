---
title: सामग्री नियंत्रण संशोधित करें
linktitle: सामग्री नियंत्रण संशोधित करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में सामग्री नियंत्रण के भीतर पाठ, ड्रॉपडाउन सूचियों और छवियों को संशोधित करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/modify-content-controls/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में विभिन्न प्रकार के कंटेंट कंट्रोल को कैसे संशोधित किया जाए। आप टेक्स्ट को अपडेट कर सकते हैं, ड्रॉपडाउन सूची का चयनित मान, या कंटेंट कंट्रोल के भीतर एक छवि को बदल सकते हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए आपके पास निम्नलिखित चीजें होनी चाहिए:

- Aspose.Words for .NET लाइब्रेरी स्थापित की गई।
- C# और वर्ड दस्तावेजों के साथ वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपने दस्तावेज़ निर्देशिका का पथ सेट करके आरंभ करें।`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहां आपका दस्तावेज़ स्थित है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ लोड करें और सामग्री नियंत्रणों पर पुनरावृति करें
 Word दस्तावेज़ को लोड करने के लिए निम्न का उपयोग करें:`Document`कंस्ट्रक्टर, दस्तावेज़ के पथ को पैरामीटर के रूप में पास करता है। दस्तावेज़ में सभी संरचित दस्तावेज़ टैग पर पुनरावृत्ति करें`foreach` कुंडली।

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // सामग्री नियंत्रण के प्रकार के आधार पर कार्यवाहियाँ निष्पादित करें
}
```

## चरण 3: सादा पाठ सामग्री नियंत्रण संशोधित करें
 प्रकार के सामग्री नियंत्रणों के लिए`SdtType.PlainText`, सभी मौजूदा बच्चों को हटा दें, एक नया पैराग्राफ बनाएं, और वांछित पाठ के साथ एक रन जोड़ें।

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

## चरण 4: ड्रॉप-डाउन सूची सामग्री नियंत्रण संशोधित करें
 प्रकार के सामग्री नियंत्रणों के लिए`SdtType.DropDownList` , चयनित मान को एक विशिष्ट मान पर सेट करके अपडेट करें`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## चरण 5: चित्र सामग्री नियंत्रण संशोधित करें
 प्रकार के सामग्री नियंत्रणों के लिए`SdtType.Picture`, सामग्री नियंत्रण के भीतर आकृति को पुनः प्राप्त करें और इसकी छवि को एक नई छवि से बदलें।

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
 संशोधित दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.ModifyContentControls.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके सामग्री नियंत्रण संशोधित करने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
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

बस! आपने Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ में विभिन्न प्रकार के सामग्री नियंत्रणों को सफलतापूर्वक संशोधित कर लिया है।