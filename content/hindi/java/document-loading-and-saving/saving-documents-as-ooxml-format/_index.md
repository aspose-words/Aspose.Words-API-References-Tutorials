---
title: जावा के लिए Aspose.Words में दस्तावेज़ों को OOXML प्रारूप के रूप में सहेजना
linktitle: दस्तावेज़ों को OOXML प्रारूप के रूप में सहेजना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words के साथ दस्तावेज़ों को OOXML प्रारूप में सहेजना सीखें। अपनी फ़ाइलों को आसानी से सुरक्षित, अनुकूलित और अनुकूलित करें।
type: docs
weight: 20
url: /hi/java/document-loading-and-saving/saving-documents-as-ooxml-format/
---

## जावा के लिए Aspose.Words में OOXML प्रारूप के रूप में दस्तावेज़ों को सहेजने का परिचय

इस गाइड में, हम यह पता लगाएंगे कि Java के लिए Aspose.Words का उपयोग करके OOXML प्रारूप में दस्तावेज़ों को कैसे सहेजा जाए। OOXML (ऑफिस ओपन XML) एक फ़ाइल स्वरूप है जिसका उपयोग Microsoft Word और अन्य कार्यालय अनुप्रयोगों द्वारा किया जाता है। हम OOXML प्रारूप में दस्तावेज़ों को सहेजने के लिए विभिन्न विकल्पों और सेटिंग्स को कवर करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके प्रोजेक्ट में जावा लाइब्रेरी के लिए Aspose.Words सेटअप है।

## पासवर्ड एन्क्रिप्शन के साथ दस्तावेज़ सहेजना

आप अपने दस्तावेज़ को OOXML प्रारूप में सहेजते समय पासवर्ड से एन्क्रिप्ट कर सकते हैं। यहां बताया गया है कि आप यह कैसे कर सकते हैं:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// दस्तावेज़ लोड करें
Document doc = new Document("Document.docx");

// OoxmlSaveOptions बनाएं और पासवर्ड सेट करें
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setPassword("password");

// दस्तावेज़ को एन्क्रिप्शन के साथ सहेजें
doc.save("EncryptedDoc.docx", saveOptions);
```

## OOXML अनुपालन सेट करना

दस्तावेज़ सहेजते समय आप OOXML अनुपालन स्तर निर्दिष्ट कर सकते हैं। उदाहरण के लिए, आप इसे ISO 29500:2008 (सख्त) पर सेट कर सकते हैं। ऐसे:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.MsWordVersion;
import com.aspose.words.OoxmlCompliance;

// दस्तावेज़ लोड करें
Document doc = new Document("Document.docx");

// वर्ड 2016 के लिए ऑप्टिमाइज़ करें
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);

// OoxmlSaveOptions बनाएं और अनुपालन स्तर सेट करें
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT);

// दस्तावेज़ को अनुपालन सेटिंग के साथ सहेजें
doc.save("ComplianceDoc.docx", saveOptions);
```

## अंतिम सहेजे गए समय की संपत्ति को अद्यतन करना

आप दस्तावेज़ को सहेजते समय उसकी "अंतिम सहेजा गया समय" संपत्ति को अपडेट करना चुन सकते हैं। ऐसे:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// दस्तावेज़ लोड करें
Document doc = new Document("Document.docx");

// OoxmlSaveOptions बनाएं और अंतिम सहेजे गए समय प्रॉपर्टी को अपडेट करने में सक्षम करें
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setUpdateLastSavedTimeProperty(true);

// दस्तावेज़ को अद्यतन संपत्ति के साथ सहेजें
doc.save("UpdatedLastSavedTime.docx", saveOptions);
```

## विरासत नियंत्रण वर्ण रखना

यदि आपके दस्तावेज़ में विरासत नियंत्रण वर्ण हैं, तो आप सहेजते समय उन्हें रखना चुन सकते हैं। ऐसे:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.SaveFormat;

// लीगेसी नियंत्रण वर्णों वाला दस्तावेज़ लोड करें
Document doc = new Document("LegacyControlChars.doc");

//FLAT_OPC प्रारूप के साथ OoxmlSaveOptions बनाएं और विरासत नियंत्रण वर्ण रखने में सक्षम करें
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC);
saveOptions.setKeepLegacyControlChars(true);

// दस्तावेज़ को लीगेसी नियंत्रण वर्णों के साथ सहेजें
doc.save("LegacyControlCharsPreserved.docx", saveOptions);
```

