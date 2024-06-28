---
title: Odebrat zápatí zdrojových záhlaví
linktitle: Odebrat zápatí zdrojových záhlaví
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak odstranit záhlaví a zápatí při spojování a připojování dokumentů aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/remove-source-headers-footers/
---

Tento tutoriál vás provede procesem používání funkce Odebrat zdrojová záhlaví zápatí Aspose.Words for .NET. Tato funkce umožňuje spojovat a připojovat dokumenty Wordu a zároveň odstraňovat záhlaví a zápatí ze zdrojového dokumentu.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

1. Aspose.Words for .NET nainstalován. Můžete si jej stáhnout z webu Aspose nebo nainstalovat přes NuGet.
2. Visual Studio nebo jiné vývojové prostředí C#.

## Krok 1: Inicializujte adresáře dokumentů

 Nejprve musíte nastavit cestu k adresáři dokumentů. Upravte hodnotu`dataDir` proměnnou k cestě, kde jsou umístěny vaše dokumenty.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Načtěte zdrojové a cílové dokumenty

Dále musíte načíst zdrojové a cílové dokumenty pomocí Aspose.Words.`Document` třída. Aktualizujte názvy souborů v`Document` konstruktor podle názvů vašich dokumentů.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Krok 3: Odeberte záhlaví a zápatí ze sekcí zdrojového dokumentu

 Chcete-li odstranit záhlaví a zápatí z každého oddílu ve zdrojovém dokumentu, můžete oddíly iterovat pomocí a`foreach` smyčka a zavolejte`ClearHeadersFooters` metoda.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Krok 4: Zakažte nastavení "LinkToPrevious" pro záhlavíZápatí

 po vymazání záhlaví a zápatí ze zdrojového dokumentu existuje možnost, že nastavení "LinkToPrevious" pro`HeadersFooters` lze ještě nastavit. Chcete-li se tomuto chování vyhnout, musíte jej výslovně nastavit`false` pro první oddíl`HeadersFooters` vlastnictví.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Krok 5: Připojte zdrojový dokument k cílovému dokumentu

 Nyní můžete připojit zdrojový dokument k cílovému dokumentu pomocí`AppendDocument` metoda`Document` třída. The`ImportFormatMode.KeepSourceFormatting` Parametr zajišťuje zachování formátování zdroje během operace připojení.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 6: Uložte konečný dokument

 Nakonec uložte sloučený dokument s povolenou funkcí Odebrat zdrojová záhlaví zápatí pomocí`Save` metoda`Document` třída.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Příklad zdrojového kódu pro Odstranit zápatí zdrojových záhlaví pomocí Aspose.Words pro .NET 

Zde je úplný zdrojový kód pro funkci "Odebrat zápatí zdrojových záhlaví" v C# pomocí Aspose.Words pro .NET:


```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Odeberte záhlaví a zápatí z každého oddílu ve zdrojovém dokumentu.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// I poté, co jsou ze zdrojového dokumentu vymazána záhlaví a zápatí, nastavení "LinkToPrevious".
	// pro HeadersFooters lze stále nastavit. To způsobí, že záhlaví a zápatí budou pokračovat z cíle
	// dokument. Toto by mělo být nastaveno na hodnotu false, aby se tomuto chování zabránilo.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
je to! Úspěšně jste implementovali funkci Odebrat zdrojová záhlaví zápatí pomocí Aspose.Words pro .NET. Konečný dokument bude obsahovat sloučený obsah se záhlavím a zápatím odstraněným ze zdrojového dokumentu.