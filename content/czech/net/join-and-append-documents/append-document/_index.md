---
title: Připojit dokument
linktitle: Připojit dokument
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak připojit obsah jednoho dokumentu k druhému pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/append-document/
---

Tento tutoriál vysvětluje, jak používat Aspose.Words pro .NET k připojení obsahu jednoho dokumentu k druhému. Poskytnutý zdrojový kód ukazuje, jak otevřít zdrojový a cílový dokument, importovat a připojit sekce ze zdrojového dokumentu do cílového dokumentu.

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

## Krok 3: Připojte oddíly ze zdrojového dokumentu do cílového dokumentu

 Projděte všechny sekce ve zdrojovém dokumentu a importujte každou sekci do cílového dokumentu pomocí`ImportNode` metoda. Poté připojte importovanou sekci k cílovému dokumentu.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## Krok 4: Uložte cílový dokument

 Nakonec uložte upravený cílový dokument pomocí`Save` metoda`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

Tím je implementace připojení dokumentu pomocí Aspose.Words for .NET dokončena.

### Příklad zdrojového kódu pro Append Document pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Projděte všechny sekce ve zdrojovém dokumentu.
	//Uzly sekcí jsou bezprostředními potomky uzlu Dokument, takže můžeme dokument pouze vyčíslit.
	foreach (Section srcSection in srcDoc)
	{
		// Protože kopírujeme část z jednoho dokumentu do druhého,
		// je nutné importovat uzel Section do cílového dokumentu.
		// Tím se upraví všechny odkazy specifické pro dokument na styly, seznamy atd.
		//
		// Import uzlu vytvoří kopii původního uzlu, ale kopii
		// ss připraven k vložení do cílového dokumentu.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Nyní lze nový uzel sekce připojit k cílovému dokumentu.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```