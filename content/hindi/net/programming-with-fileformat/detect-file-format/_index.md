---
title: दस्तावेज़ फ़ाइल स्वरूप का पता लगाएं
linktitle: दस्तावेज़ फ़ाइल स्वरूप का पता लगाएं
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ फ़ाइल स्वरूप का पता लगाने के लिए चरण दर चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-fileformat/detect-file-format/
---

यह आलेख .NET के लिए Aspose.Words के साथ दस्तावेज़ फ़ाइल प्रारूप पहचान सुविधा का उपयोग करने के तरीके पर चरण-दर-चरण मार्गदर्शिका प्रदान करता है। हम कोड के प्रत्येक भाग को विस्तार से समझाएंगे। इस ट्यूटोरियल के अंत में, आप यह समझ सकेंगे कि विभिन्न दस्तावेज़ फ़ाइलों के प्रारूप का पता कैसे लगाया जाए।

शुरू करने से पहले, सुनिश्चित करें कि आपने अपने प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words को स्थापित और कॉन्फ़िगर किया है। आप Aspose वेबसाइट पर लाइब्रेरी और इंस्टॉलेशन निर्देश पा सकते हैं।

## चरण 1: निर्देशिकाओं को परिभाषित करें

 आरंभ करने के लिए, आपको उन निर्देशिकाओं को परिभाषित करने की आवश्यकता है जहां आप फ़ाइलों को उनके प्रारूप के अनुसार संग्रहीत करना चाहते हैं। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ। हम "समर्थित", "अज्ञात", "एन्क्रिप्टेड" और "प्री97" निर्देशिका बनाते हैं यदि वे पहले से मौजूद नहीं हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// यदि निर्देशिकाएँ पहले से मौजूद नहीं हैं तो बनाएँ।
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## चरण 2: फ़ाइलें ब्राउज़ करें

 फिर हम उपयोग करते हैं`GetFiles` की विधि`Directory` निर्दिष्ट निर्देशिका में फ़ाइलों की सूची प्राप्त करने के लिए क्लास। हम भी a का उपयोग करते हैं`Where`"दूषित दस्तावेज़.docx" नामक एक विशिष्ट फ़ाइल को बाहर करने के लिए खंड।

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## चरण 3: प्रत्येक फ़ाइल के प्रारूप का पता लगाएं

 हम सूची में प्रत्येक फ़ाइल को लूप करते हैं और इसका उपयोग करते हैं`DetectFileFormat` की विधि`FileFormatUtil` फ़ाइल के प्रारूप का पता लगाने के लिए क्लास। हम पता लगाए गए दस्तावेज़ प्रकार को भी प्रदर्शित करते हैं।

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// दस्तावेज़ प्रकार प्रदर्शित करें
switch (info.LoadFormat)
{
LoadFormat.Doc box:
Console.WriteLine("\tDocument Microsoft Word 97-2003.");
break;
LoadFormat.Dot box:
Console.WriteLine("\tMicrosoft Word 97-2003 template.");
break;
LoadFormat.Docx box:
Console.WriteLine("\tDocument Office Open XML WordprocessingML without macros.");
break;
// ... अन्य समर्थित दस्तावेज़ प्रारूपों के लिए मामले जोड़ें
LoadFormat.Unknown case:
Console.WriteLine("\tFormat in

known.");
break;
}

if (info.IsEncrypted)
{
Console.WriteLine("\tAn encrypted document.");
File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
}
else
{
switch (info.LoadFormat)
{
LoadFormat.DocPreWord60 box:
File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
break;
LoadFormat.Unknown case:
File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
break;
default:
File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
break;
}
}
}
```

बस इतना ही ! आपने .NET के लिए Aspose.Words का उपयोग करके विभिन्न दस्तावेज़ फ़ाइलों के प्रारूप का सफलतापूर्वक पता लगा लिया है।

### .NET के लिए Aspose.Words के साथ फ़ाइल प्रारूप का पता लगाने के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// यदि निर्देशिकाएँ पहले से मौजूद नहीं हैं तो बनाएँ।
	if (Directory.Exists(supportedDir) == false)
		Directory.CreateDirectory(supportedDir);
	if (Directory.Exists(unknownDir) == false)
		Directory.CreateDirectory(unknownDir);
	if (Directory.Exists(encryptedDir) == false)
		Directory.CreateDirectory(encryptedDir);
	if (Directory.Exists(pre97Dir) == false)
		Directory.CreateDirectory(pre97Dir);

	
	IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
	
	foreach (string fileName in fileList)
	{
		string nameOnly = Path.GetFileName(fileName);
		
		Console.Write(nameOnly);
		
		FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

		// दस्तावेज़ प्रकार प्रदर्शित करें
		switch (info.LoadFormat)
		{
			case LoadFormat.Doc:
				Console.WriteLine("\tMicrosoft Word 97-2003 document.");
				break;
			case LoadFormat.Dot:
				Console.WriteLine("\tMicrosoft Word 97-2003 template.");
				break;
			case LoadFormat.Docx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
				break;
			case LoadFormat.Docm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
				break;
			case LoadFormat.Dotx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
				break;
			case LoadFormat.Dotm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
				break;
			case LoadFormat.FlatOpc:
				Console.WriteLine("\tFlat OPC document.");
				break;
			case LoadFormat.Rtf:
				Console.WriteLine("\tRTF format.");
				break;
			case LoadFormat.WordML:
				Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
				break;
			case LoadFormat.Html:
				Console.WriteLine("\tHTML format.");
				break;
			case LoadFormat.Mhtml:
				Console.WriteLine("\tMHTML (Web archive) format.");
				break;
			case LoadFormat.Odt:
				Console.WriteLine("\tOpenDocument Text.");
				break;
			case LoadFormat.Ott:
				Console.WriteLine("\tOpenDocument Text Template.");
				break;
			case LoadFormat.DocPreWord60:
				Console.WriteLine("\tMS Word 6 or Word 95 format.");
				break;
			case LoadFormat.Unknown:
				Console.WriteLine("\tUnknown format.");
				break;
		}
		

		if (info.IsEncrypted)
		{
			Console.WriteLine("\tAn encrypted document.");
			File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
		}
		else
		{
			switch (info.LoadFormat)
			{
				case LoadFormat.DocPreWord60:
					File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
					break;
				case LoadFormat.Unknown:
					File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
					break;
				default:
					File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
					break;
			}
		}
	}
	

```

