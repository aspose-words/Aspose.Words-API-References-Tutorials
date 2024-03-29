---
title: हाइफ़नेशन कॉलबैक
linktitle: हाइफ़नेशन कॉलबैक
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: शब्द हाइफ़नेशन को संभालने के लिए .NET के लिए Aspose.Words में हाइफ़नेशन कॉलबैक का उपयोग करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-hyphenation/hyphenation-callback/
---

इस चरण-दर-चरण ट्यूटोरियल में, हम आपको दिखाएंगे कि .NET के लिए Aspose.Words में हाइफ़नेशन कॉलबैक सुविधा का उपयोग कैसे करें। हम दिए गए C# स्रोत कोड की व्याख्या करेंगे और आपको दिखाएंगे कि इसे अपनी परियोजनाओं में कैसे लागू किया जाए।

 आरंभ करने के लिए, सुनिश्चित करें कि आपके पास अपने विकास परिवेश में .NET के लिए Aspose.Words स्थापित और कॉन्फ़िगर है। यदि आपने पहले से नहीं किया है, तो यहां से लाइब्रेरी डाउनलोड और इंस्टॉल करें[Aspose.Releases]https://releases.aspose.com/words/net/।

## चरण 1: हाइफ़नेशन अनुस्मारक सहेजें

 सबसे पहले, हम एक कस्टम का उपयोग करके हाइफ़नेशन कॉलबैक पंजीकृत करेंगे`CustomHyphenationCallback` कक्षा। यह हमें अपने नियमों के अनुसार शब्द हाइफ़नेशन को संभालने की अनुमति देगा:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 सुनिश्चित करें कि आपने इसे लागू कर दिया है`CustomHyphenationCallback` आपकी विशिष्ट आवश्यकताओं के अनुसार कक्षा।

## चरण 2: दस्तावेज़ लोड करना और हाइफ़नेशन लागू करना

इसके बाद, अपने दस्तावेज़ को निर्दिष्ट निर्देशिका से लोड करें और Aspose.Words का उपयोग करके शब्दों को हाइफ़न करें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## चरण 3: लुप्त शब्दकोश त्रुटियों को संभालना

यदि कोई हाइफ़नेशन शब्दकोश गायब है, तो हम संबंधित अपवाद को पकड़ लेंगे और एक त्रुटि संदेश प्रदर्शित करेंगे:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## चरण 4: सफाई और हाइफ़नेशन अनुस्मारक अक्षम करें

अंत में, सफ़ाई के लिए और हाइफ़नेशन अनुस्मारक को बंद करने के लिए, निम्नलिखित चरण निष्पादित करें:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

यह प्रसंस्करण समाप्त करने के बाद हाइफ़नेशन अनुस्मारक को साफ़ और अक्षम कर देता है।

इसलिए ! आपने .NET के लिए Aspose.Words में हाइफ़नेशन कॉलबैक का सफलतापूर्वक उपयोग किया है।

### .NET के लिए Aspose.Words के साथ हाइफ़नेशन कॉलबैक के लिए नमूना स्रोत कोड

