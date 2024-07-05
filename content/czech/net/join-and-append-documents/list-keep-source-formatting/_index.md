---
title: List Keep Source Formátování
linktitle: List Keep Source Formátování
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak zachovat formátování seznamu při spojování a připojování dokumentů Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/list-keep-source-formatting/
---

Tento tutoriál vás provede procesem používání funkce List Keep Source Formatting aplikace Aspose.Words for .NET. Tato funkce umožňuje spojovat a připojovat dokumenty aplikace Word při zachování zdrojového formátování seznamů.

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

Dále musíte načíst zdrojové a cílové dokumenty pomocí Aspose.Words`Document` třída. Aktualizujte názvy souborů v`Document` konstruktor podle názvů vašich dokumentů.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Krok 3: Nastavte zdrojový dokument na nepřetržitý tok

 Abyste zajistili, že obsah ze zdrojového dokumentu bude po připojení k cílovému dokumentu plynule proudit, musíte nastavit`SectionStart` vlastnost první sekce ve zdrojovém dokumentu na`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Krok 4: Připojte zdrojový dokument k cílovému dokumentu

 Nyní můžete připojit zdrojový dokument k cílovému dokumentu pomocí`AppendDocument` metoda`Document` třída. The`ImportFormatMode.KeepSourceFormatting`Parametr zajišťuje, že během operace připojení bude zachováno zdrojové formátování, včetně formátování seznamů.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 5: Uložte konečný dokument

 Nakonec uložte sloučený dokument s povolenou funkcí List Keep Source Formatting pomocí`Save` metoda`Document` třída.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Příklad zdrojového kódu pro formátování List Keep pomocí Aspose.Words pro .NET 

Zde je úplný zdrojový kód pro funkci List Keep Source Formatting v C# pomocí Aspose.Words pro .NET:

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Připojte obsah dokumentu tak, aby plynule plynul.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

A je to! Úspěšně jste implementovali funkci List Keep Source Formatting pomocí Aspose.Words for .NET. Konečný dokument bude obsahovat sloučený obsah se zachováním formátování seznamu zdrojového dokumentu.