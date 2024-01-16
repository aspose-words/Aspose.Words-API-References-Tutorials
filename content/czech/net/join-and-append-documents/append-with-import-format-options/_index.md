---
title: Připojit pomocí možností formátu importu
linktitle: Připojit pomocí možností formátu importu
second_title: Aspose.Words API pro zpracování dokumentů
description: Přečtěte si, jak připojit dokument s možnostmi formátu importu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/append-with-import-format-options/
---

Tento výukový program vysvětluje, jak používat Aspose.Words pro .NET k připojení obsahu jednoho dokumentu k druhému pomocí možností formátu importu. Poskytnutý zdrojový kód ukazuje, jak otevřít zdrojový a cílový dokument, určit volby formátu importu a připojit zdrojový dokument k cílovému dokumentu.

## Krok 1: Nastavte projekt

Ujistěte se, že máte následující předpoklady:

-  Nainstalovaná knihovna Aspose.Words for .NET. Můžete si jej stáhnout z[Aspose.Releases]https://releases.aspose.com/words/net/ nebo k instalaci použijte správce balíčků NuGet.
- Cesta k adresáři dokumentů, kde jsou umístěny zdrojové a cílové dokumenty.

## Krok 2: Otevřete zdrojové a cílové dokumenty

 Otevřete zdrojové a cílové dokumenty pomocí`Document` konstruktor třídy. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Krok 3: Zadejte možnosti formátu importu

 Vytvořte instanci souboru`ImportFormatOptions` třídy k určení možností formátu importu. V tomto příkladu používáme`KeepSourceNumbering` vlastnost, která zajistí, že se použije číslování ze zdrojového dokumentu, pokud dojde ke kolizím s cílovým dokumentem.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Krok 4: Připojte zdrojový dokument k cílovému dokumentu

 Použijte`AppendDocument` způsob cílového dokumentu pro připojení zdrojového dokumentu. Složit`ImportFormatMode.UseDestinationStyles` jako druhý parametr pro použití stylů a formátování cílového dokumentu.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Krok 5: Uložte cílový dokument

 Nakonec uložte upravený cílový dokument pomocí`Save` metoda`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Tím je dokončena implementace připojení dokumentu s možnostmi formátu importu pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro možnosti Append With Import Format Options pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Určete, že pokud se číslování ve zdrojových a cílových dokumentech střetává,
	//pak se použije číslování ze zdrojového dokumentu.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```