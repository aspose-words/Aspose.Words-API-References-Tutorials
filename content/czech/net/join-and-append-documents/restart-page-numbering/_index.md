---
title: Restartujte číslování stránek
linktitle: Restartujte číslování stránek
second_title: Aspose.Words API pro zpracování dokumentů
description: Přečtěte si, jak restartovat číslování stránek při spojování a připojování dokumentů aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/restart-page-numbering/
---

Tento výukový program vás provede procesem používání funkce číslování stránek po restartu Aspose.Words for .NET. Tato funkce umožňuje připojovat a připojovat dokumenty aplikace Word při restartování číslování stránek ve zdrojovém dokumentu.

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

## Krok 3: Nastavte zdrojový dokument na Restartovat číslování stránek

 Chcete-li znovu spustit číslování stránek ve zdrojovém dokumentu, musíte nastavit`SectionStart` vlastnost první sekce ve zdrojovém dokumentu na`SectionStart.NewPage` a nastavte`RestartPageNumbering`majetek do`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## Krok 4: Připojte zdrojový dokument k cílovému dokumentu

 Nyní můžete připojit zdrojový dokument k cílovému dokumentu pomocí`AppendDocument` metoda`Document` třída. The`ImportFormatMode.KeepSourceFormatting` Parametr zajišťuje zachování formátování zdroje během operace připojení.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 5: Uložte konečný dokument

 Nakonec uložte sloučený dokument s povolenou funkcí Restartovat číslování stránek pomocí`Save` metoda`Document` třída.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### Příklad zdrojového kódu pro číslování stránek Restart pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód pro funkci "Restart Page Numbering" v C# pomocí Aspose.Words for .NET:
 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

A je to! Úspěšně jste implementovali funkci Restartovat číslování stránek pomocí Aspose.Words for .NET. Konečný dokument bude obsahovat sloučený obsah s číslováním stránek restartovaným ve zdrojovém dokumentu.