## संपीड़न स्तर निर्धारित करना

दस्तावेज़ सहेजते समय आप संपीड़न स्तर को समायोजित कर सकते हैं। उदाहरण के लिए, आप इसे न्यूनतम संपीड़न के लिए SUPER_FAST पर सेट कर सकते हैं। ऐसे:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.CompressionLevel;

// दस्तावेज़ लोड करें
Document doc = new Document("Document.docx");

// OoxmlSaveOptions बनाएं और संपीड़न स्तर सेट करें
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST);

// दस्तावेज़ को निर्दिष्ट संपीड़न स्तर के साथ सहेजें
doc.save("FastCompressionDoc.docx", saveOptions);
```

ये कुछ प्रमुख विकल्प और सेटिंग्स हैं जिनका उपयोग आप जावा के लिए Aspose.Words का उपयोग करके OOXML प्रारूप में दस्तावेज़ों को सहेजते समय कर सकते हैं। अधिक विकल्पों का पता लगाने और आवश्यकतानुसार अपनी दस्तावेज़-बचत प्रक्रिया को अनुकूलित करने के लिए स्वतंत्र महसूस करें।

## जावा के लिए Aspose.Words में OOXML प्रारूप के रूप में दस्तावेज़ों को सहेजने के लिए पूर्ण स्रोत कोड

```java
public void encryptDocxWithPassword() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setPassword("password"); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
}
@Test
public void ooxmlComplianceIso29500_2008_Strict() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.OoxmlComplianceIso29500_2008_Strict.docx", saveOptions);
}
@Test
public void updateLastSavedTimeProperty() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setUpdateLastSavedTimeProperty(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
}
@Test
public void keepLegacyControlChars() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Legacy control character.doc");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC); { saveOptions.setKeepLegacyControlChars(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
}
@Test
public void setCompressionLevel() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
}
```

## निष्कर्ष

इस व्यापक गाइड में, हमने पता लगाया है कि Java के लिए Aspose.Words का उपयोग करके OOXML प्रारूप में दस्तावेज़ों को कैसे सहेजा जाए। चाहे आपको अपने दस्तावेज़ों को पासवर्ड से एन्क्रिप्ट करने, विशिष्ट OOXML मानकों का अनुपालन सुनिश्चित करने, दस्तावेज़ गुणों को अपडेट करने, विरासत नियंत्रण वर्णों को संरक्षित करने, या संपीड़न स्तरों को समायोजित करने की आवश्यकता हो, Aspose.Words आपकी आवश्यकताओं को पूरा करने के लिए उपकरणों का एक बहुमुखी सेट प्रदान करता है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं पासवर्ड-सुरक्षित दस्तावेज़ से पासवर्ड सुरक्षा कैसे हटाऊं?

पासवर्ड-सुरक्षित दस्तावेज़ से पासवर्ड सुरक्षा हटाने के लिए, आप दस्तावेज़ को सही पासवर्ड के साथ खोल सकते हैं और फिर सेव विकल्पों में पासवर्ड निर्दिष्ट किए बिना इसे सहेज सकते हैं। इससे दस्तावेज़ बिना पासवर्ड सुरक्षा के सहेजा जाएगा।

### क्या मैं किसी दस्तावेज़ को OOXML प्रारूप में सहेजते समय कस्टम गुण सेट कर सकता हूँ?

 हाँ, आप किसी दस्तावेज़ को OOXML प्रारूप में सहेजने से पहले उसके लिए कस्टम गुण सेट कर सकते हैं। उपयोग`BuiltInDocumentProperties` और`CustomDocumentProperties` लेखक, शीर्षक, कीवर्ड और कस्टम गुण जैसे विभिन्न गुणों को सेट करने के लिए कक्षाएं।

### किसी दस्तावेज़ को OOXML प्रारूप में सहेजते समय डिफ़ॉल्ट संपीड़न स्तर क्या है?

 जावा के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को OOXML प्रारूप में सहेजते समय डिफ़ॉल्ट संपीड़न स्तर है`NORMAL` . आप संपीड़न स्तर को बदल सकते हैं`SUPER_FAST` या`MAXIMUM` जरुरत के अनुसार।