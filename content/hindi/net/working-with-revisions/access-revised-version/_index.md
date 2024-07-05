---
title: संशोधित संस्करण तक पहुंचें
linktitle: संशोधित संस्करण तक पहुंचें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ के संशोधित संस्करण तक पहुँचें।
type: docs
weight: 10
url: /hi/net/working-with-revisions/access-revised-version/
---

इस चरण-दर-चरण मार्गदर्शिका में, हम आपको Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ के संशोधित संस्करण तक पहुँचने का तरीका दिखाने जा रहे हैं। हम आपको पूरा स्रोत कोड प्रदान करेंगे और आपको मार्कडाउन आउटपुट को फ़ॉर्मेट करने का तरीका दिखाएंगे।

## चरण 1: दस्तावेज़ लोड करना

पहला चरण संशोधनों वाले दस्तावेज़ को अपलोड करना है।

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## चरण 2: संशोधित संस्करण तक पहुंचें

अब हम दस्तावेज़ के संशोधित संस्करण पर आगे बढ़ेंगे।

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## चरण 3: संशोधन ब्राउज़ करें

इसके बाद, हम दस्तावेज़ में मौजूद संशोधनों को देखेंगे और सूची आइटम वाले पैराग्राफों के लिए विशिष्ट जानकारी प्रदर्शित करेंगे।

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

### .NET के लिए Aspose.Words का उपयोग करके Access Revised Version के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ के संशोधित संस्करण तक पहुंचने के लिए यहां पूर्ण स्रोत कोड दिया गया है:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// दस्तावेज़ के संशोधित संस्करण पर जाएँ।
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

इस ट्यूटोरियल में, हमने सीखा कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ के संशोधित संस्करण तक कैसे पहुँचा जाए। दस्तावेज़ को लोड करके, संशोधित संस्करण पर नेविगेट करके, और संशोधनों के माध्यम से ब्राउज़ करके, हम उन पैराग्राफ़ों के लिए विशिष्ट जानकारी प्राप्त करने में सक्षम थे जो सूची आइटम हैं। Aspose.Words for .NET Word दस्तावेज़ों में हेरफेर करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है, जिसमें समीक्षाओं तक पहुँच शामिल है। अब आप इस ज्ञान का उपयोग Aspose.Words for .NET का उपयोग करके अपने स्वयं के Word दस्तावेज़ों के संशोधित संस्करण तक पहुँचने के लिए कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं .NET के लिए Aspose.Words में संशोधन के साथ एक दस्तावेज़ कैसे लोड करूं?

 उत्तर: का प्रयोग करें`Document` .NET के लिए Aspose.Words की क्लास का उपयोग संशोधनों वाली फ़ाइल से दस्तावेज़ लोड करने के लिए करें। आप पूर्ण दस्तावेज़ पथ निर्दिष्ट कर सकते हैं।

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### प्रश्न: मैं Aspose.Words for .NET में किसी दस्तावेज़ के संशोधित संस्करण तक कैसे पहुँच सकता हूँ?

 उत्तर: का प्रयोग करें`RevisionsView` की संपत्ति`Document` दस्तावेज़ के संशोधित संस्करण तक पहुँचने के लिए आप ऑब्जेक्ट का मान सेट कर सकते हैं।`RevisionsView`संपत्ति को`RevisionsView.Final` संशोधनों के बिना अंतिम संस्करण दिखाने के लिए।

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### प्रश्न: मैं .NET के लिए Aspose.Words में दस्तावेज़ संशोधन कैसे ब्राउज़ करूँ?

उत्तर: एक का उपयोग करें`foreach` दस्तावेज़ में मौजूद संशोधनों के माध्यम से पुनरावृति करने के लिए लूप। आप इसका उपयोग कर सकते हैं`Revisions` की संपत्ति`Document` दस्तावेज़ के सभी संशोधनों का संग्रह प्राप्त करने के लिए ऑब्जेक्ट का उपयोग करें।

```csharp
foreach (Revision revision in doc.Revisions)
{
     // प्रत्येक संशोधन की प्रक्रिया यहां करें
}
```

#### प्रश्न: Aspose.Words for .NET में कोई पैराग्राफ़ सूची आइटम है या नहीं, इसकी जांच कैसे करें?

 उत्तर: का प्रयोग करें`IsListItem` की संपत्ति`Paragraph` यह जाँचने के लिए कि क्या पैराग्राफ़ एक सूची आइटम है या नहीं।`IsListItem` संपत्ति रिटर्न`true` यदि पैराग्राफ़ एक सूची आइटम है, अन्यथा यह वापस लौटता है`false`.

```csharp
if (paragraph.IsListItem)
{
     // पैराग्राफ़ एक सूची आइटम है
}
else
{
     // यह पैराग्राफ़ सूची आइटम नहीं है
}
```