---
title: जोर
linktitle: जोर
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET चरण-दर-चरण मार्गदर्शिका के लिए Aspose.Words के साथ एम्फेज़ (बोल्ड और इटैलिक) का उपयोग करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-markdown/emphases/
---

इस उदाहरण में, हम बताएंगे कि .NET के लिए Aspose.Words के साथ एम्फेज़ का उपयोग कैसे करें। एम्फेज़ का उपयोग पाठ के कुछ हिस्सों पर जोर देने के लिए किया जाता है, जैसे कि बोल्ड और इटैलिक।

## चरण 1: दस्तावेज़ आरंभीकरण

 सबसे पहले, हम इसका एक उदाहरण बनाकर दस्तावेज़ को आरंभ करेंगे`Document` कक्षा।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## चरण 2: दस्तावेज़ जनरेटर का उपयोग करना

इसके बाद, हम अपने दस्तावेज़ में सामग्री जोड़ने के लिए दस्तावेज़ जनरेटर का उपयोग करेंगे।

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: जोर देकर पाठ जोड़ें

हम दस्तावेज़ जनरेटर के फ़ॉन्ट गुणों को बदलकर एम्फेज़ टेक्स्ट जोड़ सकते हैं। इस उदाहरण में, हम पाठ के विभिन्न भागों पर ज़ोर देने के लिए बोल्ड और इटैलिक का उपयोग करते हैं।

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## चरण 4: दस्तावेज़ सहेजना

 अंत में, हम दस्तावेज़ को वांछित प्रारूप में सहेज सकते हैं। इस उदाहरण में, हम इसका उपयोग कर रहे हैं`.md` मार्कडाउन प्रारूप के लिए एक्सटेंशन।

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

बधाई हो! अब आपने सीख लिया है कि .NET के लिए Aspose.Words के साथ एम्फेज़ का उपयोग कैसे करें।

### .NET के लिए Aspose.Words का उपयोग करते हुए एम्फेसिस के लिए उदाहरण स्रोत कोड


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं मार्कडाउन का उपयोग करके टेक्स्ट को कैसे हाइलाइट करूं?

 उ: मार्कडाउन का उपयोग करके टेक्स्ट को हाइलाइट करने के लिए, बस टेक्स्ट को उपयुक्त प्रतीकों से घेर लें। उपयोग`*` या`_` इटैलिक के लिए,`**` या`__` बोल्ड के लिए, और`~~` स्ट्राइकथ्रू के लिए.

#### प्रश्न: क्या हम एक ही पाठ में विभिन्न हाइलाइट्स को जोड़ सकते हैं?

 उत्तर: हाँ, एक ही पाठ में विभिन्न हाइलाइट्स को संयोजित करना संभव है। उदाहरण के लिए, आप दोनों का उपयोग करके किसी शब्द को बोल्ड और इटैलिकाइज़ कर सकते हैं`**` और`*`शब्द के चारों ओर.

#### प्रश्न: मार्कडाउन में कौन से हाइलाइटिंग विकल्प उपलब्ध हैं?

उ: मार्कडाउन में उपलब्ध हाइलाइटिंग विकल्प इटैलिक हैं (`*` या`_`), बोल्ड (`**` या`__`), और स्ट्राइकथ्रू (`~~`).

#### प्रश्न: मैं उन मामलों को कैसे संभाल सकता हूं जहां पाठ में हाइलाइटिंग के लिए मार्कडाउन द्वारा उपयोग किए गए विशेष वर्ण शामिल हैं?

 उ: यदि आपके पाठ में हाइलाइटिंग के लिए मार्कडाउन द्वारा उपयोग किए गए विशेष वर्ण हैं, तो आप उनके पहले ए लगाकर उनसे बच सकते हैं`\` . उदाहरण के लिए,`\*` एक शाब्दिक तारांकन प्रदर्शित करेगा.

#### प्रश्न: क्या हम सीएसएस का उपयोग करके हाइलाइटिंग के स्वरूप को अनुकूलित कर सकते हैं?

उ: मार्कडाउन में हाइलाइटिंग आमतौर पर ब्राउज़र की डिफ़ॉल्ट शैलियों का उपयोग करके प्रस्तुत की जाती है। यदि आप अपने मार्कडाउन को HTML में परिवर्तित करते हैं, तो आप CSS नियमों का उपयोग करके हाइलाइटिंग की उपस्थिति को अनुकूलित कर सकते हैं।