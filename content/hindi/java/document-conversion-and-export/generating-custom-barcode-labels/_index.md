---
title: Java के लिए Aspose.Words में कस्टम बारकोड लेबल बनाना
linktitle: कस्टम बारकोड लेबल बनाना
second_title: Aspose.Words जावा दस्तावेज़ प्रसंस्करण एपीआई
description: Aspose.Words for Java में कस्टम बारकोड लेबल जेनरेट करें। इस चरण-दर-चरण मार्गदर्शिका में Aspose.Words for Java का उपयोग करके वैयक्तिकृत बारकोड समाधान बनाना सीखें।
type: docs
weight: 10
url: /hi/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## जावा के लिए Aspose.Words में कस्टम बारकोड लेबल बनाने का परिचय

इस व्यापक गाइड में, हम Aspose.Words for Java का उपयोग करके कस्टम बारकोड लेबल बनाने की प्रक्रिया में गहराई से जाएंगे। Aspose.Words for Java एक शक्तिशाली API है जो डेवलपर्स को Word दस्तावेज़ों को प्रोग्रामेटिक रूप से हेरफेर करने की अनुमति देता है। इसकी उल्लेखनीय विशेषताओं में से एक बारकोड लेबल के साथ काम करने की क्षमता है, जो इसे उन व्यवसायों और संगठनों के लिए एक मूल्यवान उपकरण बनाती है जिन्हें अनुकूलित बारकोड समाधान की आवश्यकता होती है।

## आवश्यक शर्तें

इससे पहले कि हम कस्टम बारकोड लेबल बनाने के विवरण में उतरें, आइए सुनिश्चित करें कि हमारे पास आवश्यक शर्तें मौजूद हैं:

1. जावा विकास पर्यावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा और एकीकृत विकास पर्यावरण (आईडीई) स्थापित है।

2.  Aspose.Words for Java: Aspose.Words for Java को यहां से डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/words/java/).

3. जावा का बुनियादी ज्ञान: जावा प्रोग्रामिंग से परिचित होना उपयोगी होगा क्योंकि हम कस्टम बारकोड लेबल बनाने के लिए जावा कोड लिखेंगे।

## कस्टम बारकोड लेबल बनाना

अब, आइए Java के लिए Aspose.Words का उपयोग करके कस्टम बारकोड लेबल बनाना शुरू करें। हम इस प्रक्रिया को चरणों में विभाजित करेंगे और प्रत्येक चरण के लिए Java कोड स्निपेट प्रदान करेंगे।

## बारकोड की ऊंचाई निर्धारित करना

शुरू करने के लिए, हमें अपने बारकोड की ऊंचाई ट्विप्स (1/1440 इंच) में सेट करनी होगी। फिर हम इस मान को मिलीमीटर (मिमी) में बदल देंगे। इसे पूरा करने के लिए कोड यहाँ दिया गया है:

