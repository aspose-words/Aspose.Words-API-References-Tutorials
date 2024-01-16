---
title: Ponechat formátování zdroje
linktitle: Ponechat formátování zdroje
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak připojit zdrojový dokument k cílovému dokumentu při zachování původního formátování pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/keep-source-formatting/
---

Tento kurz ukazuje, jak připojit zdrojový dokument k cílovému dokumentu při zachování původního formátování zdrojového dokumentu pomocí Aspose.Words for .NET.

## Krok 1: Nastavte projekt

Ujistěte se, že máte následující předpoklady:

-  Nainstalovaná knihovna Aspose.Words for .NET. Můžete si jej stáhnout z[Aspose.Releases]https://releases.aspose.com/words/net/ nebo k instalaci použijte správce balíčků NuGet.
- Cesta k adresáři dokumentů, kam budou uloženy zdrojové a cílové dokumenty.

## Krok 2: Vytvořte cílové a zdrojové dokumenty

 Vytvořit instance`Document` pro cílové a zdrojové dokumenty.

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## Krok 3: Připojte zdrojový dokument k cílovému dokumentu

 Použijte`AppendDocument` způsob cílového dokumentu pro připojení zdrojového dokumentu. Složit`ImportFormatMode.KeepSourceFormatting` jako režim formátu importu pro zachování původního formátování zdrojového dokumentu.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 4: Uložte upravený dokument

 Uložte upravený dokument pomocí`Save` metoda`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

Tím je dokončena implementace připojení zdrojového dokumentu k cílovému dokumentu při zachování původního formátování pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro formátování formátu Keep pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// Připojte zdrojový dokument k cílovému dokumentu.
	// Předejte režim formátování, aby bylo zachováno původní formátování zdrojového dokumentu při jeho importu.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```