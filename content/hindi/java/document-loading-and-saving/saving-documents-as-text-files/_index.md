---
title: जावा के लिए Aspose.Words में दस्तावेज़ों को टेक्स्ट फ़ाइलों के रूप में सहेजना
linktitle: दस्तावेज़ों को टेक्स्ट फ़ाइलों के रूप में सहेजना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words में दस्तावेज़ों को टेक्स्ट फ़ाइलों के रूप में सहेजना सीखें। जावा कोड उदाहरणों के साथ हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 24
url: /hi/java/document-loading-and-saving/saving-documents-as-text-files/
---

## जावा के लिए Aspose.Words में दस्तावेज़ों को टेक्स्ट फ़ाइलों के रूप में सहेजने का परिचय

इस ट्यूटोरियल में, हम यह पता लगाएंगे कि जावा लाइब्रेरी के लिए Aspose.Words का उपयोग करके दस्तावेज़ों को टेक्स्ट फ़ाइलों के रूप में कैसे सहेजा जाए। Aspose.Words Word दस्तावेज़ों के साथ काम करने के लिए एक शक्तिशाली जावा एपीआई है, और यह सादे पाठ सहित विभिन्न स्वरूपों में दस्तावेज़ों को सहेजने के लिए विभिन्न विकल्प प्रदान करता है। हम इसे प्राप्त करने के चरणों को कवर करेंगे और रास्ते में नमूना जावा कोड प्रदान करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Words आपके प्रोजेक्ट में एकीकृत है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/words/java/).
- जावा प्रोग्रामिंग का बुनियादी ज्ञान।

## चरण 1: एक दस्तावेज़ बनाएँ

किसी दस्तावेज़ को टेक्स्ट फ़ाइल के रूप में सहेजने के लिए, हमें सबसे पहले Aspose.Words का उपयोग करके एक दस्तावेज़ बनाना होगा। कुछ सामग्री के साथ दस्तावेज़ बनाने के लिए यहां एक सरल जावा कोड स्निपेट दिया गया है:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

इस कोड में, हम एक नया दस्तावेज़ बनाते हैं और उसमें कुछ टेक्स्ट जोड़ते हैं, जिसमें विभिन्न भाषाओं के टेक्स्ट भी शामिल होते हैं।

## चरण 2: टेक्स्ट सेव विकल्पों को परिभाषित करें

इसके बाद, हमें टेक्स्ट सेव विकल्पों को परिभाषित करने की आवश्यकता है जो निर्दिष्ट करते हैं कि दस्तावेज़ को टेक्स्ट फ़ाइल के रूप में कैसे सहेजा जाना चाहिए। हम विभिन्न सेटिंग्स कॉन्फ़िगर कर सकते हैं जैसे बीड़ी चिह्न जोड़ना, सूची इंडेंटेशन, और बहुत कुछ। आइए दो उदाहरण देखें:

### उदाहरण 1: बीड़ी के निशान जोड़ना

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

 इस उदाहरण में, हम एक बनाते हैं`TxtSaveOptions` ऑब्जेक्ट करें और सेट करें`AddBidiMarks`संपत्ति को`true` टेक्स्ट आउटपुट में बीड़ी के निशान शामिल करने के लिए।

### उदाहरण 2: सूची इंडेंटेशन के लिए टैब कैरेक्टर का उपयोग करना

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

यहां, हम 1 की गिनती के साथ सूची इंडेंटेशन के लिए टैब कैरेक्टर का उपयोग करने के लिए सेव विकल्पों को कॉन्फ़िगर करते हैं।

## चरण 3: दस्तावेज़ को टेक्स्ट के रूप में सहेजें

अब जब हमने टेक्स्ट सेव विकल्पों को परिभाषित कर लिया है, तो हम दस्तावेज़ को टेक्स्ट फ़ाइल के रूप में सहेज सकते हैं। निम्नलिखित कोड दर्शाता है कि यह कैसे करना है:

