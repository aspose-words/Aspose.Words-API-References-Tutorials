---
title: Ignorovat záhlaví zápatí
linktitle: Ignorovat záhlaví zápatí
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak připojit dokument a přitom ignorovat obsah záhlaví a zápatí pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/ignore-header-footer/
---

Tento tutoriál vysvětluje, jak používat Aspose.Words pro .NET k připojení dokumentu při ignorování obsahu záhlaví a zápatí. Poskytnutý zdrojový kód ukazuje, jak nastavit možnosti formátu importu pro vyloučení záhlaví a zápatí během procesu přidávání.

## Krok 1: Nastavte projekt

Ujistěte se, že máte následující předpoklady:

-  Nainstalovaná knihovna Aspose.Words for .NET. Můžete si jej stáhnout z[Aspose.Releases]https://releases.aspose.com/words/net/ nebo k instalaci použijte správce balíčků NuGet.
- Cesta k adresáři dokumentů, kde jsou umístěny zdrojové a cílové dokumenty.

## Krok 2: Otevřete zdrojové a cílové dokumenty

 Otevřete zdrojové a cílové dokumenty pomocí`Document` konstruktor třídy. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## Krok 3: Nastavte možnosti formátu importu

 Vytvořte instanci souboru`ImportFormatOptions` třídu a nastavte`IgnoreHeaderFooter`majetek do`false`. To zajistí, že obsah záhlaví a zápatí bude zahrnut během procesu přidávání.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## Krok 4: Připojte zdrojový dokument k cílovému dokumentu

 Použijte`AppendDocument` způsob cílového dokumentu pro připojení zdrojového dokumentu. Složit`ImportFormatMode.KeepSourceFormatting`jako druhý parametr a možnosti formátu importu jako třetí parametr.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Krok 5: Uložte cílový dokument

Nakonec uložte upravený cílový dokument pomocí`Save` metoda`Document` objekt.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

Tím je dokončena implementace připojení dokumentu při ignorování obsahu záhlaví a zápatí pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro Ignorovat záhlaví zápatí pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```