---
title: दस्तावेज़ गुण और मेटाडेटा प्रबंधन
linktitle: दस्तावेज़ गुण और मेटाडेटा प्रबंधन
second_title: Aspose.Words Python दस्तावेज़ प्रबंधन API
description: Python के लिए Aspose.Words का उपयोग करके दस्तावेज़ गुणों और मेटाडेटा को प्रबंधित करना सीखें। स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 12
url: /hi/python-net/document-options-and-settings/document-properties-metadata/
---

## दस्तावेज़ गुण और मेटाडेटा का परिचय

दस्तावेज़ गुण और मेटाडेटा इलेक्ट्रॉनिक दस्तावेज़ों के आवश्यक घटक हैं। वे दस्तावेज़ के बारे में महत्वपूर्ण जानकारी प्रदान करते हैं, जैसे लेखकत्व, निर्माण तिथि और कीवर्ड। मेटाडेटा में अतिरिक्त प्रासंगिक जानकारी शामिल हो सकती है, जो दस्तावेज़ वर्गीकरण और खोज में सहायता करती है। Aspose.Words for Python इन पहलुओं को प्रोग्रामेटिक रूप से प्रबंधित करने की प्रक्रिया को सरल बनाता है।

## पायथन के लिए Aspose.Words के साथ शुरुआत करना

इससे पहले कि हम दस्तावेज़ गुणों और मेटाडेटा के प्रबंधन में उतरें, आइए पायथन के लिए Aspose.Words के साथ अपना वातावरण स्थापित करें।

```python
# Install the Aspose.Words for Python package
pip install aspose-words

# Import the necessary classes
import aspose.words as aw
```

## दस्तावेज़ गुण पुनर्प्राप्त करना

आप Aspose.Words API का उपयोग करके दस्तावेज़ गुणों को आसानी से पुनः प्राप्त कर सकते हैं। किसी दस्तावेज़ के लेखक और शीर्षक को पुनः प्राप्त करने का एक उदाहरण यहां दिया गया है:

```python
# Load the document
doc = aw.Document("document.docx")

# Retrieve document properties
author = doc.built_in_document_properties["Author"]
title = doc.built_in_document_properties["Title"]

print("Author:", author)
print("Title:", title)
```

## दस्तावेज़ गुण सेट करना

दस्तावेज़ गुणों को अद्यतन करना बिल्कुल सरल है। मान लीजिए कि आप लेखक का नाम और शीर्षक अपडेट करना चाहते हैं:

```python
# Update document properties
doc.built_in_document_properties["Author"] = "John Doe"
doc.built_in_document_properties["Title"] = "My Updated Document"

# Save the changes
doc.save("updated_document.docx")
```

## कस्टम दस्तावेज़ गुणों के साथ कार्य करना

कस्टम दस्तावेज़ गुण आपको दस्तावेज़ के भीतर अतिरिक्त जानकारी संग्रहीत करने की अनुमति देते हैं। आइए "विभाग" नामक एक कस्टम प्रॉपर्टी जोड़ें:

```python
# Add a custom document property
doc.custom_document_properties.add("Department", "Marketing")

# Save the changes
doc.save("document_with_custom_property.docx")
```

## मेटाडेटा सूचना का प्रबंधन

मेटाडेटा प्रबंधन में ट्रैक परिवर्तन, दस्तावेज़ आँकड़े और बहुत कुछ जैसी जानकारी को नियंत्रित करना शामिल है। Aspose.Words आपको इस मेटाडेटा को प्रोग्रामेटिक रूप से एक्सेस करने और संशोधित करने की सुविधा देता है।

```python
# Access and modify metadata
doc.metadata["Keywords"] = "Python, Aspose.Words, Metadata"
```

## मेटाडेटा अपडेट स्वचालित करना

Aspose.Words का उपयोग करके बार-बार मेटाडेटा अपडेट को स्वचालित किया जा सकता है। उदाहरण के लिए, आप स्वचालित रूप से "अंतिम संशोधित" संपत्ति को अपडेट कर सकते हैं:

```python
# Automatically update "Last Modified By"
doc.built_in_document_properties["LastModifiedBy"] = "Automated Process"
```

## मेटाडेटा में संवेदनशील जानकारी की सुरक्षा करना

मेटाडेटा में कभी-कभी संवेदनशील जानकारी हो सकती है। डेटा गोपनीयता सुनिश्चित करने के लिए, आप विशिष्ट गुण हटा सकते हैं:

```python
# Remove sensitive metadata properties
sensitive_properties = ["LastPrinted", "LastSavedBy"]
for prop in sensitive_properties:
    if prop in doc.built_in_document_properties:
        doc.built_in_document_properties.remove(prop)
```

## दस्तावेज़ संस्करण और इतिहास को संभालना

दस्तावेज़ इतिहास को बनाए रखने के लिए संस्करणीकरण महत्वपूर्ण है। Aspose.Words आपको संस्करणों को प्रभावी ढंग से प्रबंधित करने की अनुमति देता है:

```python
# Add version history information
version_info = doc.built_in_document_properties.add("VersionInfo")
version_info.value = "Version 1.0 - Initial Release"
```

## दस्तावेज़ संपत्ति सर्वोत्तम प्रथाएँ

- दस्तावेज़ गुणों को सटीक और अद्यतन रखें।
- अतिरिक्त संदर्भ के लिए कस्टम गुणों का उपयोग करें।
- मेटाडेटा का नियमित रूप से ऑडिट और अद्यतन करें।
- मेटाडेटा में संवेदनशील जानकारी सुरक्षित रखें.

## निष्कर्ष

दस्तावेज़ के गुणों और मेटाडेटा को प्रभावी ढंग से प्रबंधित करना दस्तावेज़ संगठन और पुनर्प्राप्ति के लिए महत्वपूर्ण है। Aspose.Words for Python इस प्रक्रिया को सुव्यवस्थित करता है, जिससे डेवलपर्स प्रोग्रामेटिक रूप से दस्तावेज़ विशेषताओं में आसानी से हेरफेर और नियंत्रण कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Python के लिए Aspose.Words कैसे स्थापित करूं?

आप निम्नलिखित कमांड का उपयोग करके पायथन के लिए Aspose.Words इंस्टॉल कर सकते हैं:

```python
pip install aspose-words
```

### क्या मैं Aspose.Words का उपयोग करके मेटाडेटा अपडेट स्वचालित कर सकता हूँ?

हां, आप Aspose.Words का उपयोग करके मेटाडेटा अपडेट स्वचालित कर सकते हैं। उदाहरण के लिए, आप स्वचालित रूप से "अंतिम संशोधित द्वारा" संपत्ति को अपडेट कर सकते हैं।

### मैं मेटाडेटा में संवेदनशील जानकारी की सुरक्षा कैसे कर सकता हूँ?

 मेटाडेटा में संवेदनशील जानकारी की सुरक्षा के लिए, आप इसका उपयोग करके विशिष्ट गुणों को हटा सकते हैं`remove` तरीका।

### दस्तावेज़ संपत्तियों के प्रबंधन के लिए कुछ सर्वोत्तम अभ्यास क्या हैं?

- दस्तावेज़ गुणों की सटीकता और मुद्रा सुनिश्चित करें।
- अतिरिक्त संदर्भ के लिए कस्टम गुणों का उपयोग करें।
- मेटाडेटा की नियमित रूप से समीक्षा और अद्यतन करें।
- मेटाडेटा में मौजूद संवेदनशील जानकारी को सुरक्षित रखें।