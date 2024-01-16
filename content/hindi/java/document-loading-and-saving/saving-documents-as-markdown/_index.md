---
title: जावा के लिए Aspose.Words में दस्तावेज़ों को मार्कडाउन के रूप में सहेजना
linktitle: दस्तावेज़ों को मार्कडाउन के रूप में सहेजना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words के साथ Word दस्तावेज़ों को मार्कडाउन में परिवर्तित करना सीखें। यह चरण-दर-चरण मार्गदर्शिका तालिका संरेखण, छवि प्रबंधन और बहुत कुछ शामिल करती है।
type: docs
weight: 18
url: /hi/java/document-loading-and-saving/saving-documents-as-markdown/
---

## जावा के लिए Aspose.Words में दस्तावेज़ों को मार्कडाउन के रूप में सहेजने का परिचय

इस चरण-दर-चरण मार्गदर्शिका में, हम दिखाएंगे कि जावा के लिए Aspose.Words का उपयोग करके दस्तावेज़ों को मार्कडाउन के रूप में कैसे सहेजा जाए। मार्कडाउन एक हल्की मार्कअप भाषा है जिसका उपयोग आमतौर पर टेक्स्ट दस्तावेज़ों को फ़ॉर्मेट करने के लिए किया जाता है। जावा के लिए Aspose.Words के साथ, आप आसानी से अपने Word दस्तावेज़ों को मार्कडाउन प्रारूप में परिवर्तित कर सकते हैं। हम टेबल सामग्री संरेखण और छवियों को संभालने सहित मार्कडाउन फ़ाइलों को सहेजने के विभिन्न पहलुओं को कवर करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Words। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/words/java/).

## चरण 1: एक वर्ड दस्तावेज़ बनाना

आइए एक वर्ड डॉक्यूमेंट बनाकर शुरुआत करें जिसे हम बाद में मार्कडाउन फॉर्मेट में बदल देंगे। आप इस दस्तावेज़ को अपनी आवश्यकताओं के अनुसार अनुकूलित कर सकते हैं।

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// दो कक्षों वाली एक तालिका सम्मिलित करें
builder.insertCell();
builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
builder.write("Cell1");

builder.insertCell();
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.write("Cell2");

// दस्तावेज़ को मार्कडाउन के रूप में सहेजें
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
doc.save("output.md", saveOptions);
```

 इस उदाहरण में, हम दो कोशिकाओं के साथ एक सरल तालिका बनाते हैं और इन कोशिकाओं के भीतर पैराग्राफ के संरेखण को सेट करते हैं। फिर, हम दस्तावेज़ को मार्कडाउन के रूप में सहेजते हैं`MarkdownSaveOptions`.

## चरण 2: तालिका सामग्री संरेखण को अनुकूलित करें

जावा के लिए Aspose.Words आपको मार्कडाउन के रूप में सहेजते समय तालिका सामग्री के संरेखण को अनुकूलित करने की अनुमति देता है। आप तालिका सामग्री को बाएँ, दाएँ, केंद्र में संरेखित कर सकते हैं, या प्रत्येक तालिका कॉलम में पहले पैराग्राफ के आधार पर इसे स्वचालित रूप से निर्धारित करने दे सकते हैं।

तालिका सामग्री संरेखण को अनुकूलित करने का तरीका यहां बताया गया है:

```java
// तालिका सामग्री संरेखण को बाईं ओर सेट करें
saveOptions.setTableContentAlignment(TableContentAlignment.LEFT);
doc.save("left_alignment.md", saveOptions);

// तालिका सामग्री संरेखण को दाईं ओर सेट करें
saveOptions.setTableContentAlignment(TableContentAlignment.RIGHT);
doc.save("right_alignment.md", saveOptions);

// तालिका सामग्री संरेखण को केंद्र में सेट करें
saveOptions.setTableContentAlignment(TableContentAlignment.CENTER);
doc.save("center_alignment.md", saveOptions);

//तालिका सामग्री संरेखण को ऑटो पर सेट करें (पहले पैराग्राफ द्वारा निर्धारित)
saveOptions.setTableContentAlignment(TableContentAlignment.AUTO);
doc.save("auto_alignment.md", saveOptions);
```

 को बदलने से`TableContentAlignment` संपत्ति, आप यह नियंत्रित कर सकते हैं कि मार्कडाउन में कनवर्ट करते समय तालिकाओं के अंदर की सामग्री को कैसे संरेखित किया जाए।

## चरण 3: छवियों को संभालना

 अपने मार्कडाउन दस्तावेज़ में छवियां शामिल करने के लिए, आपको वह फ़ोल्डर निर्दिष्ट करना होगा जहां छवियां स्थित हैं। जावा के लिए Aspose.Words आपको इमेज फ़ोल्डर सेट करने की अनुमति देता है`MarkdownSaveOptions`.

यहां इमेज फ़ोल्डर को सेट करने और छवियों के साथ दस्तावेज़ को सहेजने का तरीका बताया गया है:

```java
// छवियों वाला दस्तावेज़ लोड करें
Document doc = new Document("document_with_images.docx");