```java
doc.save("output.txt", saveOptions);
```

 प्रतिस्थापित करें`"output.txt"` वांछित फ़ाइल पथ के साथ जहां आप टेक्स्ट फ़ाइल को सहेजना चाहते हैं।

## जावा के लिए Aspose.Words में दस्तावेज़ों को टेक्स्ट फ़ाइलों के रूप में सहेजने के लिए संपूर्ण स्रोत कोड

```java
    public void addBidiMarks() throws Exception
    {        
		Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello world!");
        builder.getParagraphFormat().setBidi(true);
        builder.writeln("שלום עולם!");
        builder.writeln("مرحبا بالعالم!");
        TxtSaveOptions saveOptions = new TxtSaveOptions(); { saveOptions.setAddBidiMarks(true); }
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
    }
    @Test
    public void useTabCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // इंडेंटेशन के तीन स्तरों के साथ एक सूची बनाएं।
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(1);
        saveOptions.getListIndentation().setCharacter('\t');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
    }
    @Test
    public void useSpaceCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // इंडेंटेशन के तीन स्तरों के साथ एक सूची बनाएं।
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(3);
        saveOptions.getListIndentation().setCharacter(' ');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
	}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि जावा के लिए Aspose.Words में दस्तावेज़ों को टेक्स्ट फ़ाइलों के रूप में कैसे सहेजा जाए। हमने दस्तावेज़ बनाने, टेक्स्ट सेव विकल्पों को परिभाषित करने और दस्तावेज़ को टेक्स्ट प्रारूप में सहेजने के चरणों को कवर किया है। जब दस्तावेज़ों को सहेजने की बात आती है तो Aspose.Words व्यापक लचीलापन प्रदान करता है, जिससे आप आउटपुट को अपनी विशिष्ट आवश्यकताओं के अनुरूप बना सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं टेक्स्ट आउटपुट में बीड़ी के निशान कैसे जोड़ूँ?

 टेक्स्ट आउटपुट में बीड़ी चिह्न जोड़ने के लिए, सेट करें`AddBidiMarks` की संपत्ति`TxtSaveOptions` को`true`. उदाहरण के लिए:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### क्या मैं सूची इंडेंटेशन वर्ण को अनुकूलित कर सकता हूँ?

 हाँ, आप कॉन्फ़िगर करके सूची इंडेंटेशन वर्ण को अनुकूलित कर सकते हैं`ListIndentation` की संपत्ति`TxtSaveOptions`. उदाहरण के लिए, सूची इंडेंटेशन के लिए टैब वर्ण का उपयोग करने के लिए, आप निम्न कार्य कर सकते हैं:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### क्या जावा के लिए Aspose.Words बहुभाषी पाठ को संभालने के लिए उपयुक्त है?

हां, जावा के लिए Aspose.Words बहुभाषी पाठ को संभालने के लिए उपयुक्त है। यह विभिन्न भाषाओं और कैरेक्टर एन्कोडिंग का समर्थन करता है, जिससे यह विभिन्न भाषाओं में दस्तावेज़ों के साथ काम करने के लिए एक बहुमुखी विकल्प बन जाता है।

### मैं जावा के लिए Aspose.Words के लिए अधिक दस्तावेज़ और संसाधनों तक कैसे पहुंच सकता हूं?

 आप Aspose दस्तावेज़ीकरण वेबसाइट पर जावा के लिए Aspose.Words के लिए व्यापक दस्तावेज़ और संसाधन पा सकते हैं:[जावा दस्तावेज़ीकरण के लिए Aspose.Words](https://reference.aspose.com/words/java/).

### मैं जावा के लिए Aspose.Words कहां से डाउनलोड कर सकता हूं?

 आप Aspose वेबसाइट से जावा लाइब्रेरी के लिए Aspose.Words डाउनलोड कर सकते हैं:[जावा के लिए Aspose.Words डाउनलोड करें](https://releases.aspose.com/words/java/).