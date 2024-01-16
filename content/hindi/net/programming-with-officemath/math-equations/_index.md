---
title: गणित के समीकरण
linktitle: गणित के समीकरण
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ों में गणित समीकरण जोड़ना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-officemath/math-equations/
---

.NET के लिए Aspose.Words C# एप्लिकेशन में Word दस्तावेज़ बनाने, संपादित करने और हेरफेर करने के लिए एक शक्तिशाली लाइब्रेरी है। Aspose.Words द्वारा दी जाने वाली सुविधाओं में से आपके दस्तावेज़ों में गणितीय समीकरण जोड़ने की संभावना है। इस गाइड में, हम आपको बताएंगे कि Word दस्तावेज़ में गणित समीकरण जोड़ने के लिए .NET के लिए Aspose.Words के C# स्रोत कोड का उपयोग कैसे करें।

## Aspose.Words लाइब्रेरी को समझना

कोड में गोता लगाने से पहले, .NET के लिए Aspose.Words लाइब्रेरी को समझना महत्वपूर्ण है। Aspose.Words एक लोकप्रिय लाइब्रेरी है जो Word दस्तावेज़ों के साथ Word प्रोसेसिंग को आसान और कुशल बनाती है। यह गणितीय समीकरणों के समर्थन सहित Word दस्तावेज़ों को बनाने, संपादित करने और हेरफेर करने के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है।

## Word दस्तावेज़ लोड हो रहा है

पहला कदम उस वर्ड दस्तावेज़ को लोड करना है जिसमें आप गणित समीकरण जोड़ना चाहते हैं। दस्तावेज़ को स्रोत फ़ाइल से लोड करने के लिए दस्तावेज़ वर्ग का उपयोग करें। यहाँ एक उदाहरण है :

```csharp
Document doc = new Document(dataDir + "Office math.docx");
```

इस उदाहरण में, हम दस्तावेज़ निर्देशिका में स्थित "Office Math.docx" दस्तावेज़ लोड कर रहे हैं।

## गणित का समीकरण जोड़ना

एक बार दस्तावेज़ लोड हो जाने पर, आप दस्तावेज़ में OfficeMath तत्व तक पहुंच सकते हैं। निर्दिष्ट इंडेक्स से OfficeMath आइटम प्राप्त करने के लिए दस्तावेज़ वर्ग की GetChild विधि का उपयोग करें। यहाँ एक उदाहरण है :

```csharp
OfficeMath officeMath = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);
```

इस उदाहरण में, हमें दस्तावेज़ में पहला OfficeMath आइटम मिलता है।

## गणित समीकरण गुणों को कॉन्फ़िगर करना

आप OfficeMath ऑब्जेक्ट गुणों का उपयोग करके गणित समीकरण के विभिन्न गुणों को कॉन्फ़िगर कर सकते हैं। उदाहरण के लिए, आप डिस्प्लेटाइप प्रॉपर्टी का उपयोग करके गणित समीकरण का डिस्प्ले प्रकार सेट कर सकते हैं। यहाँ एक उदाहरण है :

```csharp
officeMath.DisplayType = OfficeMathDisplayType.Display;
```

इस उदाहरण में, हमने गणित समीकरण के प्रदर्शन प्रकार को "प्रदर्शन" पर सेट किया है, जिसका अर्थ है कि समीकरण अपनी लाइन पर प्रदर्शित होगा।

इसी तरह, आप जस्टिफिकेशन प्रॉपर्टी का उपयोग करके गणित समीकरण का संरेखण निर्धारित कर सकते हैं। यहाँ एक उदाहरण है :

```csharp
officeMath.Justification = OfficeMathJustification.Left;
```

इस उदाहरण में, हम गणित समीकरण के संरेखण को बाईं ओर सेट करते हैं।

## दस्तावेज़ को गणितीय समीकरण के साथ सहेजना

एक बार जब आप गणितीय समीकरण के गुणों को कॉन्फ़िगर कर लेते हैं, तो आप दस्तावेज़ वर्ग की सेव विधि का उपयोग करके संशोधित दस्तावेज़ को सहेज सकते हैं। यहाँ एक उदाहरण है :

```csharp
doc.Save(dataDir + "WorkingWithOfficeMath.MathEquations.docx

");
```

इस उदाहरण में, हम संशोधित दस्तावेज़ को "WorkingWithOfficeMath.MathEqations.docx" के रूप में सहेजते हैं।

### .NET के लिए Aspose.Words के साथ गणित समीकरणों के लिए उदाहरण स्रोत कोड

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "Office math.docx");

// OfficeMath तत्व प्राप्त करें
OfficeMath officeMath = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);

// गणितीय समीकरण के गुणों को कॉन्फ़िगर करें
officeMath.DisplayType = OfficeMathDisplayType.Display;
officeMath.Justification = OfficeMathJustification.Left;

// दस्तावेज़ को गणितीय समीकरण के साथ सहेजें
doc.Save(dataDir + "WorkingWithOfficeMath.MathEquations.docx");
```

## निष्कर्ष

इस गाइड में, हमने बताया है कि दिए गए C# स्रोत कोड का उपयोग करके किसी Word दस्तावेज़ में गणित समीकरण जोड़ने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें। दिए गए चरणों का पालन करके, आप आसानी से अपने C# एप्लिकेशन में अपने Word दस्तावेज़ों में गणित समीकरण जोड़ सकते हैं। Aspose.Words गणितीय समीकरणों के साथ वर्ड प्रोसेसिंग के लिए जबरदस्त लचीलापन और शक्ति प्रदान करता है, जिससे आप पेशेवर, अच्छी तरह से प्रारूपित दस्तावेज़ बना सकते हैं।