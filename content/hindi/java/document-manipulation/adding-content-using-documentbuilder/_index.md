---
title: Java के लिए Aspose.Words में DocumentBuilder का उपयोग करके सामग्री जोड़ना
linktitle: DocumentBuilder का उपयोग करके सामग्री जोड़ना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words के साथ मास्टर दस्तावेज़ निर्माण। टेक्स्ट, तालिकाएँ, छवियाँ और बहुत कुछ जोड़ने के लिए चरण-दर-चरण मार्गदर्शिका। सहजता से आश्चर्यजनक वर्ड दस्तावेज़ बनाएँ।
type: docs
weight: 26
url: /hi/java/document-manipulation/adding-content-using-documentbuilder/
---

## Java के लिए Aspose.Words में DocumentBuilder का उपयोग करके सामग्री जोड़ने का परिचय

इस चरण-दर-चरण मार्गदर्शिका में, हम यह पता लगाएंगे कि Word दस्तावेज़ में विभिन्न प्रकार की सामग्री जोड़ने के लिए Java के DocumentBuilder के लिए Aspose.Words का उपयोग कैसे करें। हम पाठ, तालिकाएँ, क्षैतिज नियम, फ़ॉर्म फ़ील्ड, HTML, हाइपरलिंक, सामग्री तालिका, इनलाइन और फ़्लोटिंग छवियां, पैराग्राफ और बहुत कुछ सम्मिलित करना कवर करेंगे। आएँ शुरू करें!

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके प्रोजेक्ट में जावा लाइब्रेरी के लिए Aspose.Words सेटअप है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/words/java/).

## पाठ जोड़ना

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// एक साधारण पाठ अनुच्छेद सम्मिलित करें
builder.write("This is a simple text paragraph.");

// दस्तावेज़ सहेजें
doc.save("path/to/your/document.docx");
```

## तालिकाएँ जोड़ना

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// एक तालिका प्रारंभ करें
Table table = builder.startTable();

// सेल और सामग्री सम्मिलित करें
builder.insertCell();
builder.write("Cell 1");

builder.insertCell();
builder.write("Cell 2");

// तालिका समाप्त करें
builder.endTable();

// दस्तावेज़ सहेजें
doc.save("path/to/your/document.docx");
```

## क्षैतिज नियम जोड़ना

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// एक क्षैतिज नियम सम्मिलित करें
builder.insertHorizontalRule();

// दस्तावेज़ सहेजें
doc.save("path/to/your/document.docx");
```

## प्रपत्र फ़ील्ड जोड़ना

### टेक्स्ट इनपुट फॉर्म फ़ील्ड

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// एक टेक्स्ट इनपुट फॉर्म फ़ील्ड डालें
builder.insertTextInput("TextInput", TextFormFieldType.REGULAR, "", "Default text", 0);

// दस्तावेज़ सहेजें
doc.save("path/to/your/document.docx");
```

### चेक बॉक्स प्रपत्र फ़ील्ड

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// एक चेक बॉक्स प्रपत्र फ़ील्ड सम्मिलित करें
builder.insertCheckBox("CheckBox", true, true, 0);

// दस्तावेज़ सहेजें
doc.save("path/to/your/document.docx");
```

### कॉम्बो बॉक्स फॉर्म फ़ील्ड

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// कॉम्बो बॉक्स के लिए आइटम परिभाषित करें
String[] items = { "Option 1", "Option 2", "Option 3" };

// कॉम्बो बॉक्स प्रपत्र फ़ील्ड सम्मिलित करें
builder.insertComboBox("DropDown", items, 0);

// दस्तावेज़ सहेजें
doc.save("path/to/your/document.docx");
```

## HTML जोड़ना

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// HTML सामग्री सम्मिलित करें
builder.insertHtml("<p>This is an HTML paragraph.</p>");

// दस्तावेज़ सहेजें
doc.save("path/to/your/document.docx");
```

## हाइपरलिंक्स जोड़ना

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// एक हाइपरलिंक डालें
builder.write("Visit ");
builder.getFont().setColor(Color.BLUE);
builder.getFont().setUnderline(Underline.SINGLE);
builder.insertHyperlink("Aspose Website", "http://www.aspose.com", गलत);
builder.getFont().clearFormatting();
builder.write(" for more information.");

// दस्तावेज़ सहेजें
doc.save("path/to/your/document.docx");
```

## विषय-सूची जोड़ना

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// सामग्री की एक तालिका सम्मिलित करें
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// दस्तावेज़ सामग्री जोड़ें
// ...

// सामग्री तालिका अद्यतन करें
doc.updateFields();

// दस्तावेज़ सहेजें
doc.save("path/to/your/document.docx");
```

## छवियाँ जोड़ना

### इनलाइन छवि

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// एक इनलाइन छवि सम्मिलित करें
builder.insertImage("path/to/your/image.png");

// दस्तावेज़ सहेजें
doc.save("path/to/your/document.docx");
```

### तैरती हुई छवि

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// एक फ़्लोटिंग छवि डालें
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);

// दस्तावेज़ सहेजें
doc.save("path/to/your/document.docx");
```

## पैराग्राफ जोड़ना

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// अनुच्छेद स्वरूपण सेट करें
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// एक अनुच्छेद सम्मिलित करें
builder.writeln("This is a formatted paragraph.");

// दस्तावेज़ सहेजें
doc.save("path/to/your/document.docx");
```

