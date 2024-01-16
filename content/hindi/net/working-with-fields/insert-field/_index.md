---
title: फ़ील्ड सम्मिलित करें
linktitle: फ़ील्ड सम्मिलित करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ अपने Word दस्तावेज़ों में फ़ील्ड सम्मिलित करना सीखें। गतिशील फ़ील्ड के साथ अपने दस्तावेज़ों को वैयक्तिकृत करें।
type: docs
weight: 10
url: /hi/net/working-with-fields/insert-field/
---

नीचे C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है, जो .NET के लिए Aspose.Words की "इन्सर्ट अ फ़ील्ड" सुविधा का उपयोग करती है। वांछित परिणाम प्राप्त करने के लिए प्रत्येक चरण का सावधानीपूर्वक पालन करना सुनिश्चित करें।

## चरण 1: दस्तावेज़ निर्देशिका सेटअप

दिए गए कोड में, आपको अपने दस्तावेज़ों की निर्देशिका निर्दिष्ट करनी होगी। अपने दस्तावेज़ निर्देशिका के लिए उचित पथ के साथ "आपकी दस्तावेज़ निर्देशिका" मान को बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ और दस्तावेज़बिल्डर बनाना

हम एक नया दस्तावेज़ बनाकर और एक DocumentBuilder प्रारंभ करके शुरुआत करते हैं।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: फ़ील्ड सम्मिलित करना

 हम उपयोग करते हैं`InsertField()` दस्तावेज़ में फ़ील्ड सम्मिलित करने के लिए DocumentBuilder की विधि। इस उदाहरण में, हम फ़ील्ड नाम "MyFieldName" और मर्ज प्रारूप के साथ एक मर्ज फ़ील्ड (MERGEFIELD) सम्मिलित करते हैं।

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### .NET के लिए Aspose.Words के साथ फ़ील्ड सम्मिलित करने के लिए स्रोत कोड का उदाहरण

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ और DocumentBuilder बनाएँ।
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// फ़ील्ड सम्मिलित करें.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

इस उदाहरण में, हमने एक नया दस्तावेज़ बनाया, एक DocumentBuilder आरंभ किया, और फिर फ़ील्ड नाम "MyFieldName" और मर्ज प्रारूप के साथ एक मर्ज फ़ील्ड डाला। फिर दस्तावेज़ को एक निर्दिष्ट फ़ाइल नाम के साथ सहेजा जाता है।

यह .NET के लिए Aspose.Words के साथ "इन्सर्ट ए फील्ड" सुविधा का उपयोग करने पर हमारी मार्गदर्शिका का समापन करता है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: वर्ड में फ़ील्ड क्या है?

ए: वर्ड में एक फ़ील्ड एक तत्व है जो आपको दस्तावेज़ में गतिशील डेटा डालने और हेरफेर करने की अनुमति देता है। इसका उपयोग परिवर्तनीय जानकारी जैसे तिथियां, पृष्ठ संख्या, तालिकाएं, गणितीय सूत्र इत्यादि प्रदर्शित करने के लिए किया जा सकता है।

#### प्रश्न: वर्ड डॉक्यूमेंट में फ़ील्ड कैसे डालें?

उ: किसी Word दस्तावेज़ में फ़ील्ड सम्मिलित करने के लिए, आप इन चरणों का पालन कर सकते हैं:

1. अपना कर्सर वहां रखें जहां आप फ़ील्ड सम्मिलित करना चाहते हैं।
2. रिबन में "इन्सर्ट" टैब पर जाएँ।
3. फ़ील्ड संवाद बॉक्स खोलने के लिए "टेक्स्ट" समूह में "फ़ील्ड" बटन पर क्लिक करें।
4. ड्रॉप-डाउन सूची से उस फ़ील्ड का प्रकार चुनें जिसे आप सम्मिलित करना चाहते हैं।
5. आवश्यकतानुसार फ़ील्ड विकल्प कॉन्फ़िगर करें.
6. फ़ील्ड को अपने दस्तावेज़ में सम्मिलित करने के लिए "ओके" बटन पर क्लिक करें।

#### प्रश्न: वर्ड में आमतौर पर उपयोग किए जाने वाले फ़ील्ड प्रकार क्या हैं?

उ: Word विभिन्न प्रकार के फ़ील्ड प्रकार प्रदान करता है जिनका उपयोग आप अपने दस्तावेज़ों में कर सकते हैं। यहां आमतौर पर उपयोग किए जाने वाले कुछ फ़ील्ड प्रकार दिए गए हैं:

- दिनांक और समय: वर्तमान दिनांक और समय प्रदर्शित करता है।
- पृष्ठ क्रमांक: वर्तमान पृष्ठ क्रमांक प्रदर्शित करता है.
- विषय-सूची: स्वचालित रूप से आपके शीर्षकों की शैलियों के आधार पर विषय-सूची तैयार करता है।
- गणना: सूत्रों का उपयोग करके गणितीय गणना करता है।
- फिलर टेक्स्ट: आपके दस्तावेज़ को भरने के लिए यादृच्छिक टेक्स्ट उत्पन्न करता है।

#### प्रश्न: क्या मैं वर्ड में फ़ील्ड्स के स्वरूप को अनुकूलित कर सकता हूँ?

उ: हाँ, आप उपलब्ध फ़ॉर्मेटिंग विकल्पों का उपयोग करके Word में फ़ील्ड्स के स्वरूप को अनुकूलित कर सकते हैं। उदाहरण के लिए, आप किसी फ़ील्ड में टेक्स्ट का फ़ॉन्ट, आकार, रंग और शैली बदल सकते हैं। आप बोल्ड, इटैलिक और अंडरलाइन जैसे फ़ॉर्मेटिंग प्रभाव भी लागू कर सकते हैं।
  