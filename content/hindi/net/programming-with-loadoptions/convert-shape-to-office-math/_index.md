---
title: आकार को कार्यालय गणित में बदलें
linktitle: आकार को कार्यालय गणित में बदलें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ अपलोड करते समय आकृतियों को Office गणित फ़ार्मुलों में परिवर्तित करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-loadoptions/convert-shape-to-office-math/
---
जब C# एप्लिकेशन में गणित आकृतियों वाले दस्तावेज़ों के साथ वर्ड प्रोसेसिंग होती है, तो आपको बेहतर अनुकूलता और प्रस्तुति के लिए उन्हें ऑफिस गणित फ़ार्मुलों में बदलने की आवश्यकता हो सकती है। .NET के लिए Aspose.Words लाइब्रेरी के साथ, आप दस्तावेज़ लोड करते समय आकृतियों को आसानी से Office गणित फ़ार्मुलों में परिवर्तित कर सकते हैं। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको बताएंगे कि LoadOptions का उपयोग करके आकृतियों को Office गणित फ़ार्मुलों में परिवर्तित करने वाले दस्तावेज़ को लोड करने के लिए .NET C# स्रोत कोड के लिए Aspose.Words का उपयोग कैसे करें।

## Aspose.Words लाइब्रेरी को समझना

कोड में गोता लगाने से पहले, .NET के लिए Aspose.Words लाइब्रेरी को समझना महत्वपूर्ण है। Aspose.Words .NET सहित विभिन्न प्लेटफार्मों में Word दस्तावेज़ों को बनाने, संपादित करने, परिवर्तित करने और सुरक्षित करने के लिए एक शक्तिशाली लाइब्रेरी है। यह दस्तावेज़ों में हेरफेर करने के लिए कई सुविधाएँ प्रदान करता है, जैसे टेक्स्ट सम्मिलित करना, फ़ॉर्मेटिंग बदलना, अनुभाग जोड़ना और बहुत कुछ।

## लोडिंग विकल्प कॉन्फ़िगर करना

