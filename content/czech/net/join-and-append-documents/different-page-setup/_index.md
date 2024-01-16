---
title: Různé nastavení stránky
linktitle: Různé nastavení stránky
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak připojit dokument s různými nastaveními stránky pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/different-page-setup/
---

Tento tutoriál vysvětluje, jak používat Aspose.Words pro .NET k připojení dokumentu s jiným nastavením stránky k jinému dokumentu. Poskytnutý zdrojový kód ukazuje, jak nastavit různá nastavení stránky pro zdrojové a cílové dokumenty a jak zajistit správné pokračování a číslování.

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

## Krok 3: Nastavte nastavení stránky pro zdrojový dokument

 Upravte nastavení stránky zdrojového dokumentu, abyste zajistili správné pokračování a číslování. V tomto příkladu nastavíme začátek sekce na`SectionStart.Continuous` a restartujte číslování stránek. Dbáme také na to, aby šířka, výška a orientace stránky odpovídaly poslední části cílového dokumentu.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Krok 4: Upravte formátování odstavce

 Chcete-li zachovat správné formátování, projděte všechny odstavce ve zdrojovém dokumentu a nastavte`KeepWithNext`majetek do`true`To zajistí, že odstavce zůstanou během procesu přidávání pohromadě.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Krok 5: Připojte zdrojový dokument k cílovému dokumentu

 Použijte`AppendDocument` metoda cílového dokumentu k připojení upraveného zdrojového dokumentu k cílovému dokumentu, přičemž se zachová zdrojové formátování.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 6: Uložte cílový dokument

 Nakonec uložte upravený cílový dokument pomocí`Save` metoda`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Tím je implementace připojení dokumentu s různými nastaveními stránky pomocí Aspose.Words for .NET dokončena.

### Příklad zdrojového kódu pro různé nastavení stránky pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Nastavte zdrojový dokument tak, aby pokračoval přímo po konci cílového dokumentu.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Restartujte číslování stránek na začátku zdrojového dokumentu.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// Abyste zajistili, že se to nestane, když má zdrojový dokument jiné nastavení nastavení stránky, ujistěte se, že
	// nastavení jsou identická pro poslední část cílového dokumentu.
	// Pokud ve zdrojovém dokumentu následují další souvislé části,
	//to bude nutné pro tyto úseky opakovat.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Projděte všechny sekce ve zdrojovém dokumentu.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```