---
title: जावा के लिए Aspose.Words में शैलियों और विषयों का उपयोग करना
linktitle: शैलियों और विषयों का उपयोग करना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि Java के लिए Aspose.Words के साथ दस्तावेज़ फ़ॉर्मेटिंग को कैसे बढ़ाया जाए। स्रोत कोड उदाहरणों के साथ इस व्यापक मार्गदर्शिका में शैलियों, विषयों और बहुत कुछ का अन्वेषण करें।
type: docs
weight: 20
url: /hi/java/document-manipulation/using-styles-and-themes/
---

## जावा के लिए Aspose.Words में शैलियों और विषयों का उपयोग करने का परिचय

इस गाइड में, हम यह पता लगाएंगे कि आपके दस्तावेज़ों की फ़ॉर्मेटिंग और उपस्थिति को बढ़ाने के लिए जावा के लिए Aspose.Words में शैलियों और थीम के साथ कैसे काम किया जाए। हम शैलियों को पुनः प्राप्त करने, शैलियों की प्रतिलिपि बनाने, थीम प्रबंधित करने और शैली विभाजक सम्मिलित करने जैसे विषयों को कवर करेंगे। आएँ शुरू करें!

## शैलियाँ पुनर्प्राप्त करना

किसी दस्तावेज़ से शैलियाँ पुनर्प्राप्त करने के लिए, आप निम्नलिखित जावा कोड स्निपेट का उपयोग कर सकते हैं:

```java
Document doc = new Document();
String styleName = "";
//दस्तावेज़ से शैलियों का संग्रह प्राप्त करें।
StyleCollection styles = doc.getStyles();
for (Style style : styles)
{
    if ("".equals(styleName))
    {
        styleName = style.getName();
        System.out.println(styleName);
    }
    else
    {
        styleName = styleName + ", " + style.getName();
        System.out.println(styleName);
    }
}
```

यह कोड दस्तावेज़ में परिभाषित शैलियों को लाता है और उनके नाम प्रिंट करता है।

## शैलियाँ कॉपी करना

 शैलियों को एक दस्तावेज़ से दूसरे दस्तावेज़ में कॉपी करने के लिए, आप इसका उपयोग कर सकते हैं`copyStylesFromTemplate` विधि जैसा कि नीचे दिखाया गया है:

```java
@Test
public void copyStyles() throws Exception
{
    Document doc = new Document();
    Document target = new Document("Your Directory Path" + "Rendering.docx");
    target.copyStylesFromTemplate(doc);
    doc.save("Your Directory Path" + "WorkingWithStylesAndThemes.CopyStyles.docx");
}
```

यह कोड टेम्पलेट दस्तावेज़ से शैलियों को वर्तमान दस्तावेज़ में कॉपी करता है।

## थीम प्रबंधित करना

आपके दस्तावेज़ के समग्र स्वरूप को परिभाषित करने के लिए थीम आवश्यक हैं। आप थीम गुणों को पुनः प्राप्त और सेट कर सकते हैं जैसा कि निम्नलिखित कोड में दिखाया गया है:

```java
@Test
public void getThemeProperties() throws Exception
{
    Document doc = new Document();
    Theme theme = doc.getTheme();
    System.out.println(theme.getMajorFonts().getLatin());
    System.out.println(theme.getMinorFonts().getEastAsian());
    System.out.println(theme.getColors().getAccent1());
}

@Test
public void setThemeProperties() throws Exception
{
    Document doc = new Document();
    Theme theme = doc.getTheme();
    theme.getMinorFonts().setLatin("Times New Roman");
    theme.getColors().setHyperlink(Color.ORANGE);
}
```

ये स्निपेट प्रदर्शित करते हैं कि फ़ॉन्ट और रंग जैसे थीम गुणों को कैसे पुनः प्राप्त और संशोधित किया जाए।

## स्टाइल सेपरेटर सम्मिलित करना

स्टाइल सेपरेटर एक ही पैराग्राफ में विभिन्न शैलियों को लागू करने के लिए उपयोगी होते हैं। स्टाइल सेपरेटर कैसे डालें इसका एक उदाहरण यहां दिया गया है:

```java
@Test
public void insertStyleSeparator() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    Style paraStyle = builder.getDocument().getStyles().add(StyleType.PARAGRAPH, "MyParaStyle");
    paraStyle.getFont().setBold(false);
    paraStyle.getFont().setSize(8.0);
    paraStyle.getFont().setName("Arial");
    // टेक्स्ट को "शीर्षक 1" शैली के साथ जोड़ें।
    builder.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_1);
    builder.write("Heading 1");
    builder.insertStyleSeparator();
    // टेक्स्ट को किसी अन्य शैली के साथ जोड़ें.
    builder.getParagraphFormat().setStyleName(paraStyle.getName());
    builder.write("This is text with some other formatting ");
    doc.save("Your Directory Path" + "WorkingWithStylesAndThemes.InsertStyleSeparator.docx");
}
```

इस कोड में, हम एक कस्टम पैराग्राफ शैली बनाते हैं और उसी पैराग्राफ के भीतर शैलियों को स्विच करने के लिए एक स्टाइल सेपरेटर डालते हैं।

## निष्कर्ष

इस गाइड में जावा के लिए Aspose.Words में शैलियों और विषयों के साथ काम करने की मूल बातें शामिल हैं। आपने सीखा है कि कैसे शैलियों को पुनः प्राप्त और कॉपी किया जाए, थीम प्रबंधित की जाए और दृश्य रूप से आकर्षक और अच्छी तरह से प्रारूपित दस्तावेज़ बनाने के लिए शैली विभाजक सम्मिलित किए जाएं। अपनी आवश्यकताओं के अनुसार अपने दस्तावेज़ों को अनुकूलित करने के लिए इन तकनीकों का प्रयोग करें।


## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Words में थीम गुण कैसे पुनः प्राप्त कर सकता हूं?

आप थीम ऑब्जेक्ट और उसके गुणों तक पहुंच कर थीम गुणों को पुनः प्राप्त कर सकते हैं।

### मैं थीम गुण, जैसे फ़ॉन्ट और रंग, कैसे सेट कर सकता हूं?

आप थीम ऑब्जेक्ट के गुणों को संशोधित करके थीम गुण सेट कर सकते हैं।

### मैं एक ही पैराग्राफ में शैलियों को बदलने के लिए स्टाइल सेपरेटर का उपयोग कैसे कर सकता हूं?

 आप इसका उपयोग करके स्टाइल सेपरेटर सम्मिलित कर सकते हैं`insertStyleSeparator` की विधि`DocumentBuilder` कक्षा।