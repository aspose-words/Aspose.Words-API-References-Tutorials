---
title: रिक्त स्थानों के साथ क्रमांकन का पता लगाना
linktitle: रिक्त स्थानों के साथ क्रमांकन का पता लगाना
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: Aspose.Words for .NET में रिक्त स्थान वाली सूची संख्याओं का पता लगाना सीखें। आसानी से अपने दस्तावेज़ों की संरचना में सुधार करें।
type: docs
weight: 10
url: /hi/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
इस ट्यूटोरियल में, हम .NET के लिए Aspose.Words के साथ "सफेद रिक्त स्थान के साथ नंबरिंग का पता लगाना" सुविधा के लिए प्रदान किए गए C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको सफेद रिक्त स्थान के बाद सूची संख्याओं वाले टेक्स्ट दस्तावेज़ से सूचियों का पता लगाने और बनाने की अनुमति देती है।

## चरण 1: वातावरण की स्थापना

आरंभ करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.Words के साथ अपना विकास वातावरण सेट अप कर लिया है। सुनिश्चित करें कि आपने आवश्यक संदर्भ जोड़ दिए हैं और उचित नामस्थान आयात कर लिए हैं।

## चरण 2: टेक्स्ट दस्तावेज़ बनाना

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

इस चरण में, हम एक टेक्स्ट स्ट्रिंग बनाते हैं जो एक टेक्स्ट दस्तावेज़ की तरह दिखता है जिसमें सूची संख्याएँ होती हैं और उसके बाद रिक्त स्थान होते हैं। हम अलग-अलग सूची सीमांकक जैसे कि अवधि, दायाँ कोष्ठक, बुलेट प्रतीक और रिक्त स्थान का उपयोग करते हैं।

## चरण 3: अपलोड विकल्प कॉन्फ़िगर करना

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 इस चरण में, हम दस्तावेज़ लोडिंग विकल्पों को कॉन्फ़िगर करते हैं। हम एक नया दस्तावेज़ बनाते हैं।`TxtLoadOptions` ऑब्जेक्ट और सेट करें`DetectNumberingWithWhitespaces`संपत्ति को`true`इससे Aspose.Words को सूची संख्याओं का पता लगाने की अनुमति मिलेगी, भले ही उनके बाद रिक्त स्थान हों।

## चरण 4: दस्तावेज़ लोड करना और सहेजना

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 इस चरण में, हम निर्दिष्ट टेक्स्ट स्ट्रिंग और लोड विकल्पों का उपयोग करके दस्तावेज़ लोड करते हैं।`MemoryStream` टेक्स्ट स्ट्रिंग को मेमोरी स्ट्रीम में बदलने के लिए। फिर हम परिणामी दस्तावेज़ को .docx प्रारूप में सहेजते हैं।

### .NET के लिए Aspose.Words के साथ व्हाइट स्पेस नंबरिंग डिटेक्शन सुविधा के लिए नमूना स्रोत कोड।

```csharp

            
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// स्ट्रिंग के रूप में एक सादा पाठ दस्तावेज़ बनाएं, जिसके कुछ भागों को सूचियों के रूप में समझा जा सके।
// लोड होने पर, पहली तीन सूचियाँ हमेशा Aspose.Words द्वारा पहचानी जाएंगी,
// और लोड होने के बाद उनके लिए सूची ऑब्जेक्ट बनाए जाएंगे।
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// चौथी सूची, सूची संख्या और सूची आइटम सामग्री के बीच रिक्त स्थान के साथ,
// केवल तभी सूची के रूप में पहचाना जाएगा जब LoadOptions ऑब्जेक्ट में "DetectNumberingWithWhitespaces" को true पर सेट किया गया हो,
// ताकि संख्याओं से शुरू होने वाले पैराग्राफ को गलती से सूची समझे जाने से बचाया जा सके।
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// LoadOptions को पैरामीटर के रूप में लागू करते हुए दस्तावेज़ लोड करें और परिणाम सत्यापित करें।
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

अब आप स्रोत कोड चलाकर रिक्त स्थान के साथ सूची संख्या वाले टेक्स्ट दस्तावेज़ को लोड कर सकते हैं, फिर पता लगाई गई सूचियों के साथ एक .docx दस्तावेज़ बना सकते हैं। आउटपुट फ़ाइल निर्दिष्ट निर्देशिका में "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx" नाम से सहेजी जाएगी।

## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Words में रिक्त स्थान क्रमांकन पहचान सुविधा का पता लगाया। हमने सीखा कि रिक्त स्थान के बाद सूची संख्या वाले टेक्स्ट दस्तावेज़ से सूचियाँ कैसे बनाई जाती हैं।

यह सुविधा अलग-अलग तरीकों से स्वरूपित सूची संख्याओं वाले दस्तावेज़ों को संसाधित करने के लिए अत्यंत उपयोगी है। उचित लोडिंग विकल्पों का उपयोग करके, Aspose.Words इन सूची संख्याओं का पता लगाने में सक्षम है, भले ही उनके बाद रिक्त स्थान हों, और उन्हें अंतिम दस्तावेज़ में संरचित सूचियों में परिवर्तित कर देता है।

इस सुविधा का उपयोग करके आप अपना समय बचा सकते हैं और अपने वर्कफ़्लो दक्षता में सुधार कर सकते हैं। आप आसानी से टेक्स्ट दस्तावेज़ों से जानकारी निकाल सकते हैं और उन्हें उचित सूचियों के साथ अच्छी तरह से संरचित दस्तावेज़ों में परिवर्तित कर सकते हैं।

वांछित परिणाम प्राप्त करने के लिए लोडिंग विकल्पों पर विचार करना याद रखें, जैसे कि रिक्त स्थान डायलिंग पहचान को कॉन्फ़िगर करना।

Aspose.Words for .NET दस्तावेज़ हेरफेर और निर्माण के लिए कई उन्नत सुविधाएँ प्रदान करता है। Aspose.Words द्वारा प्रदान किए गए दस्तावेज़ों और उदाहरणों की और खोज करके, आप इस शक्तिशाली लाइब्रेरी की क्षमताओं का पूरी तरह से दोहन करने में सक्षम होंगे।

इसलिए, अपने Aspose.Words for .NET प्रोजेक्ट्स में रिक्त स्थान क्रमांकन पहचान को एकीकृत करने में संकोच न करें और अच्छी तरह से संरचित और पठनीय दस्तावेज़ बनाने के लिए इसके लाभों का लाभ उठाएं।


