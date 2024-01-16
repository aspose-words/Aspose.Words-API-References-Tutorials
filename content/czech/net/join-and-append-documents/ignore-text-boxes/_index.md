---
title: Ignorovat textová pole
linktitle: Ignorovat textová pole
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak připojit dokument a přitom ignorovat formátování textového pole pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/ignore-text-boxes/
---

Tento tutoriál vysvětluje, jak používat Aspose.Words pro .NET k připojení dokumentu při zachování formátování textových polí. Poskytnutý zdrojový kód ukazuje, jak nastavit možnosti formátu importu tak, aby zahrnoval textová pole během procesu přidávání.

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

## Krok 3: Nastavte možnosti formátu importu

 Vytvořte instanci souboru`ImportFormatOptions` třídu a nastavte`IgnoreTextBoxes`majetek do`false`. Tím je zajištěno, že textová pole budou zahrnuta během procesu přidávání při zachování jejich formátování.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## Krok 4: Přidejte obsah textového pole

 Vytvořit`NodeImporter` objekt a použijte jej k importu uzlů textových polí ze zdrojového dokumentu do cílového dokumentu. Iterujte každý odstavec ve zdrojovém dokumentu a importujte jej do cílového dokumentu.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Krok 5: Uložte cílový dokument

 Nakonec uložte upravený cílový dokument pomocí`Save` metoda`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

Tím je dokončena implementace připojení dokumentu při zachování formátování textového pole pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro Ignorovat textová pole pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Při importu ponechte formátování zdrojových textových polí.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```