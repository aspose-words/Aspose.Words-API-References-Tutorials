---
title: जावा के लिए Aspose.Words में सूचियों का उपयोग करना
linktitle: सूचियों का उपयोग करना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: इस चरण-दर-चरण ट्यूटोरियल के साथ जावा के लिए Aspose.Words में सूचियों का उपयोग करना सीखें। अपने दस्तावेज़ों को प्रभावी ढंग से व्यवस्थित और प्रारूपित करें।
type: docs
weight: 18
url: /hi/java/using-document-elements/using-lists/
---

इस व्यापक ट्यूटोरियल में, हम यह पता लगाएंगे कि जावा के लिए Aspose.Words में सूचियों का प्रभावी ढंग से उपयोग कैसे किया जाए, जो प्रोग्रामेटिक रूप से Microsoft Word दस्तावेज़ों के साथ काम करने के लिए एक शक्तिशाली एपीआई है। आपके दस्तावेज़ों में सामग्री की संरचना और व्यवस्थित करने के लिए सूचियाँ आवश्यक हैं। हम सूचियों के साथ काम करने के दो प्रमुख पहलुओं को कवर करेंगे: प्रत्येक अनुभाग पर सूचियों को पुनः प्रारंभ करना और सूची स्तरों को निर्दिष्ट करना। आइए गोता लगाएँ!

## जावा के लिए Aspose.Words का परिचय

इससे पहले कि हम सूचियों के साथ काम करना शुरू करें, आइए जावा के लिए Aspose.Words से परिचित हो जाएं। यह एपीआई डेवलपर्स को जावा वातावरण में वर्ड दस्तावेज़ बनाने, संशोधित करने और हेरफेर करने के लिए उपकरण प्रदान करता है। यह सरल दस्तावेज़ निर्माण से लेकर जटिल स्वरूपण और सामग्री प्रबंधन तक के कार्यों के लिए एक बहुमुखी समाधान है।

### अपना वातावरण स्थापित करना

 आरंभ करने के लिए, सुनिश्चित करें कि आपके पास जावा के लिए Aspose.Words स्थापित है और आपके विकास परिवेश में स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/words/java/). 

## प्रत्येक अनुभाग पर सूचियाँ पुनः आरंभ करना

कई परिदृश्यों में, आपको अपने दस्तावेज़ के प्रत्येक अनुभाग में सूचियों को पुनः आरंभ करने की आवश्यकता हो सकती है। यह रिपोर्ट, मैनुअल या अकादमिक पेपर जैसे कई अनुभागों के साथ संरचित दस्तावेज़ बनाने के लिए उपयोगी हो सकता है।

जावा के लिए Aspose.Words का उपयोग करके इसे कैसे प्राप्त करें, इस पर चरण-दर-चरण मार्गदर्शिका यहां दी गई है:

### अपना दस्तावेज़ प्रारंभ करें: 
एक नया दस्तावेज़ ऑब्जेक्ट बनाकर प्रारंभ करें।

```java
Document doc = new Document();
```

### क्रमांकित सूची जोड़ें: 
अपने दस्तावेज़ में क्रमांकित सूची जोड़ें. हम डिफ़ॉल्ट क्रमांकन शैली का उपयोग करेंगे.

```java
doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
```

### सूची सेटिंग्स कॉन्फ़िगर करें: 
\प्रत्येक अनुभाग पर सूची को पुनः प्रारंभ करने के लिए सक्षम करें।

```java
List list = doc.getLists().get(0);
list.isRestartAtEachSection(true);
```

### दस्तावेज़बिल्डर सेटअप: 
अपने दस्तावेज़ में सामग्री जोड़ने के लिए एक DocumentBuilder बनाएँ।

```java
DocumentBuilder builder = new DocumentBuilder(doc);
builder.getListFormat().setList(list);
```

### सूची आइटम जोड़ें: 
अपने दस्तावेज़ में सूची आइटम जोड़ने के लिए लूप का उपयोग करें। हम 15वें आइटम के बाद एक अनुभाग विराम सम्मिलित करेंगे।

