---
title: जावा के लिए Aspose.Words में क्लीनअप विकल्पों का उपयोग करना
linktitle: सफ़ाई विकल्पों का उपयोग करना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा क्लीनअप विकल्पों के लिए Aspose.Words के साथ दस्तावेज़ स्पष्टता बढ़ाएँ। जानें कि खाली पैराग्राफ, अप्रयुक्त क्षेत्र और बहुत कुछ कैसे हटाएं।
type: docs
weight: 10
url: /hi/java/document-manipulation/using-cleanup-options/
---

## जावा के लिए Aspose.Words में क्लीनअप विकल्पों का उपयोग करने का परिचय

इस ट्यूटोरियल में, हम यह पता लगाएंगे कि मेल मर्ज प्रक्रिया के दौरान दस्तावेज़ों में हेरफेर करने और साफ़ करने के लिए जावा के लिए Aspose.Words में क्लीनअप विकल्पों का उपयोग कैसे करें। क्लीनअप विकल्प आपको दस्तावेज़ क्लीनअप के विभिन्न पहलुओं को नियंत्रित करने की अनुमति देते हैं, जैसे खाली पैराग्राफ, अप्रयुक्त क्षेत्रों को हटाना और बहुत कुछ।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Words for Java लाइब्रेरी आपके प्रोजेक्ट में एकीकृत है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/words/java/).

## चरण 1: खाली अनुच्छेदों को हटाना

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// मर्ज फ़ील्ड सम्मिलित करें
FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
mergeFieldOption1.setFieldName("Option_1");
builder.write(" ? ");
FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
mergeFieldOption2.setFieldName("Option_2");

// सफ़ाई विकल्प सेट करें
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);

// विराम चिह्नों के साथ क्लीनअप पैराग्राफ सक्षम करें
doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);

// मेल मर्ज निष्पादित करें
doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });

// दस्तावेज़ सहेजें
doc.save("WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
```

इस उदाहरण में, हम एक नया दस्तावेज़ बनाते हैं, मर्ज फ़ील्ड सम्मिलित करते हैं, और खाली अनुच्छेदों को हटाने के लिए क्लीनअप विकल्प सेट करते हैं। इसके अतिरिक्त, हम विराम चिह्न वाले अनुच्छेदों को हटाने में सक्षम बनाते हैं। मेल मर्ज निष्पादित करने के बाद, दस्तावेज़ को निर्दिष्ट क्लीनअप लागू करके सहेजा जाता है।

## चरण 2: असंबद्ध क्षेत्रों को हटाना

```java
Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
DataSet data = new DataSet();

// अप्रयुक्त क्षेत्रों को हटाने के लिए सफाई विकल्प सेट करें
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);

// क्षेत्रों के साथ मेल मर्ज निष्पादित करें
doc.getMailMerge().executeWithRegions(data);

// दस्तावेज़ सहेजें
doc.save("WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
```

इस उदाहरण में, हम मर्ज क्षेत्रों के साथ एक मौजूदा दस्तावेज़ खोलते हैं, अप्रयुक्त क्षेत्रों को हटाने के लिए सफाई विकल्प सेट करते हैं, और फिर खाली डेटा के साथ मेल मर्ज निष्पादित करते हैं। यह प्रक्रिया दस्तावेज़ से अप्रयुक्त क्षेत्रों को स्वचालित रूप से हटा देती है।

## चरण 3: खाली फ़ील्ड हटाना

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// खाली फ़ील्ड हटाने के लिए क्लीनअप विकल्प सेट करें
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_FIELDS);

// मेल मर्ज निष्पादित करें
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// दस्तावेज़ सहेजें
doc.save("WorkingWithCleanupOptions.RemoveEmptyFields.docx");
```

इस उदाहरण में, हम मर्ज फ़ील्ड के साथ एक दस्तावेज़ खोलते हैं, खाली फ़ील्ड को हटाने के लिए क्लीनअप विकल्प सेट करते हैं, और डेटा के साथ मेल मर्ज निष्पादित करते हैं। मर्ज के बाद, किसी भी खाली फ़ील्ड को दस्तावेज़ से हटा दिया जाएगा।

## चरण 4: अप्रयुक्त फ़ील्ड को हटाना

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// अप्रयुक्त फ़ील्ड को हटाने के लिए क्लीनअप विकल्प सेट करें
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);

