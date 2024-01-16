---
title: संशोधित संस्करण तक पहुंचें
linktitle: संशोधित संस्करण तक पहुंचें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ के संशोधित संस्करण तक पहुंचें।
type: docs
weight: 10
url: /hi/net/working-with-revisions/access-revised-version/
---

इस चरण-दर-चरण मार्गदर्शिका में, हम आपको यह दिखाने जा रहे हैं कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ के संशोधित संस्करण तक कैसे पहुँचें। हम आपको संपूर्ण स्रोत कोड प्रदान करेंगे और आपको दिखाएंगे कि मार्कडाउन आउटपुट को कैसे प्रारूपित किया जाए।

## चरण 1: दस्तावेज़ लोड करना

पहला कदम संशोधन वाले दस्तावेज़ को अपलोड करना है।

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## चरण 2: संशोधित संस्करण तक पहुंचें

अब हम दस्तावेज़ के संशोधित संस्करण की ओर बढ़ेंगे।

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## चरण 3: संशोधन ब्राउज़ करें

इसके बाद, हम दस्तावेज़ में मौजूद संशोधनों के माध्यम से लूप करेंगे और उन पैराग्राफों के लिए विशिष्ट जानकारी प्रदर्शित करेंगे जो सूची आइटम हैं।

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### .NET के लिए Aspose.Words का उपयोग करके एक्सेस संशोधित संस्करण के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ के संशोधित संस्करण तक पहुंचने के लिए संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// दस्तावेज़ के संशोधित संस्करण पर स्विच करें.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ के संशोधित संस्करण तक कैसे पहुँचें। दस्तावेज़ को लोड करके, संशोधित संस्करण पर नेविगेट करके, और संशोधनों के माध्यम से ब्राउज़ करके, हम उन पैराग्राफों के लिए विशिष्ट जानकारी प्राप्त करने में सक्षम थे जो सूची आइटम हैं। .NET के लिए Aspose.Words समीक्षाओं तक पहुंच सहित Word दस्तावेज़ों में हेरफेर करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है। अब आप इस ज्ञान का उपयोग .NET के लिए Aspose.Words का उपयोग करके अपने स्वयं के Word दस्तावेज़ों के संशोधित संस्करण तक पहुंचने के लिए कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं .NET के लिए Aspose.Words में संशोधन के साथ एक दस्तावेज़ कैसे लोड करूं?

 ए: का प्रयोग करें`Document`संशोधन वाली फ़ाइल से दस्तावेज़ लोड करने के लिए .NET के लिए Aspose.Words का वर्ग। आप संपूर्ण दस्तावेज़ पथ निर्दिष्ट कर सकते हैं.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### प्रश्न: मैं .NET के लिए Aspose.Words में किसी दस्तावेज़ के संशोधित संस्करण तक कैसे पहुँच सकता हूँ?

 ए: का प्रयोग करें`RevisionsView` की संपत्ति`Document` दस्तावेज़ के संशोधित संस्करण तक पहुँचने के लिए आपत्ति। आप का मान निर्धारित कर सकते हैं`RevisionsView`संपत्ति को`RevisionsView.Final` संशोधनों के बिना अंतिम संस्करण दिखाने के लिए।

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### प्रश्न: मैं .NET के लिए Aspose.Words में दस्तावेज़ संशोधन कैसे ब्राउज़ करूं?

 ए: ए का प्रयोग करें`foreach` दस्तावेज़ में मौजूद संशोधनों के माध्यम से पुनरावृत्त करने के लिए लूप। आप इसका उपयोग कर सकते हैं`Revisions` की संपत्ति`Document` दस्तावेज़ के सभी संशोधनों का संग्रह प्राप्त करने के लिए ऑब्जेक्ट।

```csharp
foreach (Revision revision in doc.Revisions)
{
     // प्रत्येक संशोधन को यहां संसाधित करें
}
```

#### प्रश्न: यह कैसे जांचें कि कोई पैराग्राफ .NET के लिए Aspose.Words में एक सूची आइटम है?

 ए: का प्रयोग करें`IsListItem` की संपत्ति`Paragraph` यह जाँचने के लिए ऑब्जेक्ट करें कि कोई अनुच्छेद एक सूची आइटम है या नहीं।`IsListItem` संपत्ति रिटर्न`true` यदि पैराग्राफ एक सूची आइटम है, अन्यथा यह वापस आ जाता है`false`.

```csharp
if (paragraph.IsListItem)
{
     // अनुच्छेद एक सूची आइटम है
}
else
{
     // अनुच्छेद कोई सूची आइटम नहीं है
}
```