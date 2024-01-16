---
title: जावा के लिए Aspose.Words में कस्टम बारकोड लेबल बनाना
linktitle: कस्टम बारकोड लेबल बनाना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words में कस्टम बारकोड लेबल जेनरेट करें। इस चरण-दर-चरण मार्गदर्शिका में जानें कि जावा के लिए Aspose.Words का उपयोग करके वैयक्तिकृत बारकोड समाधान कैसे बनाएं।
type: docs
weight: 10
url: /hi/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## जावा के लिए Aspose.Words में कस्टम बारकोड लेबल बनाने का परिचय

इस व्यापक गाइड में, हम जावा के लिए Aspose.Words का उपयोग करके कस्टम बारकोड लेबल बनाने की प्रक्रिया के बारे में विस्तार से जानेंगे। जावा के लिए Aspose.Words एक शक्तिशाली API है जो डेवलपर्स को Word दस्तावेज़ों को प्रोग्रामेटिक रूप से हेरफेर करने की अनुमति देता है। इसकी उल्लेखनीय विशेषताओं में से एक बारकोड लेबल के साथ काम करने की क्षमता है, जो इसे उन व्यवसायों और संगठनों के लिए एक मूल्यवान उपकरण बनाती है जिन्हें अनुकूलित बारकोड समाधान की आवश्यकता होती है।

## आवश्यक शर्तें

इससे पहले कि हम कस्टम बारकोड लेबल बनाने के विवरण में उतरें, आइए सुनिश्चित करें कि हमारे पास आवश्यक शर्तें मौजूद हैं:

1. जावा विकास पर्यावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा और एक एकीकृत विकास पर्यावरण (आईडीई) स्थापित है।

2.  जावा के लिए Aspose.Words: जावा के लिए Aspose.Words को यहां से डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/words/java/).

3. जावा का बुनियादी ज्ञान: जावा प्रोग्रामिंग से परिचित होना सहायक होगा क्योंकि हम कस्टम बारकोड लेबल बनाने के लिए जावा कोड लिखेंगे।

## कस्टम बारकोड लेबल बनाना

अब, जावा के लिए Aspose.Words का उपयोग करके कस्टम बारकोड लेबल बनाना शुरू करें। हम प्रक्रिया को चरणों में विभाजित करेंगे और प्रत्येक चरण के लिए जावा कोड स्निपेट प्रदान करेंगे।

## बारकोड की ऊँचाई निर्धारित करना

आरंभ करने के लिए, हमें अपने बारकोड की ऊंचाई को ट्विप्स (1/1440 इंच) में सेट करना होगा। फिर हम इस मान को मिलीमीटर (मिमी) में बदल देंगे। इसे पूरा करने के लिए कोड यहां दिया गया है:

```java
	// इनपुट मान 1/1440 इंच (twips) में है
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// मिमी में कनवर्ट करें
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## बारकोड छवि रंग परिवर्तित करना

इसके बाद, हम बारकोड छवि के रंग को Word से Aspose.BarCode में बदल देंगे। इनपुट रंग "0xRRGGBB" (हेक्साडेसिमल) प्रारूप में होना चाहिए। यहाँ रूपांतरण के लिए कोड है:

```java
/// <सारांश>
/// बारकोड छवि रंग को वर्ड से Aspose.BarCode में परिवर्तित करता है।
///</सारांश>
/// <param name='inputColor'></param>
/// <रिटर्न्स></रिटर्न्स>
private static Color convertColor(String inputColor) throws Exception {
	// इनपुट "0x000000" से "0xFFFFFF" तक होना चाहिए
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## बारकोड स्केलिंग फ़ैक्टर को परिवर्तित करना

अब, हम बारकोड स्केलिंग फैक्टर को प्रतिशत से फ्लोट वैल्यू में बदल देंगे। यह स्केलिंग कारक बारकोड का आकार निर्धारित करता है। यहाँ रूपांतरण के लिए कोड है:

```java
/// <सारांश>
/// बार कोड स्केलिंग फैक्टर को प्रतिशत से फ्लोट में परिवर्तित करता है।
///</सारांश>
/// <परम नाम='स्केलिंगफैक्टर'></परम>
/// <रिटर्न्स></रिटर्न्स>
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

## GetBarCodeImage() विधि को कार्यान्वित करना

 इस चरण में, हम इसे लागू करेंगे`getBarcodeImage` विधि, जो दिए गए मापदंडों के आधार पर बारकोड छवि उत्पन्न करती है। हम विभिन्न बारकोड प्रकारों को संभालेंगे, रंग सेट करेंगे, आयाम समायोजित करेंगे, और बहुत कुछ करेंगे। इस विधि के लिए कोड यहां दिया गया है:

```java
/// <सारांश>
/// IBarCodeGenerator इंटरफ़ेस के लिए GetBarCodeImage() विधि का कार्यान्वयन।
///</सारांश>
/// <परम नाम = "पैरामीटर"></परम>
/// <रिटर्न्स></रिटर्न्स>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// जांचें कि क्या बारकोड प्रकार और मूल्य प्रदान किया गया है
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// बारकोड प्रकार के आधार पर एक बारकोड जेनरेटर बनाएं
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
	
	// प्रतीक की ऊँचाई और आयाम निर्धारित करें
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	//कोड टेक्स्ट स्थान को अनुकूलित करें
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// क्यूआर कोड के लिए अतिरिक्त समायोजन
	final float SCALE = 2.4f; // वर्ड बारकोड को Aspose.BarCode में परिवर्तित करने के लिए अनुभवजन्य स्केलिंग कारक
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
	
	// स्केलिंग फैक्टर लागू करें
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
	
	// बारकोड छवि बनाएं और वापस करें
	return generator.generateBarCodeImage();
}
```

## GetOldBarcodeImage() विधि को कार्यान्वित करना

 इस चरण में, हम इसे लागू करेंगे`getOldBarcodeImage` विधि, जो पुराने जमाने के बारकोड के लिए बारकोड छवियां उत्पन्न करती है। यहां, हम एक विशिष्ट बारकोड प्रकार, जैसे POSTNET, को संभालेंगे। इस विधि के लिए कोड यहां दिया गया है:

```java
/// <सारांश>
/// IBarCodeGenerator इंटरफ़ेस के लिए GetOldBarcodeImage() विधि का कार्यान्वयन।
///</सारांश>
/// <परम नाम = "पैरामीटर"></परम>
/// <रिटर्न्स></रिटर्न्स>
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

