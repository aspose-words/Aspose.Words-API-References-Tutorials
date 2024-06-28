---
title: Jednoduché připojení dokumentu
linktitle: Jednoduché připojení dokumentu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se připojovat a připojovat dokumenty Wordu se zachovaným formátováním pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/simple-append-document/
---

Tento tutoriál vás provede procesem používání funkce Simple Append Document aplikace Aspose.Words for .NET. Tato funkce umožňuje spojovat a připojovat dokumenty aplikace Word bez dalších možností.

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

Dále musíte načíst zdrojové a cílové dokumenty pomocí Aspose.Words.`Document` třída. Aktualizujte názvy souborů v`Document` konstruktor podle názvů vašich dokumentů.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Krok 3: Připojte zdrojový dokument k cílovému dokumentu

 Nyní můžete připojit zdrojový dokument k cílovému dokumentu pomocí`AppendDocument` metoda`Document` třída. The`ImportFormatMode.KeepSourceFormatting` Parametr zajišťuje zachování formátování zdroje během operace připojení.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 4: Uložte konečný dokument

 Nakonec uložte sloučený dokument pomocí funkce Jednoduché připojení dokumentu pomocí`Save` metoda`Document` třída.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Příklad zdrojového kódu pro Simple Append Document pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód pro funkci "Simple Append Document" v C# pomocí Aspose.Words pro .NET:

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Připojte zdrojový dokument k cílovému dokumentu bez dalších možností.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

A je to! Úspěšně jste implementovali funkci Simple Append Document pomocí Aspose.Words for .NET. Konečný dokument bude obsahovat sloučený obsah se zachovaným zdrojovým formátováním.