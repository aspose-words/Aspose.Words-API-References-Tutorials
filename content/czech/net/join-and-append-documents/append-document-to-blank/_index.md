---
title: Připojit dokument k prázdnému
linktitle: Připojit dokument k prázdnému
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak připojit dokument k prázdnému cílovému dokumentu v Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/append-document-to-blank/
---

Tento tutoriál vysvětluje, jak používat Aspose.Words pro .NET k připojení obsahu jednoho dokumentu k prázdnému cílovému dokumentu. Poskytnutý zdrojový kód ukazuje, jak vytvořit nový dokument, odstranit jeho obsah a poté k němu připojit zdrojový dokument.

## Krok 1: Nastavte projekt

Ujistěte se, že máte následující předpoklady:

-  Nainstalovaná knihovna Aspose.Words for .NET. Můžete si jej stáhnout z[Aspose.Releases]https://releases.aspose.com/words/net/ nebo k instalaci použijte správce balíčků NuGet.
- Cesta k adresáři dokumentů, kde jsou umístěny zdrojové a cílové dokumenty.

## Krok 2: Vytvořte nový cílový dokument

 Vytvoř nový`Document` objekt pro cílový dokument.

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Krok 3: Odstraňte existující obsah z cílového dokumentu

 Chcete-li zajistit čistý cílový dokument, odstraňte z dokumentu veškerý existující obsah pomocí`RemoveAllChildren` metoda.

```csharp
dstDoc.RemoveAllChildren();
```

## Krok 4: Připojte zdrojový dokument k cílovému dokumentu

 Připojte obsah zdrojového dokumentu k cílovému dokumentu pomocí`AppendDocument` metoda s`ImportFormatMode.KeepSourceFormatting` volba.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 5: Uložte cílový dokument

Nakonec uložte upravený cílový dokument pomocí`Save` metoda`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

Tím je implementace připojení dokumentu k prázdnému cílovému dokumentu pomocí Aspose.Words for .NET dokončena.

### Příklad zdrojového kódu pro Append Document To Blank pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// Cílový dokument není prázdný, což často způsobuje, že se před připojeným dokumentem objeví prázdná stránka.
	// To je způsobeno tím, že základní dokument má prázdnou sekci a nový dokument je spuštěn na další stránce.
	// Před připojením odstraňte veškerý obsah z cílového dokumentu.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```