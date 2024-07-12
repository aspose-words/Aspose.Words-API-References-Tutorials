---
title: Upptäck dokumentfilformat
linktitle: Upptäck dokumentfilformat
second_title: Aspose.Words Document Processing API
description: Steg för steg guide för att upptäcka dokumentfilformat med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-fileformat/detect-file-format/
---

Den här artikeln ger en steg-för-steg-guide om hur du använder funktionen för identifiering av dokumentfilformat med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av den här handledningen kommer du att kunna förstå hur du upptäcker formatet för olika dokumentfiler.

Innan du börjar, se till att du har installerat och konfigurerat Aspose.Words for .NET-biblioteket i ditt projekt. Du hittar biblioteket och installationsinstruktioner på Asposes webbplats.

## Steg 1: Definiera kataloger

 För att börja måste du definiera katalogerna där du vill lagra filerna enligt deras format. Byta ut`"YOUR DOCUMENT DIRECTORY"`med den faktiska sökvägen till din dokumentkatalog. Vi skapar katalogerna "Supported", "Okänd", "Encrypted" och "Pre97" om de inte redan finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Skapa katalogerna om de inte redan finns.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## Steg 2: Bläddra bland filer

 Då använder vi`GetFiles` metod för`Directory` klass för att få listan över filer i den angivna katalogen. Vi använder också en`Where` klausul för att utesluta en specifik fil med namnet "Corrupted document.docx".

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Steg 3: Upptäck formatet för varje fil

 Vi går igenom varje fil i listan och använder`DetectFileFormat` metod för`FileFormatUtil` klass för att upptäcka filformatet. Vi visar också den upptäckta dokumenttypen.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Visa dokumenttypen
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
// ... Lägg till fall för andra dokumentformat som stöds
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

Det är allt ! Du har framgångsrikt upptäckt formatet för olika dokumentfiler med Aspose.Words för .NET.

### Exempel på källkod för filformatsdetektering med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Skapa katalogerna om de inte redan finns.
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

		// Visa dokumenttypen
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

### Vanliga frågor för identifiering av dokumentfilformat

#### Hur upptäcker man formatet på en dokumentfil med Aspose.Words för .NET?

 För att upptäcka formatet på en dokumentfil med Aspose.Words för .NET kan du följa stegen i handledningen. Använda`DetectFileFormat` metod för`FileFormatUtil` class låter dig upptäcka formatet på dokumentfilen. Detta gör att du kan avgöra om det är ett Microsoft Word 97-2003-dokument, en mall, ett Office Open XML WordprocessingML-dokument eller andra format som stöds. Koden som tillhandahålls i handledningen hjälper dig att implementera den här funktionen.

#### Vilka dokumentformat stöder Aspose.Words för .NET?

Aspose.Words för .NET stöder en mängd olika dokumentformat inklusive Microsoft Word 97-2003-dokument (DOC), Mallar (DOT), Office Open XML WordprocessingML-dokument (DOCX), Office Open XML WordprocessingML-dokument med makron (DOCM), Office Open XML WordprocessingML-mallar utan makron (DOTX), Office Open XML WordprocessingML-mallar med makron (DOTM), Flat OPC-dokument, RTF-dokument, Microsoft Word 2003 WordprocessingML-dokument, HTML-dokument, MHTML (webbarkiv)-dokument, OpenDocument Text (ODT)-dokument, OpenDocument Text-mallar (OTT), MS Word 6- eller Word 95-dokument och okända dokumentformat.

#### Hur hanterar man krypterade dokumentfiler under formatdetektering?

 När du upptäcker formatet för en dokumentfil kan du använda`IsEncrypted` egendom av`FileFormatInfo` objekt för att kontrollera om filen är krypterad. Om filen är krypterad kan du vidta ytterligare åtgärder för att hantera det här specifika fallet, som att kopiera filen till en katalog avsedd för krypterade dokument. Du kan använda`File.Copy` metod för att göra detta.

#### Vilka åtgärder bör vidtas när formatet på ett dokument är okänt?

När formatet på ett dokument är okänt kan du bestämma dig för att hantera det på ett sätt som är specifikt för din ansökan. I exemplet i handledningen kopieras dokumentet till en specifik katalog dedikerad till dokument av okänt format. Du kan anpassa denna åtgärd för att passa dina specifika behov.

#### Finns det några andra funktioner i Aspose.Words för .NET som kan användas i samband med identifiering av dokumentformat?

Ja, Aspose.Words för .NET erbjuder många andra funktioner för att bearbeta och manipulera Word-dokument. Du kan till exempel använda biblioteket för att extrahera text, bilder eller metadata från dokument, tillämpa formateringsändringar, slå samman dokument, konvertera dokument till olika format och mer.