---
title: Detecteer het documentbestandsformaat
linktitle: Detecteer het documentbestandsformaat
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het detecteren van documentbestandsindelingen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-fileformat/detect-file-format/
---

Dit artikel biedt een stapsgewijze handleiding voor het gebruik van de functie voor het detecteren van documentbestandsindelingen met Aspose.Words voor .NET. We zullen elk deel van de code in detail uitleggen. Aan het einde van deze zelfstudie begrijpt u hoe u het formaat van verschillende documentbestanden kunt detecteren.

Zorg ervoor dat u, voordat u begint, de Aspose.Words voor .NET-bibliotheek in uw project hebt geïnstalleerd en geconfigureerd. U kunt de bibliotheek en installatie-instructies vinden op de Aspose-website.

## Stap 1: Definieer mappen

 Om te beginnen moet u de mappen definiëren waarin u de bestanden wilt opslaan op basis van hun formaat. Vervangen`"YOUR DOCUMENT DIRECTORY"`met het daadwerkelijke pad naar uw documentenmap. We maken de mappen "Ondersteund", "Onbekend", "Gecodeerd" en "Pre97" aan als deze nog niet bestaan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Maak de mappen als ze nog niet bestaan.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## Stap 2: Blader door bestanden

 Dan gebruiken wij de`GetFiles` werkwijze van de`Directory` class om de lijst met bestanden in de opgegeven map op te halen. Wij gebruiken ook een`Where` clausule om een specifiek bestand met de naam "Beschadigd document.docx" uit te sluiten.

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Stap 3: Detecteer het formaat van elk bestand

 We doorlopen elk bestand in de lijst en gebruiken de`DetectFileFormat` werkwijze van de`FileFormatUtil` klasse om het formaat van het bestand te detecteren. We geven ook het gedetecteerde documenttype weer.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Geef het documenttype weer
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
// ... Voeg cases toe voor andere ondersteunde documentformaten
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

Dat is alles ! U hebt met succes de indeling van verschillende documentbestanden gedetecteerd met Aspose.Words voor .NET.

### Voorbeeldbroncode voor detectie van bestandsindelingen met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Maak de mappen aan als deze nog niet bestaan.
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

		// Geef het documenttype weer
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

### Veelgestelde vragen over detectie van documentbestandsindelingen

#### Hoe kan ik het formaat van een documentbestand detecteren met Aspose.Words voor .NET?

 Om de indeling van een documentbestand te detecteren met Aspose.Words voor .NET, kunt u de stappen in de zelfstudie volgen. De ... gebruiken`DetectFileFormat` werkwijze van de`FileFormatUtil` class kunt u het formaat van het documentbestand detecteren. Hiermee kunt u bepalen of het een Microsoft Word 97-2003-document, een sjabloon, een Office Open XML WordprocessingML-document of een ander ondersteund formaat is. De code in de zelfstudie begeleidt u bij het implementeren van deze functie.

#### Welke documentformaten ondersteunt Aspose.Words voor .NET?

Aspose.Words voor .NET ondersteunt een verscheidenheid aan documentformaten, waaronder Microsoft Word 97-2003-documenten (DOC), sjablonen (DOT), Office Open XML WordprocessingML-documenten (DOCX), Office Open XML WordprocessingML-documenten met macro's (DOCM), Office Open XML WordprocessingML-sjablonen zonder macro's (DOTX), Office Open XML WordprocessingML-sjablonen met macro's (DOTM), Flat OPC-documenten, RTF-documenten, Microsoft Word 2003 WordprocessingML-documenten, HTML-documenten, MHTML-documenten (Webarchief), OpenDocument Text (ODT)-documenten, OpenDocument Text (OTT)-sjablonen, MS Word 6- of Word 95-documenten en onbekende documentformaten.

#### Hoe om te gaan met gecodeerde documentbestanden tijdens formaatdetectie?

 Wanneer u het formaat van een documentbestand detecteert, kunt u de`IsEncrypted` eigendom van de`FileFormatInfo` object om te controleren of het bestand gecodeerd is. Als het bestand is gecodeerd, kunt u aanvullende stappen ondernemen om dit specifieke geval af te handelen, zoals het kopiëren van het bestand naar een map die speciaal is bedoeld voor gecodeerde documenten. U kunt gebruik maken van de`File.Copy` methode om dit te doen.

#### Welke acties moeten worden ondernomen als het formaat van een document onbekend is?

Wanneer het formaat van een document onbekend is, kunt u ervoor kiezen om er op een voor uw toepassing specifieke wijze mee om te gaan. In het voorbeeld in de zelfstudie wordt het document gekopieerd naar een specifieke map die is bestemd voor documenten met een onbekend formaat. U kunt deze actie aanpassen aan uw specifieke behoeften.

#### Zijn er nog andere functies van Aspose.Words voor .NET die kunnen worden gebruikt in combinatie met detectie van documentindelingen?

Ja, Aspose.Words voor .NET biedt vele andere functies voor het verwerken en manipuleren van Word-documenten. U kunt de bibliotheek bijvoorbeeld gebruiken om tekst, afbeeldingen of metagegevens uit documenten te extraheren, opmaakwijzigingen toe te passen, documenten samen te voegen, documenten naar andere indelingen te converteren en meer.