---
title: Zápatí odkazu záhlaví
linktitle: Zápatí odkazu záhlaví
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak propojit záhlaví a zápatí při spojování a připojování dokumentů Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/link-headers-footers/
---

Tento tutoriál vás provede procesem používání funkce Link Headers Footers Aspose.Words for .NET. Tato funkce umožňuje spojit a připojit více dokumentů aplikace Word a zároveň propojit záhlaví a zápatí zdrojového dokumentu s předchozí částí v cílovém dokumentu.

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

## Krok 3: Nastavte připojený dokument tak, aby se objevil na nové stránce

 Chcete-li zajistit, aby se obsah ze zdrojového dokumentu objevil na nové stránce v cílovém dokumentu, musíte nastavit`SectionStart` vlastnost první sekce ve zdrojovém dokumentu na`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Krok 4: Propojte záhlaví a zápatí s předchozí částí

 Chcete-li propojit záhlaví a zápatí zdrojového dokumentu s předchozí sekcí v cílovém dokumentu, můžete použít`LinkToPrevious` metoda`HeadersFooters` sbírka. Míjením`true` jako parametr přepíšete všechna existující záhlaví nebo zápatí ve zdrojovém dokumentu.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Krok 5: Připojte zdrojový dokument k cílovému dokumentu

 Nyní můžete připojit zdrojový dokument k cílovému dokumentu pomocí`AppendDocument` metoda`Document` třída. The`ImportFormatMode.KeepSourceFormatting` Parametr zajišťuje zachování formátování zdroje během operace připojení.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 6: Uložte konečný dokument

 Nakonec uložte sloučený dokument s propojeným záhlavím a zápatím pomocí`Save` metoda`Document` třída.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Příklad zdrojového kódu pro zápatí záhlaví odkazu pomocí Aspose.Words pro .NET 

Zde je úplný zdrojový kód pro funkci "Link Headers Footers" v C# pomocí Aspose.Words pro .NET:


```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Nastavte připojený dokument tak, aby se objevil na nové stránce.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Propojte záhlaví a zápatí ve zdrojovém dokumentu s předchozí částí.
	// Tím přepíšete všechna záhlaví nebo zápatí, která již byla ve zdrojovém dokumentu nalezena.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

je to! Úspěšně jste implementovali funkci Link Headers Footers pomocí Aspose.Words for .NET. Konečný dokument bude obsahovat sloučený obsah se záhlavím a zápatím ze zdrojového dokumentu propojeného s předchozí sekcí v cílovém dokumentu.