## चरण 10: कर्सर को ले जाना

 आप विभिन्न तरीकों का उपयोग करके दस्तावेज़ के भीतर कर्सर की स्थिति को नियंत्रित कर सकते हैं`moveToParagraph`, `moveToCell`और अधिक। यहाँ एक उदाहरण है:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// कर्सर को किसी विशिष्ट अनुच्छेद पर ले जाएँ
builder.moveToParagraph(2, 0);

// नए कर्सर स्थान पर सामग्री जोड़ें
builder.writeln("This is the 3rd paragraph.");
```

ये कुछ सामान्य ऑपरेशन हैं जिन्हें आप Java के DocumentBuilder के लिए Aspose.Words का उपयोग करके निष्पादित कर सकते हैं। अधिक उन्नत सुविधाओं और अनुकूलन विकल्पों के लिए लाइब्रेरी के दस्तावेज़ों का अन्वेषण करें। दस्तावेज़ निर्माण की शुभकामनाएँ!


## निष्कर्ष

इस व्यापक गाइड में, हमने Word दस्तावेज़ों में विभिन्न प्रकार की सामग्री जोड़ने के लिए Java के DocumentBuilder के लिए Aspose.Words की क्षमताओं का पता लगाया है। हमने टेक्स्ट, टेबल, क्षैतिज नियम, फॉर्म फ़ील्ड, HTML, हाइपरलिंक, सामग्री तालिका, छवियां, पैराग्राफ और कर्सर आंदोलन को कवर किया है।

## अक्सर पूछे जाने वाले प्रश्न

### प्रश्न: जावा के लिए Aspose.Words क्या है?

उत्तर: Aspose.Words for Java एक जावा लाइब्रेरी है जो डेवलपर्स को Microsoft Word दस्तावेज़ों को प्रोग्रामेटिक रूप से बनाने, संशोधित करने और हेरफेर करने की अनुमति देती है। यह दस्तावेज़ निर्माण, स्वरूपण और सामग्री प्रविष्टि के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है।

### प्रश्न: मैं अपने दस्तावेज़ में विषय-सूची कैसे जोड़ सकता हूँ?

उ: सामग्री तालिका जोड़ने के लिए, का उपयोग करें`DocumentBuilder` अपने दस्तावेज़ में सामग्री तालिका फ़ील्ड सम्मिलित करने के लिए। सामग्री तालिका को भरने के लिए सामग्री जोड़ने के बाद दस्तावेज़ में फ़ील्ड को अपडेट करना सुनिश्चित करें। यहाँ एक उदाहरण है:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// सामग्री तालिका फ़ील्ड सम्मिलित करें
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// दस्तावेज़ सामग्री जोड़ें
// ...

// सामग्री तालिका अद्यतन करें
doc.updateFields();
```

### प्रश्न: मैं जावा के लिए Aspose.Words का उपयोग करके दस्तावेज़ में छवियां कैसे सम्मिलित करूं?

 उ: आप इसका उपयोग करके इनलाइन और फ्लोटिंग दोनों प्रकार की छवियां सम्मिलित कर सकते हैं`DocumentBuilder`. यहां दोनों के उदाहरण दिए गए हैं:

#### इनलाइन छवि:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// एक इनलाइन छवि सम्मिलित करें
builder.insertImage("path/to/your/image.png");
```

#### फ़्लोटिंग छवि:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// एक फ़्लोटिंग छवि डालें
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);
```

### प्रश्न: क्या मैं सामग्री जोड़ते समय पाठ और अनुच्छेदों को प्रारूपित कर सकता हूँ?

 उत्तर: हां, आप इसका उपयोग करके टेक्स्ट और पैराग्राफ को प्रारूपित कर सकते हैं`DocumentBuilder`. आप फ़ॉन्ट गुण, पैराग्राफ संरेखण, इंडेंटेशन और बहुत कुछ सेट कर सकते हैं। यहाँ एक उदाहरण है:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// फ़ॉन्ट और पैराग्राफ फ़ॉर्मेटिंग सेट करें
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// एक स्वरूपित अनुच्छेद सम्मिलित करें
builder.writeln("This is a formatted paragraph.");
```

### प्रश्न: मैं दस्तावेज़ के भीतर कर्सर को किसी विशिष्ट स्थान पर कैसे ले जा सकता हूँ?

 उ: आप जैसे तरीकों का उपयोग करके कर्सर की स्थिति को नियंत्रित कर सकते हैं`moveToParagraph`, `moveToCell`और अधिक। यहाँ एक उदाहरण है:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// कर्सर को किसी विशिष्ट अनुच्छेद पर ले जाएँ
builder.moveToParagraph(2, 0);

// नए कर्सर स्थान पर सामग्री जोड़ें
builder.writeln("This is the 3rd paragraph.");
```

Java के DocumentBuilder के लिए Aspose.Words के साथ आरंभ करने में आपकी सहायता के लिए ये कुछ सामान्य प्रश्न और उत्तर हैं। यदि आपके पास अधिक प्रश्न हैं या अतिरिक्त सहायता की आवश्यकता है, तो देखें[पुस्तकालय का दस्तावेज़ीकरण](https://reference.aspose.com/words/java/) या Aspose.Words समुदाय और सहायता संसाधनों से सहायता लें।