पहला कदम हमारे दस्तावेज़ के लिए लोडिंग विकल्पों को कॉन्फ़िगर करना है। लोडिंग पैरामीटर निर्दिष्ट करने के लिए LoadOptions वर्ग का उपयोग करें। हमारे मामले में, हम आकृतियों को Office गणित फ़ार्मुलों में परिवर्तित करना चाहते हैं, इसलिए हमें ConvertShapeToOfficeMath प्रॉपर्टी को सत्य पर सेट करने की आवश्यकता है। यह कैसे करना है यहां बताया गया है:

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };
```

हम एक नया LoadOptions ऑब्जेक्ट बनाते हैं और दस्तावेज़ लोड करते समय आकृतियों को Office गणित फ़ार्मुलों में परिवर्तित करने में सक्षम करने के लिए ConvertShapeToOfficeMath प्रॉपर्टी को सही पर सेट करते हैं।

## आकृतियों को Office गणित फ़ार्मुलों में परिवर्तित करने के साथ दस्तावेज़ लोड हो रहा है

अब जब हमने लोड विकल्प कॉन्फ़िगर कर लिया है, तो हम दस्तावेज़ वर्ग का उपयोग करके दस्तावेज़ लोड कर सकते हैं और लोड विकल्प निर्दिष्ट कर सकते हैं। यहाँ एक उदाहरण है :

```csharp
Document doc = new Document(dataDir + "Office math.docx", loadOptions);
```

इस उदाहरण में, हम निर्दिष्ट लोड विकल्पों का उपयोग करके दस्तावेज़ निर्देशिका में स्थित दस्तावेज़ "Office Math.docx" को लोड करते हैं।

## दस्तावेज़ का पंजीकरण

आकृतियों को Office गणित फ़ार्मुलों में परिवर्तित करने के साथ दस्तावेज़ को लोड करने के बाद, आप दस्तावेज़ वर्ग की सेव विधि का उपयोग करके इसे वांछित प्रारूप में सहेज सकते हैं। उदाहरण के लिए, दस्तावेज़ को .docx प्रारूप में सहेजने के लिए:

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

अपने दस्तावेज़ों में "dataDir" को निर्देशिका पथ से बदलना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके "कन्वर्ट शेप टू ऑफिस मैथ" कार्यक्षमता वाले लोडऑप्शंस के लिए उदाहरण स्रोत कोड

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// "कन्वर्ट शेप" कार्यक्षमता के साथ लोडिंग विकल्पों का कॉन्फ़िगरेशन

  To Office Math"
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };

// दस्तावेज़ को निर्दिष्ट विकल्पों के साथ लोड करें
Document doc = new Document(dataDir + "Office math.docx", loadOptions);

// दस्तावेज़ को वांछित प्रारूप में सहेजें
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

## निष्कर्ष

इस गाइड में, हमने बताया कि .NET के लिए Aspose.Words लाइब्रेरी का उपयोग करके आकृतियों को Office गणित फ़ार्मुलों में परिवर्तित करने वाले दस्तावेज़ को कैसे लोड किया जाए। दिए गए चरणों का पालन करके और दिए गए C# स्रोत कोड का उपयोग करके, आप इस कार्यक्षमता को अपने C# एप्लिकेशन में आसानी से लागू कर सकते हैं। आकृतियों को Office गणित फ़ार्मुलों में परिवर्तित करने से गणित तत्वों वाले दस्तावेज़ों की बेहतर अनुकूलता और प्रस्तुति मिलती है।


### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: आकृतियों को कार्यालय गणित सूत्रों में परिवर्तित करना क्यों आवश्यक है?

उ: C# एप्लिकेशन में Word दस्तावेज़ों के भीतर बेहतर अनुकूलता और गणितीय तत्वों की बेहतर प्रस्तुति के लिए आकृतियों को Office गणित फ़ार्मुलों में परिवर्तित करना आवश्यक है।

#### प्रश्न: क्या Aspose.Words जटिल गणितीय अभिव्यक्तियों को संभाल सकता है?

उत्तर: बिल्कुल! Aspose.Words गणितीय अभिव्यक्तियों और सूत्रों की एक विस्तृत श्रृंखला को संभाल सकता है, जिससे यह जटिल गणितीय सामग्री को भी संसाधित करने के लिए एक उपयुक्त उपकरण बन जाता है।

#### प्रश्न: क्या Aspose.Words केवल .NET प्लेटफ़ॉर्म तक ही सीमित है?

उत्तर: जबकि Aspose.Words .NET के लिए अनुकूलित है, यह जावा और एंड्रॉइड सहित अन्य प्लेटफार्मों के लिए भी समर्थन प्रदान करता है, जो इसे दस्तावेज़ प्रसंस्करण के लिए एक बहुमुखी समाधान बनाता है।

#### प्रश्न: क्या मैं अन्य उद्देश्यों के लिए लोडिंग विकल्पों को अनुकूलित कर सकता हूं?

उत्तर: सचमुच! Aspose.Words विभिन्न लोडिंग विकल्प प्रदान करता है जिन्हें आपकी विशिष्ट आवश्यकताओं के अनुरूप अनुकूलित किया जा सकता है, जिससे आपके एप्लिकेशन में लाइब्रेरी का निर्बाध एकीकरण सुनिश्चित होता है।

#### प्रश्न: क्या Aspose.Words Word के अलावा अन्य दस्तावेज़ प्रारूपों का समर्थन करता है?

उत्तर: हां, Word दस्तावेज़ों के अलावा, Aspose.Words पीडीएफ, HTML, EPUB और अन्य जैसे प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है, जो इसे दस्तावेज़ हेरफेर के लिए एक व्यापक समाधान बनाता है।