// छवियाँ फ़ोल्डर पथ सेट करें
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
saveOptions.setImagesFolder("images_folder/");

// दस्तावेज़ को छवियों के साथ सहेजें
doc.save("document_with_images.md", saveOptions);
```

 प्रतिस्थापित करना सुनिश्चित करें`"document_with_images.docx"` आपके Word दस्तावेज़ के पथ के साथ जिसमें छवियाँ और शामिल हैं`"images_folder/"` उस फ़ोल्डर के वास्तविक पथ के साथ जहां आपकी छवियां संग्रहीत हैं।

## जावा के लिए Aspose.Words में मार्कडाउन के रूप में दस्तावेज़ों को सहेजने के लिए संपूर्ण स्रोत कोड

```java
public void autoTableContentAlignment() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertCell();
	builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
	builder.write("Cell1");
	builder.insertCell();
	builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
	builder.write("Cell2");
	// तालिका के अंदर सभी अनुच्छेदों को संरेखित करता है।
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
	{
		saveOptions.setTableContentAlignment(TableContentAlignment.LEFT);
	}
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);
	saveOptions.setTableContentAlignment(TableContentAlignment.RIGHT);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);
	saveOptions.setTableContentAlignment(TableContentAlignment.CENTER);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);
	// इस मामले में संरेखण संबंधित तालिका कॉलम में पहले पैराग्राफ से लिया जाएगा।
	saveOptions.setTableContentAlignment(TableContentAlignment.AUTO);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
}
@Test
public void setImagesFolder() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Image bullet points.docx");
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions(); { saveOptions.setImagesFolder("Your Directory Path" + "Images"); }
	try(ByteArrayOutputStream stream = new ByteArrayOutputStream())
	{
		doc.save(stream, saveOptions);
	}
}
```

## निष्कर्ष

इस गाइड में, हमने पता लगाया है कि जावा के लिए Aspose.Words का उपयोग करके दस्तावेज़ों को मार्कडाउन के रूप में कैसे सहेजा जाए। हमने वर्ड दस्तावेज़ के निर्माण, तालिका सामग्री संरेखण को अनुकूलित करने और मार्कडाउन फ़ाइलों में छवियों को संभालने पर चर्चा की। अब आप अपने वर्ड दस्तावेज़ों को कुशलतापूर्वक मार्कडाउन प्रारूप में परिवर्तित कर सकते हैं, जिससे वे विभिन्न प्रकाशन प्लेटफार्मों और दस्तावेज़ीकरण आवश्यकताओं के लिए उपयुक्त हो जाएंगे।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Words कैसे स्थापित करूं?

 आपके जावा प्रोजेक्ट में लाइब्रेरी को शामिल करके जावा के लिए Aspose.Words स्थापित किया जा सकता है। आप यहां से लाइब्रेरी डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/words/java/) और दस्तावेज़ में दिए गए इंस्टॉलेशन निर्देशों का पालन करें।

### क्या मैं तालिकाओं और छवियों के साथ जटिल वर्ड दस्तावेज़ों को मार्कडाउन में परिवर्तित कर सकता हूँ?

हां, जावा के लिए Aspose.Words तालिकाओं, छवियों और विभिन्न स्वरूपण तत्वों के साथ जटिल Word दस्तावेज़ों को मार्कडाउन में बदलने का समर्थन करता है। आप अपने दस्तावेज़ की जटिलता के अनुसार मार्कडाउन आउटपुट को कस्टमाइज़ कर सकते हैं।

### मैं मार्कडाउन फ़ाइलों में छवियों को कैसे संभाल सकता हूँ?

 मार्कडाउन फ़ाइलों में छवियों को शामिल करने के लिए, का उपयोग करके छवि फ़ोल्डर पथ सेट करें`setImagesFolder`विधि में`MarkdownSaveOptions`. सुनिश्चित करें कि छवि फ़ाइलें निर्दिष्ट फ़ोल्डर में संग्रहीत हैं, और जावा के लिए Aspose.Words तदनुसार छवि संदर्भों को संभालेगा।

### क्या जावा के लिए Aspose.Words का कोई परीक्षण संस्करण उपलब्ध है?

हाँ, आप Aspose वेबसाइट से Java के लिए Aspose.Words का परीक्षण संस्करण प्राप्त कर सकते हैं। परीक्षण संस्करण आपको लाइसेंस खरीदने से पहले लाइब्रेरी की क्षमताओं का मूल्यांकन करने की अनुमति देता है।

### मुझे और अधिक उदाहरण और दस्तावेज़ कहां मिल सकते हैं?

 जावा के लिए Aspose.Words पर अधिक उदाहरणों, दस्तावेज़ीकरण और विस्तृत जानकारी के लिए, कृपया देखें[प्रलेखन](https://reference.aspose.com/words/java/).