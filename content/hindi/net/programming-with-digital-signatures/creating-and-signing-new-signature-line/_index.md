---
title: नई सिग्नेचर लाइन बनाना और हस्ताक्षर करना
linktitle: नई सिग्नेचर लाइन बनाना और हस्ताक्षर करना
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में एक नई हस्ताक्षर पंक्ति बनाना और हस्ताक्षर करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ एक नई हस्ताक्षर लाइन सुविधा बनाने और हस्ताक्षर करने के चरणों के बारे में बताएंगे। यह सुविधा आपको Word दस्तावेज़ में एक हस्ताक्षर पंक्ति सम्मिलित करने, कस्टम विकल्प सेट करने और दस्तावेज़ पर हस्ताक्षर करने की अनुमति देती है। नीचे दिए गए चरणों का पालन करें:

## चरण 1: दस्तावेज़ और जेनरेटर बनाना

दस्तावेज़ वर्ग और दस्तावेज़बिल्डर ऑब्जेक्ट का एक उदाहरण बनाकर प्रारंभ करें:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: हस्ताक्षर पंक्ति सम्मिलित करना

दस्तावेज़ में एक नई हस्ताक्षर पंक्ति सम्मिलित करने के लिए DocumentBuilder ऑब्जेक्ट की InsertSignatureLine() विधि का उपयोग करें:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## चरण 3: दस्तावेज़ सहेजें

संशोधित दस्तावेज़ सहेजें:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

दस्तावेज़ को सहेजने के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

## चरण 4: दस्तावेज़ पर हस्ताक्षर करना

दस्तावेज़ पर हस्ताक्षर करने के लिए, आपको हस्ताक्षर विकल्प सेट करने और DigitalSignatureUtil वर्ग का उपयोग करने की आवश्यकता है:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

दस्तावेज़, हस्ताक्षर पंक्ति छवि और हस्ताक्षरित दस्तावेज़ के लिए सही पथ निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके नई सिग्नेचर लाइन बनाने और हस्ताक्षर करने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words के साथ एक नई हस्ताक्षर पंक्ति बनाने और हस्ताक्षर करने के लिए संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

इन चरणों का पालन करके, आप .NET के लिए Aspose.Words के साथ अपने Word दस्तावेज़ में आसानी से एक नई हस्ताक्षर पंक्ति बनाने और हस्ताक्षर करने में सक्षम होंगे।

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में एक नई हस्ताक्षर पंक्ति कैसे बनाएं और हस्ताक्षर करें। दिए गए चरणों का पालन करके, आप आसानी से अपने दस्तावेज़ में एक हस्ताक्षर पंक्ति डाल सकते हैं, इसके विकल्पों को अनुकूलित कर सकते हैं, और डिजिटल प्रमाणपत्र का उपयोग करके दस्तावेज़ पर हस्ताक्षर कर सकते हैं। अपने दस्तावेज़ों में हस्ताक्षर पंक्तियाँ और डिजिटल हस्ताक्षर जोड़ने से उनकी प्रामाणिकता और अखंडता बढ़ती है, जिससे वे अधिक सुरक्षित और भरोसेमंद बन जाते हैं। .NET के लिए Aspose.Words Word दस्तावेज़ों में हस्ताक्षर और डिजिटल प्रमाणपत्रों के साथ Words प्रोसेसिंग के लिए एक शक्तिशाली API प्रदान करता है, जिससे आप हस्ताक्षर प्रक्रिया को स्वचालित कर सकते हैं और अपने दस्तावेज़ों की वैधता सुनिश्चित कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: वर्ड डॉक्यूमेंट में सिग्नेचर लाइन क्या है?

उ: वर्ड दस्तावेज़ में एक हस्ताक्षर पंक्ति एक प्लेसहोल्डर है जो इंगित करती है कि हस्ताक्षर कहाँ रखा जाना चाहिए। इसमें आम तौर पर नाम, शीर्षक और तारीख शामिल होती है, और हस्तलिखित या डिजिटल हस्ताक्षर के लिए स्थान प्रदान किया जाता है।

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में एक हस्ताक्षर पंक्ति कैसे बना सकता हूँ?

उ: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में एक हस्ताक्षर पंक्ति बनाने के लिए, आप इन चरणों का पालन कर सकते हैं:
1.  का एक उदाहरण बनाएं`Document` कक्षा और ए`DocumentBuilder` वस्तु।
2.  उपयोग`InsertSignatureLine` की विधि`DocumentBuilder` दस्तावेज़ में एक नई हस्ताक्षर पंक्ति सम्मिलित करने के लिए ऑब्जेक्ट।
3. संशोधित दस्तावेज़ सहेजें.

#### प्रश्न: क्या मैं हस्ताक्षर पंक्ति विकल्पों, जैसे नाम, शीर्षक और दिनांक को अनुकूलित कर सकता हूँ?

 उ: हाँ, आप हस्ताक्षर पंक्ति विकल्पों को अनुकूलित कर सकते हैं।`SignatureLineOptions` क्लास वांछित विकल्प सेट करने के लिए गुण प्रदान करता है, जैसे`Signer`, `SignerTitle`, `ShowDate`, आदि। आप हस्ताक्षर पंक्ति डालने से पहले इन गुणों को संशोधित कर सकते हैं।

