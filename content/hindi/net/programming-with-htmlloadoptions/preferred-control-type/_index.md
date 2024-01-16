---
title: वर्ड दस्तावेज़ में पसंदीदा नियंत्रण प्रकार
linktitle: वर्ड दस्तावेज़ में पसंदीदा नियंत्रण प्रकार
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ HTML दस्तावेज़ लोड करते समय वर्ड दस्तावेज़ में पसंदीदा नियंत्रण प्रकार निर्दिष्ट करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-htmlloadoptions/preferred-control-type/
---
यह आलेख .NET के लिए Aspose.Words के साथ पसंदीदा नियंत्रण प्रकार सुविधा का उपयोग करने के तरीके पर चरण-दर-चरण मार्गदर्शिका प्रदान करता है। हम कोड के प्रत्येक भाग को विस्तार से समझाएंगे। इस ट्यूटोरियल के अंत में, आप यह समझ पाएंगे कि HTML दस्तावेज़ लोड करते समय पसंदीदा नियंत्रण प्रकार कैसे निर्दिष्ट किया जाए।

शुरू करने से पहले, सुनिश्चित करें कि आपने अपने प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words को स्थापित और कॉन्फ़िगर किया है। आप Aspose वेबसाइट पर लाइब्रेरी और इंस्टॉलेशन निर्देश पा सकते हैं।

## चरण 1: HTML कोड को परिभाषित करें

 आरंभ करने के लिए, आपको उस HTML कोड को परिभाषित करना होगा जिसे आप दस्तावेज़ के रूप में लोड करना चाहते हैं। इस उदाहरण में, हमने एक को परिभाषित किया है`html` वेरिएबल जिसमें विकल्पों के साथ चयनकर्ता का HTML कोड होता है।

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## चरण 2: HTML लोडिंग विकल्प सेट करें

 अगला, हम एक बनाते हैं`HtmlLoadOptions` ऑब्जेक्ट करें और सेट करें`PreferredControlType`संपत्ति को`HtmlControlType.StructuredDocumentTag`. यह Aspose.Words को लोड करते समय HTML का प्रतिनिधित्व करने के लिए StructuredDocumentTags का उपयोग करने के लिए कहता है।

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## चरण 3: दस्तावेज़ को लोड करें और सहेजें

 हम उपयोग करते हैं`Document` पहले परिभाषित लोड विकल्पों के साथ मेमोरी स्ट्रीम से HTML कोड लोड करने के लिए क्लास। फिर हम दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजते हैं`.docx`फ़ाइल फ़ारमैट।

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### .NET के लिए Aspose.Words के साथ पसंदीदा नियंत्रण प्रकार के लिए उदाहरण स्रोत कोड

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

बस इतना ही ! .NET के लिए Aspose.Words के साथ HTML दस्तावेज़ लोड करते समय आपने सफलतापूर्वक पसंदीदा नियंत्रण प्रकार निर्दिष्ट किया है।

## निष्कर्ष

 इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आपने HTML दस्तावेज़ लोड करते समय वांछित नियंत्रण प्रकार निर्दिष्ट करने के लिए .NET के लिए Aspose.Words में "पसंदीदा नियंत्रण प्रकार" सुविधा का उपयोग करना सीख लिया है। की स्थापना`PreferredControlType`संपत्ति को`HtmlControlType.StructuredDocumentTag` HTML सामग्री के बेहतर प्रतिनिधित्व और प्रसंस्करण के लिए Aspose.Words को StructuredDocumentTags (SDT) का उपयोग करने की अनुमति देता है। आप अपनी विशिष्ट आवश्यकताओं के अनुरूप अन्य नियंत्रण प्रकारों का भी पता लगा सकते हैं। इस सुविधा का उपयोग करने से Aspose.Words के साथ आपके C# एप्लिकेशन में HTML दस्तावेज़ों की सटीक और कुशल हैंडलिंग सुनिश्चित करने में मदद मिलती है।

### वर्ड दस्तावेज़ में पसंदीदा नियंत्रण प्रकार के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में "पसंदीदा नियंत्रण प्रकार" सुविधा क्या है?

उ: "पसंदीदा नियंत्रण प्रकार" सुविधा आपको HTML दस्तावेज़ लोड करते समय HTML तत्वों का प्रतिनिधित्व करने के लिए पसंदीदा प्रकार के नियंत्रण को निर्दिष्ट करने की अनुमति देती है। यह HTML सामग्री के बेहतर प्रतिनिधित्व और प्रसंस्करण के लिए उपयुक्त नियंत्रण प्रकार का चयन करने में मदद करता है।

#### प्रश्न: HTML दस्तावेज़ लोड करते समय मैं पसंदीदा नियंत्रण प्रकार कैसे सेट करूँ?

 उ: पसंदीदा नियंत्रण प्रकार सेट करने के लिए, आपको एक बनाना होगा`HtmlLoadOptions` ऑब्जेक्ट करें और उसे सेट करें`PreferredControlType` वांछित को संपत्ति`HtmlControlType` . दिए गए उदाहरण में,`HtmlControlType.StructuredDocumentTag` प्रयोग किया जाता है।

#### प्रश्न: पसंदीदा नियंत्रण प्रकार के रूप में स्ट्रक्चर्ड डॉक्यूमेंट टैग (एसडीटी) का उपयोग करने का क्या महत्व है?

ए: स्ट्रक्चर्ड डॉक्यूमेंट टैग (एसडीटी) एक्सएमएल-आधारित तत्व हैं जिनका उपयोग वर्ड दस्तावेज़ में जटिल सामग्री और नियंत्रण का प्रतिनिधित्व करने के लिए किया जा सकता है। पसंदीदा नियंत्रण प्रकार के रूप में एसडीटी का उपयोग HTML सामग्री की बेहतर अनुकूलता और प्रतिनिधित्व प्रदान कर सकता है।

#### प्रश्न: मैं यह कैसे सुनिश्चित कर सकता हूं कि HTML दस्तावेज़ लोड करते समय Aspose.Words पसंदीदा नियंत्रण प्रकार का उपयोग करता है?

 उत्तर: सेटिंग करके`PreferredControlType`संपत्ति को`HtmlControlType.StructuredDocumentTag`जैसा कि उदाहरण स्रोत कोड में दिखाया गया है, दस्तावेज़ लोड करते समय Aspose.Words HTML तत्वों का प्रतिनिधित्व करने के लिए SDT का उपयोग करेगा।

#### प्रश्न: क्या मैं पसंदीदा विकल्प के रूप में अन्य नियंत्रण प्रकारों का उपयोग कर सकता हूँ?

 उत्तर: हां, इसके अलावा`HtmlControlType.StructuredDocumentTag` , .NET के लिए Aspose.Words जैसे अन्य नियंत्रण प्रकारों का समर्थन करता है`HtmlControlType.ContentControl` और`HtmlControlType.CustomXmlMarkup`.