// मेल मर्ज निष्पादित करें
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// दस्तावेज़ सहेजें
doc.save("WorkingWithCleanupOptions.RemoveUnusedFields.docx");
```

इस उदाहरण में, हम मर्ज फ़ील्ड के साथ एक दस्तावेज़ खोलते हैं, अप्रयुक्त फ़ील्ड को हटाने के लिए क्लीनअप विकल्प सेट करते हैं, और डेटा के साथ मेल मर्ज निष्पादित करते हैं। विलय के बाद, किसी भी अप्रयुक्त फ़ील्ड को दस्तावेज़ से हटा दिया जाएगा।

## चरण 5: युक्त फ़ील्ड्स को हटाना

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// युक्त फ़ील्ड को हटाने के लिए क्लीनअप विकल्प सेट करें
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);

// मेल मर्ज निष्पादित करें
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// दस्तावेज़ सहेजें
doc.save("WorkingWithCleanupOptions.RemoveContainingFields.docx");
```

इस उदाहरण में, हम मर्ज फ़ील्ड के साथ एक दस्तावेज़ खोलते हैं, युक्त फ़ील्ड को हटाने के लिए क्लीनअप विकल्प सेट करते हैं, और डेटा के साथ मेल मर्ज निष्पादित करते हैं। मर्ज के बाद, फ़ील्ड स्वयं दस्तावेज़ से हटा दी जाएंगी।

## चरण 6: खाली तालिका पंक्तियों को हटाना

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// खाली तालिका पंक्तियों को हटाने के लिए सफाई विकल्प सेट करें
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);

