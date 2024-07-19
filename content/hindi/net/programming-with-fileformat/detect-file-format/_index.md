---
title: दस्तावेज़ फ़ाइल स्वरूप का पता लगाएँ
linktitle: दस्तावेज़ फ़ाइल स्वरूप का पता लगाएँ
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ फ़ाइल प्रारूप का पता लगाने के लिए चरण दर चरण गाइड।
type: docs
weight: 10
url: /hi/net/programming-with-fileformat/detect-file-format/
---

यह लेख Aspose.Words for .NET के साथ दस्तावेज़ फ़ाइल प्रारूप पहचान सुविधा का उपयोग करने के तरीके पर चरण-दर-चरण मार्गदर्शिका प्रदान करता है। हम कोड के प्रत्येक भाग को विस्तार से समझाएँगे। इस ट्यूटोरियल के अंत में, आप यह समझ पाएँगे कि विभिन्न दस्तावेज़ फ़ाइलों के प्रारूप का पता कैसे लगाया जाता है।

शुरू करने से पहले, सुनिश्चित करें कि आपने अपने प्रोजेक्ट में Aspose.Words for .NET लाइब्रेरी को इंस्टॉल और कॉन्फ़िगर किया है। आप Aspose वेबसाइट पर लाइब्रेरी और इंस्टॉलेशन निर्देश पा सकते हैं।

## चरण 1: निर्देशिकाएँ परिभाषित करें

 शुरू करने के लिए, आपको उन निर्देशिकाओं को परिभाषित करना होगा जहाँ आप फ़ाइलों को उनके प्रारूप के अनुसार संग्रहीत करना चाहते हैं।`"YOUR DOCUMENT DIRECTORY"`आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ। यदि वे पहले से मौजूद नहीं हैं, तो हम "समर्थित", "अज्ञात", "एन्क्रिप्टेड" और "प्री97" निर्देशिकाएँ बनाते हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// यदि निर्देशिकाएं पहले से मौजूद नहीं हैं तो उन्हें बनाएं।
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

 फिर हम उपयोग करते हैं`GetFiles` की विधि`Directory` निर्दिष्ट निर्देशिका में फ़ाइलों की सूची प्राप्त करने के लिए क्लास। हम एक का भी उपयोग करते हैं`Where` "भ्रष्ट document.docx" नामक एक विशिष्ट फ़ाइल को बाहर करने के लिए खंड।

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## चरण 3: प्रत्येक फ़ाइल का प्रारूप पता करें

 हम सूची में प्रत्येक फ़ाइल के माध्यम से लूप करते हैं और उपयोग करते हैं`DetectFileFormat` की विधि`FileFormatUtil` फ़ाइल के प्रारूप का पता लगाने के लिए क्लास का उपयोग करें। हम पता लगाए गए दस्तावेज़ प्रकार को भी प्रदर्शित करते हैं।

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
// ... अन्य समर्थित दस्तावेज़ स्वरूपों के लिए मामले जोड़ें
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

	// यदि निर्देशिकाएं पहले से मौजूद नहीं हैं तो उन्हें बनाएं।
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

### दस्तावेज़ फ़ाइल प्रारूप पहचान के लिए अक्सर पूछे जाने वाले प्रश्न

#### .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ फ़ाइल के प्रारूप का पता कैसे लगाएं?

 .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ फ़ाइल के प्रारूप का पता लगाने के लिए, आप ट्यूटोरियल में दिए गए चरणों का पालन कर सकते हैं।`DetectFileFormat` की विधि`FileFormatUtil` क्लास आपको दस्तावेज़ फ़ाइल के प्रारूप का पता लगाने की अनुमति देगा। यह आपको यह निर्धारित करने की अनुमति देगा कि यह Microsoft Word 97-2003 दस्तावेज़ है, टेम्पलेट है, Office Open XML WordprocessingML दस्तावेज़ है या अन्य समर्थित प्रारूप है। ट्यूटोरियल में प्रदान किया गया कोड आपको इस सुविधा को लागू करने में मार्गदर्शन करेगा।

#### Aspose.Words for .NET किस दस्तावेज़ प्रारूप का समर्थन करता है?

Aspose.Words for .NET विभिन्न प्रकार के दस्तावेज़ स्वरूपों का समर्थन करता है, जिसमें Microsoft Word 97-2003 दस्तावेज़ (DOC), टेम्पलेट्स (DOT), Office Open XML WordprocessingML दस्तावेज़ (DOCX), Office Open XML WordprocessingML दस्तावेज़ मैक्रोज़ के साथ (DOCM), Office Open XML WordprocessingML टेम्पलेट्स मैक्रोज़ के बिना (DOTX), Office Open XML WordprocessingML टेम्पलेट्स मैक्रोज़ के साथ (DOTM), फ़्लैट OPC दस्तावेज़, RTF दस्तावेज़, Microsoft Word 2003 WordprocessingML दस्तावेज़, HTML दस्तावेज़, MHTML (वेब संग्रह) दस्तावेज़, OpenDocument Text (ODT) दस्तावेज़, OpenDocument Text (OTT) टेम्पलेट्स, MS Word 6 या Word 95 दस्तावेज़, और अज्ञात दस्तावेज़ स्वरूप शामिल हैं।

#### प्रारूप पहचान के दौरान एन्क्रिप्टेड दस्तावेज़ फ़ाइलों को कैसे संभालें?

 किसी दस्तावेज़ फ़ाइल के प्रारूप का पता लगाते समय, आप इसका उपयोग कर सकते हैं`IsEncrypted` की संपत्ति`FileFormatInfo` ऑब्जेक्ट का उपयोग करके जाँच करें कि फ़ाइल एन्क्रिप्टेड है या नहीं। यदि फ़ाइल एन्क्रिप्टेड है, तो आप इस विशिष्ट मामले को संभालने के लिए अतिरिक्त कदम उठा सकते हैं, जैसे कि फ़ाइल को एन्क्रिप्टेड दस्तावेज़ों के लिए समर्पित निर्देशिका में कॉपी करना। आप इसका उपयोग कर सकते हैं`File.Copy` ऐसा करने की विधि.

#### जब किसी दस्तावेज़ का प्रारूप अज्ञात हो तो क्या कार्रवाई की जानी चाहिए?

जब किसी दस्तावेज़ का प्रारूप अज्ञात हो, तो आप इसे अपने आवेदन के लिए विशिष्ट तरीके से संभालने का निर्णय ले सकते हैं। ट्यूटोरियल में दिए गए उदाहरण में, दस्तावेज़ को अज्ञात प्रारूप के दस्तावेज़ों के लिए समर्पित एक विशिष्ट निर्देशिका में कॉपी किया जाता है। आप अपनी विशिष्ट आवश्यकताओं के अनुरूप इस क्रिया को अनुकूलित कर सकते हैं।

#### क्या .NET के लिए Aspose.Words की कोई अन्य विशेषताएं हैं जिनका उपयोग दस्तावेज़ प्रारूप पहचान के साथ किया जा सकता है?

हां, .NET के लिए Aspose.Words Word दस्तावेज़ों को संसाधित करने और उनमें हेरफेर करने के लिए कई अन्य सुविधाएँ प्रदान करता है। उदाहरण के लिए, आप दस्तावेज़ों से टेक्स्ट, छवियाँ या मेटाडेटा निकालने, फ़ॉर्मेटिंग परिवर्तन लागू करने, दस्तावेज़ों को मर्ज करने, दस्तावेज़ों को अलग-अलग फ़ॉर्मेट में बदलने आदि के लिए लाइब्रेरी का उपयोग कर सकते हैं।