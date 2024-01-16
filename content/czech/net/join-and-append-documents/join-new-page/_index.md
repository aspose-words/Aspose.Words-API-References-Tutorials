---
title: Připojte se na novou stránku
linktitle: Připojte se na novou stránku
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak spojit dva dokumenty na nové stránce při zachování formátování pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/join-new-page/
---

Tento tutoriál vysvětluje, jak spojit dva dokumenty na nové stránce pomocí Aspose.Words for .NET. Poskytnutý zdrojový kód ukazuje, jak připojit dokument na konec jiného dokumentu při spuštění připojeného dokumentu na nové stránce.

## Krok 1: Nastavte projekt

Ujistěte se, že máte následující předpoklady:

-  Nainstalovaná knihovna Aspose.Words for .NET. Můžete si jej stáhnout z[Aspose.Releases]https://releases.aspose.com/words/net/ nebo k instalaci použijte správce balíčků NuGet.
- Cesta k adresáři dokumentů, kde jsou umístěny zdrojové a cílové dokumenty.

## Krok 2: Otevřete zdrojové a cílové dokumenty

 Otevřete zdrojové a cílové dokumenty pomocí`Document` konstruktor třídy. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Krok 3: Nastavte začátek nové sekce stránky

 Chcete-li začít připojený dokument na nové stránce, nastavte`SectionStart` vlastnost první sekce ve zdrojovém dokumentu na`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Krok 4: Připojte zdrojový dokument

 Připojte zdrojový dokument k cílovému dokumentu pomocí`AppendDocument` metoda`Document` třída. Nastavte režim formátu importu na`ImportFormatMode.KeepSourceFormatting` pro zachování původních stylů ze zdrojového dokumentu.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 5: Uložte upravený dokument

 Nakonec uložte upravený cílový dokument pomocí`Save` metoda`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

Tím je dokončena implementace spojení dvou dokumentů na nové stránce pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro Join New Page pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Nastavte připojený dokument tak, aby začínal na nové stránce.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Připojte zdrojový dokument pomocí původních stylů nalezených ve zdrojovém dokumentu.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```