### दस्तावेज़ फ़ाइल स्वरूप का पता लगाने के लिए अक्सर पूछे जाने वाले प्रश्न

#### .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ फ़ाइल के प्रारूप का पता कैसे लगाएं?

 .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ फ़ाइल के प्रारूप का पता लगाने के लिए, आप ट्यूटोरियल में दिए गए चरणों का पालन कर सकते हैं। का उपयोग`DetectFileFormat` की विधि`FileFormatUtil`क्लास आपको दस्तावेज़ फ़ाइल के प्रारूप का पता लगाने की अनुमति देगा। यह आपको यह निर्धारित करने की अनुमति देगा कि क्या यह एक Microsoft Word 97-2003 दस्तावेज़, एक टेम्पलेट, एक Office Open XML WordprocessingML दस्तावेज़, या अन्य समर्थित प्रारूप है। ट्यूटोरियल में दिया गया कोड आपको इस सुविधा को लागू करने में मदद करेगा।

#### .NET के लिए Aspose.Words किस दस्तावेज़ प्रारूप का समर्थन करता है?

.NET के लिए Aspose.Words Microsoft Word 97-2003 दस्तावेज़ (DOC), टेम्प्लेट (DOT), ऑफिस ओपन XML वर्डप्रोसेसिंगML दस्तावेज़ (DOCX), मैक्रोज़ के साथ Office Open मैक्रोज़ के बिना XML वर्डप्रोसेसिंगML टेम्पलेट्स (DOTX), मैक्रोज़ के साथ Office ओपन ओपन डॉक्यूमेंट टेक्स्ट (ओटीटी) टेम्प्लेट, एमएस वर्ड 6 या वर्ड 95 दस्तावेज़, और अज्ञात दस्तावेज़ प्रारूप।

#### प्रारूप पहचान के दौरान एन्क्रिप्टेड दस्तावेज़ फ़ाइलों को कैसे संभालें?

 दस्तावेज़ फ़ाइल के प्रारूप का पता लगाते समय, आप इसका उपयोग कर सकते हैं`IsEncrypted` की संपत्ति`FileFormatInfo` यह जांचने के लिए ऑब्जेक्ट करें कि फ़ाइल एन्क्रिप्टेड है या नहीं। यदि फ़ाइल एन्क्रिप्टेड है, तो आप इस विशिष्ट मामले को संभालने के लिए अतिरिक्त कदम उठा सकते हैं, जैसे फ़ाइल को एन्क्रिप्टेड दस्तावेज़ों के लिए समर्पित निर्देशिका में कॉपी करना। आप इसका उपयोग कर सकते हैं`File.Copy` ऐसा करने की विधि.

#### किसी दस्तावेज़ का प्रारूप अज्ञात होने पर क्या कार्रवाई की जानी चाहिए?

जब किसी दस्तावेज़ का प्रारूप अज्ञात हो, तो आप इसे अपने आवेदन के लिए विशिष्ट तरीके से संभालने का निर्णय ले सकते हैं। ट्यूटोरियल में दिए गए उदाहरण में, दस्तावेज़ को अज्ञात प्रारूप के दस्तावेज़ों को समर्पित एक विशिष्ट निर्देशिका में कॉपी किया गया है। आप अपनी विशिष्ट आवश्यकताओं के अनुरूप इस क्रिया को अनुकूलित कर सकते हैं।

#### क्या .NET के लिए Aspose.Words की कोई अन्य विशेषताएं हैं जिनका उपयोग दस्तावेज़ प्रारूप पहचान के साथ संयोजन में किया जा सकता है?

हाँ, .NET के लिए Aspose.Words Word दस्तावेज़ों के प्रसंस्करण और हेरफेर के लिए कई अन्य सुविधाएँ प्रदान करता है। उदाहरण के लिए, आप लाइब्रेरी का उपयोग दस्तावेज़ों से पाठ, चित्र या मेटाडेटा निकालने, फ़ॉर्मेटिंग परिवर्तन लागू करने, दस्तावेज़ों को मर्ज करने, दस्तावेज़ों को विभिन्न प्रारूपों में परिवर्तित करने और बहुत कुछ करने के लिए कर सकते हैं।