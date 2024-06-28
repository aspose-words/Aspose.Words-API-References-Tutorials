---
title: Vložit dokument pomocí Tvůrce
linktitle: Vložit dokument pomocí Tvůrce
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vložit dokument na konec jiného dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/insert-document-with-builder/
---

 Tento tutoriál vysvětluje, jak používat Aspose.Words pro .NET k vložení dokumentu do jiného dokumentu pomocí`DocumentBuilder` třída. Poskytnutý zdrojový kód ukazuje, jak vložit dokument na konec jiného dokumentu při zachování zdrojového formátování.

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

## Krok 3: Inicializujte DocumentBuilder

 Vytvořte novou instanci souboru`DocumentBuilder` třídy a předat cílový dokument jako parametr.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Krok 4: Umístěte DocumentBuilder

Přesuňte`DocumentBuilder` na konec dokumentu pomocí`MoveToDocumentEnd` metoda. Vložením konce stránky oddělíte stávající obsah od vloženého dokumentu.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Krok 5: Vložte zdrojový dokument

 Použijte`InsertDocument` metoda`DocumentBuilder` třídy pro vložení zdrojového dokumentu do cílového dokumentu. Nastavte režim formátu importu na`ImportFormatMode.KeepSourceFormatting` pro zachování formátování zdroje.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 6: Uložte upravený dokument

Nakonec uložte upravený cílový dokument pomocí`Save` metoda`Document` objekt.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Tím je implementace vkládání dokumentu do jiného dokumentu pomocí Aspose.Words for .NET dokončena.

### Příklad zdrojového kódu pro Insert Document With Builder pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```