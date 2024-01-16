---
title: Udržujte zdroj pohromadě
linktitle: Udržujte zdroj pohromadě
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat Aspose.Words for .NET ke spojování a připojování dokumentů aplikace Word a zároveň zachovat zdrojový obsah společně s cílovým dokumentem.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/keep-source-together/
---

Tento tutoriál vás provede procesem používání funkce Keep Source Together aplikace Aspose.Words for .NET. Tato funkce umožňuje spojit a připojit více dokumentů aplikace Word a zároveň zachovat obsah zdrojového dokumentu společně s obsahem cílového dokumentu. 

## Předpoklady

Než začnete, ujistěte se, že máte následující:

1. Aspose.Words for .NET nainstalován. Můžete si jej stáhnout z webu Aspose nebo nainstalovat přes NuGet.
2. Visual Studio nebo jiné vývojové prostředí C#.

## Krok 1: Inicializujte adresáře dokumentů

 Nejprve musíte nastavit cestu k adresáři dokumentů. Upravte hodnotu`dataDir` proměnnou k cestě, kde jsou umístěny vaše dokumenty.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Načtěte zdrojové a cílové dokumenty

 Dále musíte načíst zdrojové a cílové dokumenty pomocí Aspose.Words`Document` třída. Aktualizujte názvy souborů v`Document` konstruktor podle názvů vašich dokumentů.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Krok 3: Nastavte zdrojový dokument tak, aby se objevil po obsahu cílového dokumentu

 Chcete-li zajistit, aby se zdrojový dokument objevil bezprostředně po obsahu cílového dokumentu, musíte nastavit`SectionStart` vlastnost první sekce ve zdrojovém dokumentu na`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Krok 4: Nastavte formátování odstavce "Keep with Next" pro zdrojový dokument

Chcete-li zachovat odstavce ve zdrojovém dokumentu pohromadě, můžete iterovat každý odstavec v dokumentu a nastavit`KeepWithNext`majetek do`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Krok 5: Připojte zdrojový dokument k cílovému dokumentu

 Nyní můžete připojit zdrojový dokument k cílovému dokumentu pomocí`AppendDocument` metoda`Document` třída. The`ImportFormatMode.KeepSourceFormatting` Parametr zajišťuje zachování formátování zdroje během operace připojení.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 6: Uložte konečný dokument

 Nakonec uložte sloučený dokument s povolenou funkcí "Keep Source Together" pomocí`Save` metoda`Document` třída.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Příklad zdrojového kódu pro Keep Source Together pomocí Aspose.Words pro .NET 

Zde je úplný zdrojový kód pro funkci "Keep Source Together" v C# pomocí Aspose.Words pro .NET:


```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Nastavte zdrojový dokument tak, aby se zobrazil přímo za obsahem cílového dokumentu.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

je to! Úspěšně jste implementovali funkci Keep Source Together pomocí Aspose.Words for .NET. Konečný dokument bude obsahovat sloučený obsah s odstavci ve zdrojovém dokumentu, které budou pohromadě.