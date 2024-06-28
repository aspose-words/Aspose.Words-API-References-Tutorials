---
title: चेतावनी स्रोत का प्रयोग करें
linktitle: चेतावनी स्रोत का प्रयोग करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET चरण-दर-चरण मार्गदर्शिका के लिए Aspose.Words के साथ चेतावनी स्रोत का उपयोग करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-markdown/use-warning-source/
---

इस उदाहरण में, हम आपको दिखाने जा रहे हैं कि .NET के लिए Aspose.Words के साथ चेतावनी स्रोत का उपयोग कैसे करें। कॉलबैक फ़ंक्शन का उपयोग करते समय चेतावनी स्रोत चेतावनी की उत्पत्ति को इंगित करता है।

## चरण 1: दस्तावेज़ लोड करना

 हम एक मौजूदा दस्तावेज़ को लोड करेंगे जिसमें इसका उपयोग करते हुए चेतावनियाँ शामिल हैं`Load` की विधि`Document` कक्षा।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## चरण 3: चेतावनी स्रोत का उपयोग करना

 हम दस्तावेज़ को सेट करके चेतावनी स्रोत का उपयोग करेंगे`WarningCallback` के संग्रह के लिए संपत्ति`WarningInfo` वस्तुएं.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## चरण 4: दस्तावेज़ सहेजना

अंत में, हम दस्तावेज़ को वांछित प्रारूप में सहेज सकते हैं।

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

बधाई हो! अब आपने सीख लिया है कि .NET के लिए Aspose.Words के साथ चेतावनी स्रोत का उपयोग कैसे करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या हम "चेतावनी" टैग की उपस्थिति को अनुकूलित कर सकते हैं?

 उ: "चेतावनी" टैग का स्वरूपण उपयोग किए गए मार्कडाउन रेंडरर पर निर्भर करता है। ज्यादातर मामलों में, आप लक्ष्य करने के लिए सीएसएस का उपयोग करके लुक को अनुकूलित कर सकते हैं`blockquote` अपने दस्तावेज़ में टैग करें.

#### प्रश्न: क्या "चेतावनी" टैग में आइकन जोड़ना संभव है?

उ: हां, आपके मार्कडाउन दस्तावेज़ में HTML कोड का उपयोग करके "चेतावनी" टैग में आइकन जोड़ना संभव है। आप एक सम्मिलित कर सकते हैं`span` चेतावनी पाठ के आगे एक आइकन प्रदर्शित करने के लिए उपयुक्त वर्ग के साथ टैग करें।

#### प्रश्न: क्या "चेतावनी" टैग सभी मार्कडाउन पाठकों के साथ संगत है?

 उ: "चेतावनी" टैग की अनुकूलता प्रयुक्त मार्कडाउन रेंडरिंग पर निर्भर करती है। अधिकांश मार्कडाउन पाठक इसका समर्थन करेंगे`blockquote` हाइलाइट किए गए टेक्स्ट को प्रदर्शित करने के लिए टैग, लेकिन सटीक स्वरूप भिन्न हो सकता है।