#### प्रश्न: हस्ताक्षर पंक्ति बनाने के बाद मैं दस्तावेज़ पर हस्ताक्षर कैसे कर सकता हूँ?

 उ: हस्ताक्षर पंक्ति बनाने के बाद दस्तावेज़ पर हस्ताक्षर करने के लिए, आपको हस्ताक्षर विकल्प सेट करने और इसका उपयोग करने की आवश्यकता है`DigitalSignatureUtil` कक्षा। यहां चरण दिए गए हैं:
1.  ठीक`SignatureLineId` संपत्ति में`SignOptions` हस्ताक्षर पंक्ति की आईडी पर आपत्ति।
2.  ठीक`SignatureLineImage` संपत्ति में`SignOptions` आप जिस हस्ताक्षर का उपयोग करना चाहते हैं उसकी छवि पर आपत्ति करें।
3.  का उपयोग करके हस्ताक्षर प्रमाणपत्र लोड करें`CertificateHolder` कक्षा।
4.  उपयोग`DigitalSignatureUtil.Sign` आवश्यक पैरामीटर प्रदान करते हुए दस्तावेज़ पर हस्ताक्षर करने की विधि।

#### प्रश्न: क्या मैं दस्तावेज़ पर हस्ताक्षर करने के लिए डिजिटल हस्ताक्षर छवि का उपयोग कर सकता हूँ?

 उ: हाँ, आप दस्तावेज़ पर हस्ताक्षर करने के लिए डिजिटल हस्ताक्षर छवि का उपयोग कर सकते हैं। ऐसा करने के लिए, आपको छवि फ़ाइल प्रदान करनी होगी`SignOptions` ऑब्जेक्ट का उपयोग करना`SignatureLineImage`संपत्ति। छवि किसी भी समर्थित छवि प्रारूप में हो सकती है, जैसे JPEG, PNG, या EMF।

#### प्रश्न: किसी Word दस्तावेज़ में नई हस्ताक्षर पंक्ति बनाने और हस्ताक्षर करने का उद्देश्य क्या है?

उ: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में एक नई हस्ताक्षर पंक्ति बनाना और हस्ताक्षर करना आपको हस्ताक्षर के लिए एक प्लेसहोल्डर जोड़ने और फिर डिजिटल प्रमाणपत्र का उपयोग करके दस्तावेज़ पर हस्ताक्षर करने की अनुमति देता है। यह प्रक्रिया दस्तावेज़ की प्रामाणिकता और अखंडता सुनिश्चित करती है, अनुमोदन या समझौते का प्रमाण प्रदान करती है।

#### प्रश्न: क्या मैं .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में एकाधिक हस्ताक्षर पंक्तियाँ बना और हस्ताक्षर कर सकता हूँ?

उ: हाँ, आप .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में एकाधिक हस्ताक्षर पंक्तियाँ बना और हस्ताक्षर कर सकते हैं। प्रत्येक हस्ताक्षर पंक्ति की अपनी विशिष्ट आईडी और विकल्प हो सकते हैं। आप दस्तावेज़ में अतिरिक्त हस्ताक्षर पंक्तियाँ बनाने और हस्ताक्षर करने के लिए चरणों को दोहरा सकते हैं।

#### प्रश्न: क्या मैं हस्ताक्षर पंक्ति को संशोधित कर सकता हूं या हस्ताक्षर करने के बाद अतिरिक्त जानकारी जोड़ सकता हूं?

उ: एक बार हस्ताक्षर पंक्ति पर हस्ताक्षर हो जाने के बाद, यह दस्तावेज़ की सामग्री का हिस्सा बन जाता है और इसे अलग से संशोधित नहीं किया जा सकता है। हालाँकि, आप हस्ताक्षरित हस्ताक्षर पंक्ति के बाद अतिरिक्त जानकारी या सामग्री जोड़ सकते हैं।

#### प्रश्न: क्या मैं किसी दस्तावेज़ के डिजिटल हस्ताक्षर को सत्यापित कर सकता हूं जिसमें हस्ताक्षर पंक्ति है?

 उ: हाँ, .NET के लिए Aspose.Words एक दस्तावेज़ के डिजिटल हस्ताक्षर को सत्यापित करने के लिए कार्यक्षमता प्रदान करता है जिसमें एक हस्ताक्षर पंक्ति होती है। आप इसका उपयोग कर सकते हैं`DigitalSignatureUtil.Verify` डिजिटल हस्ताक्षर की वैधता और प्रामाणिकता की जांच करने की विधि।

#### प्रश्न: हस्ताक्षर पंक्तियाँ बनाने और हस्ताक्षर करने के लिए Aspose.Words for .NET किस फ़ाइल प्रारूप का समर्थन करता है?

उ: .NET के लिए Aspose.Words DOCX फ़ाइल स्वरूप में हस्ताक्षर पंक्तियाँ बनाने और हस्ताक्षर करने का समर्थन करता है। आप दिए गए तरीकों और कक्षाओं का उपयोग करके DOCX फ़ाइलों में हस्ताक्षर पंक्तियाँ बना और हस्ताक्षर कर सकते हैं।