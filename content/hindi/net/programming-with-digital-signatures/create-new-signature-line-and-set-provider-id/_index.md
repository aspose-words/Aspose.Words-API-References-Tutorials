---
title: नई सिग्नेचर लाइन बनाएं और प्रदाता आईडी सेट करें
linktitle: नई सिग्नेचर लाइन बनाएं और प्रदाता आईडी सेट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ Word दस्तावेज़ में एक नई हस्ताक्षर पंक्ति बनाने और प्रदाता आईडी सेट करने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ क्रिएट न्यू सिग्नेचर लाइन और सेट प्रोवाइडर आईडी फीचर का उपयोग करने के चरणों के बारे में बताएंगे। यह सुविधा आपको Word दस्तावेज़ में एक हस्ताक्षर पंक्ति सम्मिलित करने, कस्टम विकल्प सेट करने और दस्तावेज़ पर हस्ताक्षर करने की अनुमति देती है। नीचे दिए गए चरणों का पालन करें:

## चरण 1: दस्तावेज़ और जेनरेटर बनाना

दस्तावेज़ वर्ग और दस्तावेज़बिल्डर ऑब्जेक्ट का एक उदाहरण बनाकर प्रारंभ करें:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: हस्ताक्षर रेखा विकल्प सेट करना

सिग्नेचरलाइनऑप्शन क्लास का एक उदाहरण बनाएं और वांछित विकल्प सेट करें:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## चरण 3: हस्ताक्षर पंक्ति सम्मिलित करना

दस्तावेज़ में हस्ताक्षर पंक्ति सम्मिलित करने के लिए DocumentBuilder ऑब्जेक्ट की InsertSignatureLine() विधि का उपयोग करें:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## चरण 4: प्रदाता आईडी सेट करें

प्रदाता आईडी संपत्ति का उपयोग करके हस्ताक्षर पंक्ति के लिए प्रदाता आईडी सेट करें:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

अपने उपयोग के मामले के लिए सही प्रदाता आईडी निर्दिष्ट करना सुनिश्चित करें।

## चरण 5: दस्तावेज़ सहेजें

संशोधित दस्तावेज़ सहेजें:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

दस्तावेज़ को सहेजने के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

## चरण 6: दस्तावेज़ पर हस्ताक्षर करना

दस्तावेज़ पर हस्ताक्षर करने के लिए, आपको हस्ताक्षर विकल्प सेट करने और DigitalSignatureUtil वर्ग का उपयोग करने की आवश्यकता है:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

दस्तावेज़, प्रमाणपत्र और हस्ताक्षरित दस्तावेज़ के लिए सही पथ निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके नई सिग्नेचर लाइन बनाने और प्रदाता आईडी सेट करने के लिए उदाहरण स्रोत कोड

नई हस्ताक्षर पंक्ति बनाने और .NET के लिए Aspose.Words के साथ प्रदाता आईडी सेट करने के लिए संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

इन चरणों का पालन करके, आप आसानी से एक नई हस्ताक्षर पंक्ति बना सकते हैं और .NET के लिए Aspose.Words के साथ अपने Word दस्तावेज़ में प्रदाता आईडी सेट कर सकते हैं।

## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Words का उपयोग करके एक नई हस्ताक्षर पंक्ति बनाने और Word दस्तावेज़ में प्रदाता आईडी सेट करने की सुविधा का पता लगाया। दिए गए चरणों का पालन करके, आप आसानी से कस्टम विकल्पों के साथ एक हस्ताक्षर पंक्ति सम्मिलित कर सकते हैं और प्रदाता आईडी का उपयोग करके इसे एक विशिष्ट प्रदाता के साथ जोड़ सकते हैं। हस्ताक्षर पंक्तियाँ जोड़ने और प्रदाता जानकारी को अनुकूलित करने से आपके दस्तावेज़ों की प्रामाणिकता और विश्वसनीयता बढ़ती है। .NET के लिए Aspose.Words Word दस्तावेज़ों में हस्ताक्षर लाइनों और डिजिटल प्रमाणपत्रों के साथ Words प्रोसेसिंग के लिए एक शक्तिशाली API प्रदान करता है, जो आपको हस्ताक्षर प्रक्रिया को स्वचालित करने और आपके दस्तावेज़ों की वैधता सुनिश्चित करने में सक्षम बनाता है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: हस्ताक्षर पंक्ति में प्रदाता आईडी क्या है?

उ: हस्ताक्षर पंक्ति में प्रदाता आईडी एक विशिष्ट पहचानकर्ता है जो डिजिटल हस्ताक्षर के प्रदाता का प्रतिनिधित्व करता है। यह हस्ताक्षर के लिए जिम्मेदार स्रोत या संगठन की पहचान करने में मदद करता है।

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में एक नई हस्ताक्षर पंक्ति कैसे बना सकता हूँ?

उ: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में एक नई हस्ताक्षर पंक्ति बनाने के लिए, आप इन चरणों का पालन कर सकते हैं:
1.  का एक उदाहरण बनाएं`Document` कक्षा और ए`DocumentBuilder` वस्तु।
2.  का एक उदाहरण बनाएं`SignatureLineOptions` कक्षा बनाएं और वांछित हस्ताक्षर पंक्ति विकल्प सेट करें।
3.  उपयोग`InsertSignatureLine` की विधि`DocumentBuilder` दस्तावेज़ में हस्ताक्षर पंक्ति सम्मिलित करने के लिए ऑब्जेक्ट।

