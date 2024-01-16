---
title: Udržujte číslování zdrojů
linktitle: Udržujte číslování zdrojů
second_title: Aspose.Words API pro zpracování dokumentů
description: Zjistěte, jak připojit dokument při zachování formátování zdrojového číslování v Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/keep-source-numbering/
---

Tento tutoriál vysvětluje, jak připojit zdrojový dokument k cílovému dokumentu při zachování původního formátování číslování číslovaných odstavců pomocí Aspose.Words for .NET.

## Krok 1: Nastavte projekt

Ujistěte se, že máte následující předpoklady:

-  Nainstalovaná knihovna Aspose.Words for .NET. Můžete si jej stáhnout z[Aspose.Releases]https://releases.aspose.com/words/net/ nebo k instalaci použijte správce balíčků NuGet.
- Cesta k adresáři dokumentů, kam budou uloženy zdrojové a cílové dokumenty.

## Krok 2: Vytvořte cílové a zdrojové dokumenty

 Vytvořit instance`Document` pro cílové a zdrojové dokumenty.

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Krok 3: Při importu ponechte číslování zdrojů

 Chcete-li zachovat formátování číslování číslovaných odstavců ze zdrojového dokumentu, vytvořte instanci`ImportFormatOptions` a nastavit`KeepSourceNumbering` na`true` . Použijte a`NodeImporter` pro import uzlů ze zdrojového dokumentu do cílového dokumentu s uvedením`ImportFormatMode.KeepSourceFormatting` a`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Krok 4: Importujte a přidejte odstavce

Procházejte odstavce ve zdrojovém dokumentu a importujte každý odstavec do cílového dokumentu pomocí`importer`. Připojte importované uzly k tělu cílového dokumentu.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Krok 5: Uložte upravený dokument

 Uložte upravený dokument pomocí`Save` metoda`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

Tím je dokončena implementace připojení zdrojového dokumentu k cílovému dokumentu při zachování původního formátování číslování pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro Keep Source Numbering pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Při importu číslovaných odstavců dodržujte formátování seznamu zdrojů.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```