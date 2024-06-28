---
title: Odpojit záhlaví a zápatí
linktitle: Odpojit záhlaví a zápatí
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se připojovat a připojovat dokumenty Wordu a zároveň zrušit propojení záhlaví a zápatí pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/unlink-headers-footers/
---

Tento tutoriál vás provede procesem používání funkce Unlink Headers Footers Aspose.Words for .NET. Tato funkce umožňuje spojovat a připojovat dokumenty Wordu a zároveň odpojovat záhlaví a zápatí od zdrojového dokumentu.

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

## Krok 3: Odpojte záhlaví a zápatí ve zdrojovém dokumentu

 Chcete-li odpojit záhlaví a zápatí ve zdrojovém dokumentu od pokračování záhlaví a zápatí cílového dokumentu, musíte nastavit`LinkToPrevious` vlastnictvím`HeadersFooters` kolekce v první části zdrojového dokumentu do`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Krok 4: Připojte zdrojový dokument k cílovému dokumentu

 Nyní můžete připojit zdrojový dokument k cílovému dokumentu pomocí`AppendDocument` metoda`Document` třída. The`ImportFormatMode.KeepSourceFormatting` Parametr zajišťuje zachování formátování zdroje během operace připojení.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 5: Uložte konečný dokument

 Nakonec uložte sloučený dokument s povolenou funkcí Unlink Headers Footers pomocí`Save` metoda`Document` třída.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Příklad zdrojového kódu pro Unlink Headers Footers pomocí Aspose.Words for .NET

Zde je úplný zdrojový kód pro funkci "Unlink Headers Footers" v C# pomocí Aspose.Words pro .NET:

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Chcete-li to zastavit, zrušte propojení záhlaví a zápatí ve zdrojovém dokumentu
	// od pokračování v záhlaví a zápatí cílového dokumentu.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

je to! Úspěšně jste implementovali funkci Unlink Headers Footers pomocí Aspose.Words for .NET. Konečný dokument bude obsahovat sloučený obsah se záhlavím a zápatím ze zdrojového dokumentu, který není propojen s cílovým dokumentem.