#### प्रश्न: क्या मैं हस्ताक्षर पंक्ति के विकल्पों को अनुकूलित कर सकता हूँ, जैसे हस्ताक्षरकर्ता का नाम, शीर्षक और निर्देश?

 उ: हाँ, आप हस्ताक्षर पंक्ति के विकल्पों को अनुकूलित कर सकते हैं।`SignatureLineOptions` क्लास वांछित विकल्प सेट करने के लिए गुण प्रदान करता है, जैसे`Signer`, `SignerTitle`, `Instructions`, `AllowComments`, आदि। आप हस्ताक्षर पंक्ति डालने से पहले इन गुणों को संशोधित कर सकते हैं।

#### प्रश्न: हस्ताक्षर पंक्ति के लिए प्रदाता आईडी सेट करने का उद्देश्य क्या है?

उ: हस्ताक्षर पंक्ति के लिए प्रदाता आईडी सेट करने से डिजिटल हस्ताक्षर के लिए जिम्मेदार स्रोत या संगठन की पहचान करने में मदद मिलती है। यह आपको हस्ताक्षर को किसी विशिष्ट प्रदाता या इकाई के साथ जोड़ने की अनुमति देता है, जिससे हस्ताक्षर की उत्पत्ति और विश्वसनीयता के बारे में अतिरिक्त जानकारी मिलती है।

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके हस्ताक्षर पंक्ति के लिए प्रदाता आईडी कैसे सेट कर सकता हूं?

उ: .NET के लिए Aspose.Words का उपयोग करके हस्ताक्षर पंक्ति के लिए प्रदाता आईडी सेट करने के लिए, आप इन चरणों का पालन कर सकते हैं:
1.  सिग्नेचर लाइन डालने के बाद एक्सेस करें`ProviderId` की संपत्ति`SignatureLine` वस्तु।
2.  ठीक`ProviderId` वांछित प्रदाता आईडी मान का उपयोग करके संपत्ति`Guid` डेटा प्रकार।

#### प्रश्न: क्या मैं एक नई हस्ताक्षर पंक्ति बनाने और प्रदाता आईडी सेट करने के बाद दस्तावेज़ पर हस्ताक्षर कर सकता हूँ?

 उ: हाँ, एक नई हस्ताक्षर पंक्ति बनाने और प्रदाता आईडी सेट करने के बाद, आप दस्तावेज़ पर हस्ताक्षर कर सकते हैं। दस्तावेज़ पर हस्ताक्षर करने के लिए, आपको हस्ताक्षर लाइन आईडी, प्रदाता आईडी, टिप्पणियाँ और हस्ताक्षर समय सहित हस्ताक्षर विकल्प सेट करने की आवश्यकता है। फिर, का उपयोग करें`DigitalSignatureUtil.Sign` डिजिटल प्रमाणपत्र का उपयोग करके दस्तावेज़ पर हस्ताक्षर करने की विधि।

#### प्रश्न: क्या मैं Word दस्तावेज़ में प्रत्येक हस्ताक्षर पंक्ति के लिए एक विशिष्ट प्रदाता आईडी निर्दिष्ट कर सकता हूँ?

उ: हाँ, आप किसी Word दस्तावेज़ में प्रत्येक हस्ताक्षर पंक्ति के लिए एक विशिष्ट प्रदाता आईडी निर्दिष्ट कर सकते हैं। प्रत्येक हस्ताक्षर पंक्ति डालने के बाद, आप उस विशेष हस्ताक्षर पंक्ति तक पहुंच कर उसके लिए प्रदाता आईडी सेट कर सकते हैं`ProviderId` संबंधित की संपत्ति`SignatureLine` वस्तु।

#### प्रश्न: नई हस्ताक्षर पंक्ति बनाने और प्रदाता आईडी सेट करने के बाद मैं संशोधित दस्तावेज़ को कैसे सहेज सकता हूँ?

 उ: नई हस्ताक्षर पंक्ति बनाने और प्रदाता आईडी सेट करने के बाद संशोधित दस्तावेज़ को सहेजने के लिए, आप इसका उपयोग कर सकते हैं`Save` की विधि`Document` वस्तु। दस्तावेज़ को सहेजने के लिए सही पथ और फ़ाइल नाम निर्दिष्ट करें।

#### प्रश्न: हस्ताक्षर पंक्तियाँ बनाने और हस्ताक्षर करने के लिए Aspose.Words for .NET किस फ़ाइल प्रारूप का समर्थन करता है?

उ: .NET के लिए Aspose.Words DOCX फ़ाइल स्वरूप में हस्ताक्षर पंक्तियाँ बनाने और हस्ताक्षर करने का समर्थन करता है। आप दिए गए तरीकों और कक्षाओं का उपयोग करके DOCX फ़ाइलों में हस्ताक्षर पंक्तियाँ बना और हस्ताक्षर कर सकते हैं।

#### प्रश्न: क्या मैं हस्ताक्षर करने के बाद प्रदाता आईडी या हस्ताक्षर पंक्ति के अन्य विकल्पों को संशोधित कर सकता हूं?

उ: एक बार हस्ताक्षर पंक्ति पर हस्ताक्षर हो जाने के बाद, यह दस्तावेज़ की सामग्री का हिस्सा बन जाता है और इसे अलग से संशोधित नहीं किया जा सकता है। हस्ताक्षर पंक्ति में कोई भी संशोधन, जैसे प्रदाता आईडी या अन्य विकल्प बदलना, मौजूदा हस्ताक्षर को हटाने और एक नई हस्ताक्षर पंक्ति बनाने की आवश्यकता होगी।