इस लेख में, हमने जावा के लिए Aspose.Words का उपयोग करके कस्टम बारकोड लेबल बनाने की प्रक्रिया का पता लगाया है। हमने बारकोड की ऊंचाई निर्धारित करने से लेकर बारकोड जेनरेशन के तरीकों को लागू करने तक आवश्यक कदमों को कवर किया। जावा के लिए Aspose.Words डेवलपर्स को गतिशील और अनुकूलित बारकोड लेबल बनाने का अधिकार देता है, जिससे यह विभिन्न उद्योगों के लिए एक मूल्यवान उपकरण बन जाता है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जेनरेट किए गए बारकोड का आकार कैसे समायोजित कर सकता हूं?

आप दिए गए कोड स्निपेट में बारकोड की प्रतीक ऊंचाई और स्केलिंग कारक सेट करके जेनरेट किए गए बारकोड के आकार को समायोजित कर सकते हैं। ये पैरामीटर आपको अपनी आवश्यकताओं के अनुसार बारकोड के आयामों को नियंत्रित करने की अनुमति देते हैं।

### क्या मैं बारकोड का रंग बदल सकता हूँ?

हां, आप कोड में अग्रभूमि और पृष्ठभूमि रंग निर्दिष्ट करके बारकोड के रंग बदल सकते हैं। यह अनुकूलन आपको अपने दस्तावेज़ के डिज़ाइन के साथ बारकोड की उपस्थिति का मिलान करने की अनुमति देता है।

### Java के लिए Aspose.Words द्वारा कौन से बारकोड प्रकार समर्थित हैं?

जावा के लिए Aspose.Words विभिन्न बारकोड प्रकारों का समर्थन करता है, जिनमें QR कोड, Code128, Code39, EAN8, EAN13, UPCA, UPCE, ITF14 और बहुत कुछ शामिल हैं। आप वह बारकोड प्रकार चुन सकते हैं जो आपके एप्लिकेशन की आवश्यकताओं के अनुरूप हो।

### मैं जेनरेट किए गए बारकोड को अपने वर्ड दस्तावेज़ में कैसे एकीकृत करूं?

जेनरेट किए गए बारकोड को अपने वर्ड दस्तावेज़ में एकीकृत करने के लिए, आप जावा की दस्तावेज़ हेरफेर क्षमताओं के लिए Aspose.Words का उपयोग कर सकते हैं। आप बारकोड छवि को अपने दस्तावेज़ में वांछित स्थान पर सम्मिलित कर सकते हैं।

### क्या आगे अनुकूलन के लिए कोई नमूना कोड उपलब्ध है?

 हां, आप जावा की संदर्भ साइट के लिए Aspose.Words पर नमूना कोड स्निपेट और अतिरिक्त दस्तावेज़ पा सकते हैं:[जावा एपीआई संदर्भ के लिए Aspose.Words](https://reference.aspose.com/words/java/).