```java
for (int i = 1; i < 45; i++) {
    builder.writeln(MessageFormat.format("List Item {0}", i));
    if (i == 15)
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
}
```

### अपना दस्तावेज़ सहेजें: 
वांछित विकल्पों के साथ दस्तावेज़ को सहेजें।

```java
OoxmlSaveOptions options = new OoxmlSaveOptions();
options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);
doc.save(outPath + "RestartListAtEachSection.docx", options);
```

इन चरणों का पालन करके, आप स्पष्ट और व्यवस्थित सामग्री संरचना को बनाए रखते हुए, प्रत्येक अनुभाग में पुनरारंभ होने वाली सूचियों के साथ दस्तावेज़ बना सकते हैं।

## सूची स्तर निर्दिष्ट करना

जावा के लिए Aspose.Words आपको सूची स्तर निर्दिष्ट करने की अनुमति देता है, जो विशेष रूप से तब उपयोगी होता है जब आपको अपने दस्तावेज़ में विभिन्न सूची प्रारूपों की आवश्यकता होती है। आइए जानें कि यह कैसे करें:

### अपना दस्तावेज़ प्रारंभ करें: 
एक नया दस्तावेज़ ऑब्जेक्ट बनाएँ।

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### एक क्रमांकित सूची बनाएं: 
माइक्रोसॉफ्ट वर्ड से क्रमांकित सूची टेम्पलेट लागू करें।

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
```

### सूची स्तर निर्दिष्ट करें: 
विभिन्न सूची स्तरों के माध्यम से पुनरावृति करें और सामग्री जोड़ें।

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### एक बुलेटेड सूची बनाएं: 
अब, आइए एक बुलेटेड सूची बनाएं।

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
```

### बुलेटेड सूची स्तर निर्दिष्ट करें: 
क्रमांकित सूची के समान, स्तर निर्दिष्ट करें और सामग्री जोड़ें।

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### स्टॉप लिस्ट फ़ॉर्मेटिंग: 
सूची फ़ॉर्मेटिंग रोकने के लिए, सूची को शून्य पर सेट करें।

```java
builder.getListFormat().setList(null);
```

### अपना दस्तावेज़ सहेजें: 
दस्तावेज़ सहेजें.

```java
builder.getDocument().save(outPath + "SpecifyListLevel.docx");
```

इन चरणों का पालन करके, आप कस्टम सूची स्तरों के साथ दस्तावेज़ बना सकते हैं, जिससे आप अपने दस्तावेज़ों में सूचियों के स्वरूपण को नियंत्रित कर सकते हैं।

## संपूर्ण स्रोत कोड
```java
	string outPath = "Your Output Directory";
 public void restartListAtEachSection() throws Exception
    {
        Document doc = new Document();
        doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
        List list = doc.getLists().get(0);
        list.isRestartAtEachSection(true);
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.getListFormat().setList(list);
        for (int i = 1; i < 45; i++)
        {
            builder.writeln(MessageFormat.format("List Item {0}", i));
            if (i == 15)
                builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        }
        // IsRestartAtEachSection तभी लिखा जाएगा जब अनुपालन OoxmlComplianceCore.Ecma376 से अधिक होगा।
        OoxmlSaveOptions options = new OoxmlSaveOptions(); { options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL); }
        doc.save(outPath + "WorkingWithList.RestartListAtEachSection.docx", options);
    }
    @Test
    public void specifyListLevel() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Microsoft Word सूची टेम्प्लेट में से किसी एक के आधार पर एक क्रमांकित सूची बनाएं
        //और इसे दस्तावेज़ निर्माता के वर्तमान पैराग्राफ पर लागू करें।
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
        // इस सूची में नौ स्तर हैं, आइए उन सभी को आज़माएँ।
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // Microsoft Word सूची टेम्प्लेट में से किसी एक के आधार पर एक बुलेटेड सूची बनाएं
        //और इसे दस्तावेज़ निर्माता के वर्तमान पैराग्राफ पर लागू करें।
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // यह सूची स्वरूपण को रोकने का एक तरीका है।
        builder.getListFormat().setList(null);
        builder.getDocument().save(outPath + "WorkingWithList.SpecifyListLevel.docx");
    }
    @Test
    public void restartListNumber() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // टेम्पलेट के आधार पर एक सूची बनाएं.
        List list1 = doc.getLists().add(ListTemplate.NUMBER_ARABIC_PARENTHESIS);
        list1.getListLevels().get(0).getFont().setColor(Color.RED);
        list1.getListLevels().get(0).setAlignment(ListLevelAlignment.RIGHT);
        builder.writeln("List 1 starts below:");
        builder.getListFormat().setList(list1);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        // पहली सूची का पुन: उपयोग करने के लिए, हमें मूल सूची स्वरूपण की एक प्रति बनाकर क्रमांकन को पुनः आरंभ करना होगा।
        List list2 = doc.getLists().addCopy(list1);
        // हम नई सूची को किसी भी तरह से संशोधित कर सकते हैं, जिसमें नया प्रारंभ नंबर सेट करना भी शामिल है।
        list2.getListLevels().get(0).setStartAt(10);
        builder.writeln("List 2 starts below:");
        builder.getListFormat().setList(list2);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        builder.getDocument().save(outPath + "WorkingWithList.RestartListNumber.docx");
	}
```

