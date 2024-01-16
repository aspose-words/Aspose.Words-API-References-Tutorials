---
title: व्हाइटस्पेस के साथ नंबरिंग का पता लगाएं
linktitle: व्हाइटस्पेस के साथ नंबरिंग का पता लगाएं
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words में सफेद रिक्त स्थान के साथ सूची संख्याओं का पता लगाने का तरीका जानें। अपने दस्तावेज़ों की संरचना को आसानी से सुधारें।
type: docs
weight: 10
url: /hi/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
इस ट्यूटोरियल में, हम .NET के लिए Aspose.Words के साथ "सफेद रिक्त स्थान के साथ नंबरिंग का पता लगाना" सुविधा के लिए प्रदान किए गए C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको टेक्स्ट दस्तावेज़ से सूचियों का पता लगाने और बनाने की अनुमति देती है जिसमें सूची संख्याएं और उसके बाद सफेद स्थान होते हैं।

## चरण 1: वातावरण स्थापित करना

शुरू करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.Words के साथ अपना विकास वातावरण स्थापित कर लिया है। सुनिश्चित करें कि आपने आवश्यक संदर्भ जोड़ दिए हैं और उचित नामस्थान आयात कर लिए हैं।

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

इस चरण में, हम एक टेक्स्ट स्ट्रिंग बनाते हैं जो एक टेक्स्ट दस्तावेज़ का अनुकरण करता है जिसमें सफेद रिक्त स्थान के बाद सूची संख्याएं होती हैं। हम अलग-अलग सूची सीमांककों का उपयोग करते हैं जैसे कि अवधि, दायां ब्रैकेट, बुलेट प्रतीक और सफेद स्थान।

## चरण 3: अपलोड विकल्पों को कॉन्फ़िगर करना

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 इस चरण में, हम दस्तावेज़ लोडिंग विकल्पों को कॉन्फ़िगर करते हैं। हम एक नया बनाते हैं`TxtLoadOptions` ऑब्जेक्ट करें और सेट करें`DetectNumberingWithWhitespaces`संपत्ति को`true`. यह Aspose.Words को सूची संख्याओं का पता लगाने की अनुमति देगा, भले ही उनके बाद सफेद रिक्त स्थान हों।

## चरण 4: दस्तावेज़ लोड करना और सहेजना

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 इस चरण में, हम निर्दिष्ट टेक्स्ट स्ट्रिंग और लोड विकल्पों का उपयोग करके दस्तावेज़ को लोड करते हैं। हम एक का उपयोग करते हैं`MemoryStream` टेक्स्ट स्ट्रिंग को मेमोरी स्ट्रीम में बदलने के लिए। फिर हम परिणामी दस्तावेज़ को .docx प्रारूप में सहेजते हैं।

### .NET के लिए Aspose.Words के साथ व्हाइट स्पेस नंबरिंग डिटेक्शन सुविधा के लिए नमूना स्रोत कोड।

```csharp

            
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// भागों के साथ एक स्ट्रिंग के रूप में एक सादा पाठ दस्तावेज़ बनाएं जिसे सूचियों के रूप में समझा जा सके।
// लोड होने पर, पहली तीन सूचियाँ हमेशा Aspose.Words द्वारा पहचानी जाएंगी,
// और लोड करने के बाद उनके लिए सूची ऑब्जेक्ट बनाए जाएंगे।
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
// केवल एक सूची के रूप में पहचाना जाएगा यदि लोडऑप्शन ऑब्जेक्ट में "डिटेक्टनंबरिंगविथव्हाइटस्पेस" सत्य पर सेट है,
// उन पैराग्राफों से बचने के लिए जो संख्याओं से शुरू होते हैं और उन्हें गलती से सूची के रूप में पहचान लिया जाता है।
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// LoadOptions को एक पैरामीटर के रूप में लागू करते हुए दस्तावेज़ को लोड करें और परिणाम को सत्यापित करें।
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

अब आप सफेद रिक्त स्थान के साथ सूची संख्याओं वाले टेक्स्ट दस्तावेज़ को लोड करने के लिए स्रोत कोड चला सकते हैं, फिर पता लगाई गई सूचियों के साथ एक .docx दस्तावेज़ बना सकते हैं। आउटपुट फ़ाइल निर्दिष्ट निर्देशिका में "WorkingWithTxtLoadOptions.डिटेक्टनंबरिंगविथव्हाइटस्पेस.docx" नाम से सहेजी जाएगी।

## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Words में व्हाइटस्पेस नंबरिंग डिटेक्शन फीचर का पता लगाया। हमने सीखा कि टेक्स्ट दस्तावेज़ से सूचियाँ कैसे बनाई जाती हैं जिनमें सूची संख्याएँ और उसके बाद सफ़ेद रिक्त स्थान होते हैं।

यह सुविधा विभिन्न तरीकों से स्वरूपित सूची संख्याओं वाले दस्तावेज़ों को संसाधित करने के लिए बेहद उपयोगी है। उपयुक्त लोडिंग विकल्पों का उपयोग करके, Aspose.Words इन सूची संख्याओं का पता लगाने में सक्षम है, भले ही उनके बाद सफेद रिक्त स्थान हों, और उन्हें अंतिम दस्तावेज़ में संरचित सूचियों में परिवर्तित कर देता है।

इस सुविधा का उपयोग करने से आपका समय बच सकता है और आपकी वर्कफ़्लो दक्षता में सुधार हो सकता है। आप टेक्स्ट दस्तावेज़ों से आसानी से जानकारी निकाल सकते हैं और उन्हें उचित सूचियों के साथ अच्छी तरह से संरचित दस्तावेज़ों में परिवर्तित कर सकते हैं।

वांछित परिणाम प्राप्त करने के लिए लोडिंग विकल्पों पर विचार करना याद रखें, जैसे व्हाइट स्पेस डायलिंग डिटेक्शन को कॉन्फ़िगर करना।

.NET के लिए Aspose.Words दस्तावेज़ हेरफेर और निर्माण के लिए कई उन्नत सुविधाएँ प्रदान करता है। Aspose.Words द्वारा उपलब्ध कराए गए दस्तावेज़ों और उदाहरणों की और खोज करके, आप इस शक्तिशाली लाइब्रेरी की क्षमताओं का पूरी तरह से दोहन करने में सक्षम होंगे।

इसलिए, .NET परियोजनाओं के लिए अपने Aspose.Words में व्हाइटस्पेस नंबरिंग डिटेक्शन को एकीकृत करने में संकोच न करें और अच्छी तरह से संरचित और पठनीय दस्तावेज़ बनाने के लिए इसके लाभों का लाभ उठाएं।

