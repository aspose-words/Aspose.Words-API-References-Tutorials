---
title: Rozpoznat formát souboru dokumentu
linktitle: Rozpoznat formát souboru dokumentu
second_title: Aspose.Words API pro zpracování dokumentů
description: Průvodce krok za krokem k detekci formátu souboru dokumentu pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-fileformat/detect-file-format/
---

Tento článek poskytuje krok za krokem průvodce, jak používat funkci zjišťování formátu souboru dokumentu s Aspose.Words pro .NET. Každou část kódu si podrobně vysvětlíme. Na konci tohoto tutoriálu budete schopni porozumět tomu, jak zjistit formát různých souborů dokumentů.

Než začnete, ujistěte se, že jste ve svém projektu nainstalovali a nakonfigurovali knihovnu Aspose.Words for .NET. Knihovnu a pokyny k instalaci najdete na webu Aspose.

## Krok 1: Definujte adresáře

 Chcete-li začít, musíte definovat adresáře, kam chcete soubory ukládat, podle jejich formátu. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů. Vytváříme adresáře "Supported", "Unknown", "Encrypted" a "Pre97", pokud již neexistují.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Vytvořte adresáře, pokud ještě neexistují.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## Krok 2: Procházení souborů

 Poté použijeme`GetFiles` metoda`Directory` třídy, abyste získali seznam souborů v zadaném adresáři. Používáme také a`Where`klauzule k vyloučení konkrétního souboru s názvem "Poškozený dokument.docx".

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Krok 3: Zjistěte formát každého souboru

 Procházíme každý soubor v seznamu a používáme`DetectFileFormat` metoda`FileFormatUtil` třídy pro zjištění formátu souboru. Zobrazíme také detekovaný typ dokumentu.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Zobrazte typ dokumentu
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
// ... Přidat pouzdra pro další podporované formáty dokumentů
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

To je vše ! Pomocí Aspose.Words for .NET jste úspěšně detekovali formát různých souborů dokumentů.

### Příklad zdrojového kódu pro detekci formátu souboru pomocí Aspose.Words pro .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Vytvořte adresáře, pokud ještě neexistují.
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

		// Zobrazte typ dokumentu
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

### Časté dotazy k detekci formátu souboru dokumentu

#### Jak zjistit formát souboru dokumentu pomocí Aspose.Words for .NET?

 Chcete-li zjistit formát souboru dokumentu pomocí Aspose.Words for .NET, můžete postupovat podle kroků uvedených v tutoriálu. Za použití`DetectFileFormat` metoda`FileFormatUtil`class vám umožní zjistit formát souboru dokumentu. To vám umožní určit, zda se jedná o dokument Microsoft Word 97-2003, šablonu, dokument Office Open XML WordprocessingML nebo jiné podporované formáty. Kód uvedený v tutoriálu vás provede implementací této funkce.

#### Jaké formáty dokumentů Aspose.Words for .NET podporuje?

Aspose.Words for .NET podporuje různé formáty dokumentů včetně dokumentů Microsoft Word 97-2003 (DOC), šablon (DOT), dokumentů Office Open XML WordprocessingML (DOCX), Office Open XML WordprocessingML dokumentů s makry (DOCM), Office Open XML WordprocessingML šablony bez maker (DOTX), Office Open XML WordprocessingML šablony s makry (DOTM), ploché OPC dokumenty, RTF dokumenty, Microsoft Word 2003 WordprocessingML dokumenty, HTML dokumenty, MHTML (webový archiv), dokumenty OpenDocument Text (ODT), dokumenty, Šablony OpenDocument Text (OTT), dokumenty MS Word 6 nebo Word 95 a neznámé formáty dokumentů.

#### Jak zacházet se zašifrovanými soubory dokumentů během zjišťování formátu?

 Při zjišťování formátu souboru dokumentu můžete použít`IsEncrypted` vlastnictvím`FileFormatInfo` objekt pro kontrolu, zda je soubor zašifrován. Pokud je soubor zašifrován, můžete podniknout další kroky k řešení tohoto konkrétního případu, jako je zkopírování souboru do adresáře vyhrazeného pro zašifrované dokumenty. Můžete použít`File.Copy` způsob, jak to udělat.

#### Jaká opatření by měla být provedena, když formát dokumentu není znám?

Pokud je formát dokumentu neznámý, můžete se rozhodnout, že s ním naložíte způsobem specifickým pro vaši aplikaci. V příkladu uvedeném v tutoriálu je dokument zkopírován do specifického adresáře věnovaného dokumentům neznámého formátu. Tuto akci můžete přizpůsobit svým konkrétním potřebám.

#### Existují nějaké další funkce Aspose.Words for .NET, které lze použít ve spojení s detekcí formátu dokumentu?

Ano, Aspose.Words for .NET nabízí mnoho dalších funkcí pro zpracování a manipulaci s dokumenty Wordu. Pomocí knihovny můžete například extrahovat text, obrázky nebo metadata z dokumentů, aplikovat změny formátování, slučovat dokumenty, převádět dokumenty do různých formátů a další.