```java
	// इनपुट मान 1/1440 इंच (ट्विप्स) में है
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// मिमी में परिवर्तित करें
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## बारकोड छवि का रंग बदलना

इसके बाद, हम बारकोड छवि के रंग को Word से Aspose.BarCode में बदलेंगे। इनपुट रंग "0xRRGGBB" (हेक्साडेसिमल) प्रारूप में होना चाहिए। रूपांतरण के लिए कोड यहाँ दिया गया है:

```java
/// <सारांश>
/// Word से Aspose.BarCode में बारकोड छवि का रंग परिवर्तित करता है।
/// </सारांश>
/// <पैरामीटर नाम="इनपुटरंग"></पैरामीटर>
/// <रिटर्न></रिटर्न>
private static Color convertColor(String inputColor) throws Exception {
	// इनपुट "0x000000" से "0xFFFFFF" तक होना चाहिए
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## बारकोड स्केलिंग फैक्टर परिवर्तित करना

अब, हम बारकोड स्केलिंग फैक्टर को प्रतिशत से फ़्लोट वैल्यू में बदलेंगे। यह स्केलिंग फैक्टर बारकोड का आकार निर्धारित करता है। रूपांतरण के लिए कोड यहाँ दिया गया है:

```java
/// <सारांश>
/// बार कोड स्केलिंग कारक को प्रतिशत से फ्लोट में परिवर्तित करता है।
/// </सारांश>
/// <param name="स्केलिंगफ़ैक्टर"></param>
/// <रिटर्न></रिटर्न>
private static float convertScalingFactor(String scalingFactor) throws Exception {
	boolean isParsed = false;
	int percent = tryParseInt(scalingFactor);
	if (percent != Integer.MIN_VALUE && percent >= 10 && percent <= 10000)
		isParsed = true;
	if (!isParsed)
		throw new Exception("Error! Incorrect scaling factor - " + scalingFactor + ".");
	return percent / 100.0f;
}
```

## GetBarCodeImage() विधि का कार्यान्वयन

 इस चरण में, हम निम्नलिखित को क्रियान्वित करेंगे`getBarcodeImage`विधि, जो दिए गए मापदंडों के आधार पर बारकोड छवि उत्पन्न करती है। हम विभिन्न बारकोड प्रकारों को संभालेंगे, रंग सेट करेंगे, आयाम समायोजित करेंगे, और बहुत कुछ करेंगे। यहाँ इस विधि का कोड है:

```java
/// <सारांश>
/// IBarCodeGenerator इंटरफ़ेस के लिए GetBarCodeImage() विधि का कार्यान्वयन।
/// </सारांश>
/// <पैरामीटर नाम="पैरामीटर"></पैरामीटर>
/// <रिटर्न></रिटर्न>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// जाँचें कि क्या बारकोड प्रकार और मान प्रदान किए गए हैं
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// बारकोड प्रकार के आधार पर बारकोड जेनरेटर बनाएं
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		// अन्य बारकोड प्रकारों को यहां संभालें
	}
	
	// बारकोड टेक्स्ट सेट करें
	generator.setCodeText(parameters.getBarcodeValue());
	
	// बारकोड रंग सेट करें
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	// प्रतीक की ऊंचाई और आयाम सेट करें
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	// कोड टेक्स्ट स्थान अनुकूलित करें
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// क्यूआर कोड के लिए अतिरिक्त समायोजन
	final float SCALE = 2.4f; // Word बारकोड को Aspose.BarCode में परिवर्तित करने के लिए अनुभवजन्य स्केलिंग कारक
	float xdim = 1.0f;
	if (generator.getBarcodeType().equals(EncodeTypes.QR))
	{
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NEAREST);
		generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageWidth().getInches() * SCALE);
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageWidth().getInches());
		xdim = generator.getParameters().getImageHeight().getInches() / 25;
		generator.getParameters().getBarcode().getXDimension().setInches(xdim);
		generator.getParameters().getBarcode().getBarHeight().setInches(xdim);
	}
	
	// स्केलिंग फ़ैक्टर लागू करें
	if (parameters.getScalingFactor() != null)
	{
		float scalingFactor = convertScalingFactor(parameters.getScalingFactor());
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageHeight().getInches() * scalingFactor);
		if (generator.getBarcodeType().equals(EncodeTypes.QR))
		{
			generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageHeight().getInches());
			generator.getParameters().getBarcode().getXDimension().setInches(xdim * scalingFactor);
			generator.getParameters().getBarcode().getBarHeight().setInches(xdim * scalingFactor);
		}
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	// बारकोड छवि उत्पन्न करें और वापस करें
	return generator.generateBarCodeImage();
}
```

## GetOldBarcodeImage() विधि का कार्यान्वयन

 इस चरण में, हम निम्नलिखित को क्रियान्वित करेंगे`getOldBarcodeImage`विधि, जो पुराने जमाने के बारकोड के लिए बारकोड छवियाँ उत्पन्न करती है। यहाँ, हम एक विशिष्ट बारकोड प्रकार, जैसे कि POSTNET को संभालेंगे। इस विधि के लिए कोड यहाँ दिया गया है:

```java
/// <सारांश>
/// IBarCodeGenerator इंटरफ़ेस के लिए GetOldBarcodeImage() विधि का कार्यान्वयन।
/// </सारांश>
/// <पैरामीटर नाम="पैरामीटर"></पैरामीटर>
/// <रिटर्न></रिटर्न>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// पुराने जमाने के बारकोड के लिए हार्डकोड प्रकार
	return generator.generateBarCodeImage();
}
```

## निष्कर्ष

इस लेख में, हमने जावा के लिए Aspose.Words का उपयोग करके कस्टम बारकोड लेबल बनाने की प्रक्रिया का पता लगाया है। हमने बारकोड की ऊँचाई निर्धारित करने से लेकर बारकोड बनाने के तरीकों को लागू करने तक के आवश्यक चरणों को कवर किया है। जावा के लिए Aspose.Words डेवलपर्स को गतिशील और अनुकूलित बारकोड लेबल बनाने में सक्षम बनाता है, जिससे यह विभिन्न उद्योगों के लिए एक मूल्यवान उपकरण बन जाता है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं उत्पन्न बारकोड का आकार कैसे समायोजित कर सकता हूं?

आप दिए गए कोड स्निपेट में बारकोड के सिंबल की ऊंचाई और स्केलिंग फैक्टर सेट करके जेनरेट किए गए बारकोड के आकार को समायोजित कर सकते हैं। ये पैरामीटर आपको अपनी आवश्यकताओं के अनुसार बारकोड के आयामों को नियंत्रित करने की अनुमति देते हैं।

### क्या मैं बारकोड का रंग बदल सकता हूँ?

हां, आप कोड में अग्रभूमि और पृष्ठभूमि रंग निर्दिष्ट करके बारकोड के रंग बदल सकते हैं। यह अनुकूलन आपको बारकोड की उपस्थिति को आपके दस्तावेज़ के डिज़ाइन से मेल खाने की अनुमति देता है।

### Java के लिए Aspose.Words द्वारा कौन से बारकोड प्रकार समर्थित हैं?

Aspose.Words for Java कई तरह के बारकोड को सपोर्ट करता है, जिसमें QR कोड, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 और बहुत कुछ शामिल है। आप अपने एप्लिकेशन की ज़रूरतों के हिसाब से बारकोड का प्रकार चुन सकते हैं।

### मैं उत्पन्न बारकोड को अपने वर्ड दस्तावेज़ में कैसे एकीकृत करूं?

अपने वर्ड डॉक्यूमेंट में जेनरेट किए गए बारकोड को एकीकृत करने के लिए, आप जावा की डॉक्यूमेंट मैनिपुलेशन क्षमताओं के लिए Aspose.Words का उपयोग कर सकते हैं। आप अपने डॉक्यूमेंट में वांछित स्थान पर बारकोड छवि डाल सकते हैं।

### क्या आगे अनुकूलन के लिए कोई नमूना कोड उपलब्ध है?

 हां, आप Aspose.Words for Java की संदर्भ साइट पर नमूना कोड स्निपेट और अतिरिक्त दस्तावेज़ पा सकते हैं:[Aspose.Words for Java API संदर्भ](https://reference.aspose.com/words/java/).