// मेल मर्ज निष्पादित करें
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// दस्तावेज़ सहेजें
doc.save("WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```

इस उदाहरण में, हम एक तालिका के साथ एक दस्तावेज़ खोलते हैं और फ़ील्ड को मर्ज करते हैं, खाली तालिका पंक्तियों को हटाने के लिए क्लीनअप विकल्प सेट करते हैं, और डेटा के साथ मेल मर्ज निष्पादित करते हैं। मर्ज के बाद, दस्तावेज़ से कोई भी खाली तालिका पंक्तियाँ हटा दी जाएंगी।

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि मेल मर्ज प्रक्रिया के दौरान दस्तावेज़ों में हेरफेर करने और साफ़ करने के लिए जावा के लिए Aspose.Words में क्लीनअप विकल्पों का उपयोग कैसे करें। ये विकल्प दस्तावेज़ सफ़ाई पर सूक्ष्म नियंत्रण प्रदान करते हैं, जिससे आप आसानी से परिष्कृत और अनुकूलित दस्तावेज़ बना सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Java के लिए Aspose.Words में क्लीनअप विकल्प क्या हैं?

जावा के लिए Aspose.Words में क्लीनअप विकल्प ऐसी सेटिंग्स हैं जो आपको मेल मर्ज प्रक्रिया के दौरान दस्तावेज़ क्लीनअप के विभिन्न पहलुओं को नियंत्रित करने की अनुमति देती हैं। वे आपको अनावश्यक तत्वों जैसे खाली पैराग्राफ, अप्रयुक्त क्षेत्रों और बहुत कुछ को हटाने में सक्षम बनाते हैं, जिससे यह सुनिश्चित होता है कि आपका अंतिम दस्तावेज़ अच्छी तरह से संरचित और पॉलिश किया गया है।

### मैं अपने दस्तावेज़ से खाली अनुच्छेद कैसे हटा सकता हूँ?

 जावा के लिए Aspose.Words का उपयोग करके अपने दस्तावेज़ से खाली पैराग्राफ हटाने के लिए, आप सेट कर सकते हैं`MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS` सत्य का विकल्प. यह स्वचालित रूप से उन पैराग्राफों को हटा देगा जिनमें कोई सामग्री नहीं है, जिसके परिणामस्वरूप एक स्वच्छ दस्तावेज़ तैयार होगा।

###  का उद्देश्य क्या है`REMOVE_UNUSED_REGIONS` cleanup option?

`MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS` विकल्प का उपयोग किसी दस्तावेज़ में उन क्षेत्रों को हटाने के लिए किया जाता है जिनमें मेल मर्ज प्रक्रिया के दौरान कोई संबंधित डेटा नहीं होता है। यह अप्रयुक्त प्लेसहोल्डर्स से छुटकारा दिलाकर आपके दस्तावेज़ को साफ-सुथरा रखने में मदद करता है।

### क्या मैं जावा के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ से खाली तालिका पंक्तियाँ हटा सकता हूँ?

 हाँ, आप इसे सेट करके किसी दस्तावेज़ से खाली तालिका पंक्तियाँ हटा सकते हैं`MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS`सफ़ाई विकल्प सत्य पर। यह स्वचालित रूप से उन सभी तालिका पंक्तियों को हटा देगा जिनमें डेटा नहीं है, जिससे आपके दस्तावेज़ में एक अच्छी तरह से संरचित तालिका सुनिश्चित होगी।

###  जब मैं सेट करता हूं तो क्या होता है`REMOVE_CONTAINING_FIELDS` option?

 की स्थापना`MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS` विकल्प मेल मर्ज प्रक्रिया के दौरान दस्तावेज़ से उसके पैराग्राफ सहित संपूर्ण मर्ज फ़ील्ड को हटा देगा। यह तब उपयोगी होता है जब आप मर्ज फ़ील्ड और उनसे जुड़े टेक्स्ट को हटाना चाहते हैं।

### मैं अपने दस्तावेज़ से अप्रयुक्त मर्ज फ़ील्ड को कैसे हटा सकता हूँ?

 किसी दस्तावेज़ से अप्रयुक्त मर्ज फ़ील्ड को हटाने के लिए, आप सेट कर सकते हैं`MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS` सत्य का विकल्प. यह स्वचालित रूप से उन मर्ज फ़ील्ड को समाप्त कर देगा जो मेल मर्ज के दौरान पॉप्युलेट नहीं हुए हैं, जिसके परिणामस्वरूप एक साफ़ दस्तावेज़ तैयार होगा।

###  के बीच क्या अंतर है`REMOVE_EMPTY_FIELDS` and `REMOVE_UNUSED_FIELDS` cleanup options?

`REMOVE_EMPTY_FIELDS` विकल्प उन मर्ज फ़ील्ड को हटा देता है जिनमें कोई डेटा नहीं है या मेल मर्ज प्रक्रिया के दौरान खाली हैं। दूसरी ओर,`REMOVE_UNUSED_FIELDS`विकल्प मर्ज फ़ील्ड को हटा देता है जो मर्ज के दौरान डेटा से भरे नहीं होते हैं। उनके बीच का चुनाव इस बात पर निर्भर करता है कि क्या आप बिना किसी सामग्री वाले फ़ील्ड को हटाना चाहते हैं या उन फ़ील्ड को हटाना चाहते हैं जो विशिष्ट मर्ज ऑपरेशन में अप्रयुक्त हैं।

### मैं विराम चिह्नों वाले अनुच्छेदों को हटाने को कैसे सक्षम कर सकता हूं?

 विराम चिह्नों वाले अनुच्छेदों को हटाने में सक्षम करने के लिए, आप सेट कर सकते हैं`cleanupParagraphsWithPunctuationMarks` सही करने का विकल्प और सफ़ाई के लिए विचार किए जाने वाले विराम चिह्नों को निर्दिष्ट करें। यह आपको अनावश्यक विराम चिह्न वाले अनुच्छेदों को हटाकर अधिक परिष्कृत दस्तावेज़ बनाने की अनुमति देता है।

### क्या मैं Java के लिए Aspose.Words में क्लीनअप विकल्पों को अनुकूलित कर सकता हूँ?

हां, आप अपनी विशिष्ट आवश्यकताओं के अनुसार सफाई विकल्पों को अनुकूलित कर सकते हैं। आप चुन सकते हैं कि कौन से क्लीनअप विकल्प लागू करने हैं और उन्हें अपने दस्तावेज़ क्लीनअप आवश्यकताओं के अनुसार कॉन्फ़िगर करें, यह सुनिश्चित करते हुए कि आपका अंतिम दस्तावेज़ आपके वांछित मानकों को पूरा करता है।