## निष्कर्ष

बधाई हो! आपने जावा के लिए Aspose.Words में सूचियों के साथ प्रभावी ढंग से काम करना सीख लिया है। आपके दस्तावेज़ों में सामग्री को व्यवस्थित करने और प्रस्तुत करने के लिए सूचियाँ महत्वपूर्ण हैं। चाहे आपको प्रत्येक अनुभाग में सूचियों को पुनः आरंभ करने या सूची स्तर निर्दिष्ट करने की आवश्यकता हो, जावा के लिए Aspose.Words आपको पेशेवर दिखने वाले दस्तावेज़ बनाने के लिए आवश्यक उपकरण प्रदान करता है।

अब आप अपने दस्तावेज़ निर्माण और फ़ॉर्मेटिंग कार्यों को बेहतर बनाने के लिए इन सुविधाओं का आत्मविश्वास से उपयोग कर सकते हैं। यदि आपके कोई प्रश्न हैं या आपको अतिरिक्त सहायता की आवश्यकता है, तो संपर्क करने में संकोच न करें[Aspose सामुदायिक मंच](https://forum.aspose.com/) समर्थन के लिए।

## पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Words कैसे स्थापित करूं?
 आप जावा के लिए Aspose.Words डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/words/java/) और दस्तावेज़ में दिए गए इंस्टॉलेशन निर्देशों का पालन करें।

### क्या मैं सूचियों के क्रमांकन प्रारूप को अनुकूलित कर सकता हूँ?
हां, जावा के लिए Aspose.Words सूची क्रमांकन प्रारूपों को अनुकूलित करने के लिए व्यापक विकल्प प्रदान करता है। आप विवरण के लिए एपीआई दस्तावेज़ देख सकते हैं।

### क्या जावा के लिए Aspose.Words नवीनतम वर्ड दस्तावेज़ मानकों के साथ संगत है?
हाँ, आप आईएसओ 29500 सहित विभिन्न वर्ड दस्तावेज़ मानकों का अनुपालन करने के लिए जावा के लिए Aspose.Words को कॉन्फ़िगर कर सकते हैं।

### क्या मैं जावा के लिए Aspose.Words का उपयोग करके तालिकाओं और छवियों के साथ जटिल दस्तावेज़ तैयार कर सकता हूँ?
बिल्कुल! जावा के लिए Aspose.Words उन्नत दस्तावेज़ स्वरूपण का समर्थन करता है, जिसमें तालिकाएँ, चित्र और बहुत कुछ शामिल हैं। उदाहरणों के लिए दस्तावेज़ की जाँच करें.

### मैं जावा के लिए Aspose.Words के लिए अस्थायी लाइसेंस कहां से प्राप्त कर सकता हूं?
 आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