```csharp
try
{
	 // हाइफ़नेशन कॉलबैक पंजीकृत करें.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

बेझिझक इस कोड को अपनी परियोजनाओं में उपयोग करें और इसे अपनी विशिष्ट आवश्यकताओं के अनुरूप संशोधित करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: Aspose.Words में सिलेबाइज़ेशन रिमाइंडर क्या है?

उत्तर: Aspose.Words में एक सिलेबाइज़ेशन रिमाइंडर एक ऐसी सुविधा है जो आपको यह अनुकूलित करने की अनुमति देती है कि आपके दस्तावेज़ों में शब्दों को कैसे सिलेबाइज़ किया गया है। सिलेबाइजेशन रिमाइंडर का उपयोग करके, आप शब्दों के सिलेबाइजेशन के लिए कस्टम नियम निर्दिष्ट कर सकते हैं, जो विशिष्ट भाषाओं या विशेष परिदृश्यों के लिए उपयोगी हो सकते हैं जहां डिफ़ॉल्ट सिलेबाइजेशन वांछित परिणाम नहीं देता है।

#### प्रश्न: Aspose.Words में सिलेबाइज़ेशन रिमाइंडर कैसे सेट करें?

 ए: Aspose.Words में एक हाइफ़नेशन कॉलबैक को परिभाषित करने के लिए, आपको एक क्लास बनाने की आवश्यकता है जो इसे लागू करती है`HyphenationCallback` इंटरफ़ेस और कार्यान्वयन करें`HandleWord()` तरीका। इस विधि को शब्दांशीकरण के दौरान सामने आए प्रत्येक शब्द के लिए बुलाया जाएगा। आप इसमें कस्टम सिलेबाइज़ेशन नियम लागू कर सकते हैं और सिलेबाइज़्ड शब्द वापस कर सकते हैं। फिर आप इसका उपयोग करके अपने हाइफ़नेशन कॉलबैक को बाइंड कर सकते हैं`Document.HyphenationCallback` आपके दस्तावेज़ की संपत्ति.

#### प्रश्न: Aspose.Words में सिलेबाइज़ेशन रिमाइंडर का उपयोग करने का क्या फायदा है?

उ: Aspose.Words में सिलेबाइज़ेशन रिमाइंडर का उपयोग करने का लाभ यह अनुकूलित करने की क्षमता है कि आपके दस्तावेज़ों में शब्दों को सिलेबाइज़ कैसे किया जाता है। यह आपको शब्दांशीकरण पर अधिक नियंत्रण देता है, विशेष रूप से विशिष्ट भाषाओं या परिदृश्यों के लिए जहां डिफ़ॉल्ट शब्दांशीकरण वांछित परिणाम नहीं देता है। आप अपनी आवश्यकताओं के अनुसार सटीक शब्दांश प्राप्त करने के लिए प्रत्येक शब्द पर विशिष्ट नियम लागू कर सकते हैं।

#### प्रश्न: कुछ सामान्य परिदृश्य क्या हैं जहां शब्दांश अनुस्मारक का उपयोग सहायक हो सकता है?

उत्तर: सिलेबसाइज़ेशन बूस्टर का उपयोग कई परिदृश्यों में उपयोगी हो सकता है, जैसे:
- विशिष्ट भाषाओं में शब्दों का शब्दांशीकरण जिसमें विशेष शब्दांशीकरण नियम होते हैं।
- परिवर्णी शब्दों या तकनीकी शब्दों के लिए वैयक्तिकृत शब्दांश नियमों का अनुप्रयोग।
- शैलीगत प्राथमिकताओं या मुद्रण मानकों के अनुसार शब्दांश का अनुकूलन।

#### प्रश्न: मैं Aspose.Words में सिलेबाइज़ेशन अनुस्मारक के साथ कस्टम सिलेबाइज़ेशन का परीक्षण कैसे कर सकता हूँ?

 उ: Aspose.Words में एक सिलेबाइज़ेशन अनुस्मारक के साथ कस्टम सिलेबाइज़ेशन का परीक्षण करने के लिए, आप एक परीक्षण दस्तावेज़ बना सकते हैं जिसमें वे शब्द शामिल हैं जिनके लिए आप कस्टम सिलेबाइज़ेशन नियम लागू करना चाहते हैं। फिर आप अपना कस्टम सिलेबाइज़ेशन कॉलबैक सेट कर सकते हैं, कॉल कर सकते हैं`Document.Range.Replace()` दस्तावेज़ में शब्दों को बदलने की विधि, और उपयोग करें`Hyphenate()` की विधि`Hyphenation` शब्दों का शब्दांश प्राप्त करने के लिए कक्षा। फिर आप आवश्यकतानुसार शब्दांश शब्दों को प्रारूपित कर सकते हैं, उदाहरण के लिए अक्षरों के बीच हाइफ़न जोड़कर।