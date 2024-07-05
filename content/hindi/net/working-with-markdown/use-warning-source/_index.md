---
title: चेतावनी स्रोत का उपयोग करें
linktitle: चेतावनी स्रोत का उपयोग करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ चेतावनी स्रोत का उपयोग करना सीखें चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/working-with-markdown/use-warning-source/
---

इस उदाहरण में, हम आपको .NET के लिए Aspose.Words के साथ चेतावनी स्रोत का उपयोग करने का तरीका दिखाने जा रहे हैं। चेतावनी स्रोत कॉलबैक फ़ंक्शन का उपयोग करते समय चेतावनी की उत्पत्ति को इंगित करता है।

## चरण 1: दस्तावेज़ लोड करना

 हम एक मौजूदा दस्तावेज़ लोड करेंगे जिसमें चेतावनियाँ शामिल हैं`Load` की विधि`Document` कक्षा।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## चरण 3: चेतावनी स्रोत का उपयोग करना

 हम दस्तावेज़ की सेटिंग करके चेतावनी स्रोत का उपयोग करेंगे`WarningCallback` संपत्ति का संग्रह`WarningInfo` वस्तुएं.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## चरण 4: दस्तावेज़ को सहेजना

अंततः, हम दस्तावेज़ को वांछित प्रारूप में सहेज सकते हैं।

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### .NET के लिए Aspose.Words के साथ चेतावनी स्रोत का उपयोग करने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

बधाई हो! अब आप सीख चुके हैं कि .NET के लिए Aspose.Words के साथ चेतावनी स्रोत का उपयोग कैसे करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या हम "चेतावनी" टैग के स्वरूप को अनुकूलित कर सकते हैं?

 उत्तर: "चेतावनी" टैग का स्वरूपण उपयोग किए गए मार्कडाउन रेंडरर पर निर्भर करता है। ज़्यादातर मामलों में, आप सीएसएस का उपयोग करके लुक को कस्टमाइज़ कर सकते हैं ताकि लक्ष्य को लक्षित किया जा सके`blockquote` अपने दस्तावेज़ में टैग जोड़ें.

#### प्रश्न: क्या "चेतावनी" टैग में आइकन जोड़ना संभव है?

उत्तर: हां, आपके मार्कडाउन दस्तावेज़ में HTML कोड का उपयोग करके "चेतावनी" टैग में आइकन जोड़ना संभव है। आप एक सम्मिलित कर सकते हैं`span` चेतावनी पाठ के बगल में एक आइकन प्रदर्शित करने के लिए उपयुक्त वर्ग के साथ टैग करें।

#### प्रश्न: क्या "चेतावनी" टैग सभी मार्कडाउन रीडर्स के साथ संगत है?

 उत्तर: "चेतावनी" टैग की अनुकूलता उपयोग किए गए मार्कडाउन रेंडरिंग पर निर्भर करती है। अधिकांश मार्कडाउन रीडर इसका समर्थन करेंगे`blockquote` टैग का उपयोग हाइलाइट किए गए टेक्स्ट को प्रदर्शित करने के लिए किया जाता है, लेकिन वास्तविक स्वरूप भिन्न हो सकता है।