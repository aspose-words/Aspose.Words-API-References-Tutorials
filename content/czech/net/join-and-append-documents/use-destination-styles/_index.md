---
title: Použijte styly cíle
linktitle: Použijte styly cíle
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se připojovat a připojovat dokumenty aplikace Word při použití stylů cílového dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/use-destination-styles/
---

Tento tutoriál vás provede procesem používání funkce Use Destination Styles v Aspose.Words for .NET. Tato funkce umožňuje spojovat a připojovat dokumenty aplikace Word při použití stylů cílového dokumentu.

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
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Krok 3: Připojte zdrojový dokument s cílovými styly

 Chcete-li připojit zdrojový dokument k cílovému dokumentu při použití stylů cílového dokumentu, můžete použít`AppendDocument` metoda`Document` třída s`ImportFormatMode.UseDestinationStyles` parametr.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Krok 4: Uložte konečný dokument

 Nakonec uložte sloučený dokument s povolenou funkcí Použít styly cíle pomocí`Save` metoda`Document` třída.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### Příklad zdrojového kódu pro Use Destination Styles pomocí Aspose.Words for .NET

Zde je úplný zdrojový kód pro funkci "Použít styly cíle" v C# pomocí Aspose.Words pro .NET:

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Připojte zdrojový dokument pomocí stylů cílového dokumentu.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

A je to! Úspěšně jste implementovali funkci Use Destination Styles pomocí Aspose.Words for .NET. Konečný dokument bude obsahovat sloučený obsah s použitými styly cílového dokumentu.