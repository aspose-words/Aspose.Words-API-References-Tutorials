---
title: Aktualizujte rozvržení stránky
linktitle: Aktualizujte rozvržení stránky
second_title: Aspose.Words API pro zpracování dokumentů
description: Přečtěte si, jak aktualizovat rozvržení stránky při spojování a připojování dokumentů Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/update-page-layout/
---

Tento výukový program vás provede procesem používání funkce Update Page Layout Aspose.Words for .NET. Tato funkce zajišťuje správnou aktualizaci rozvržení stránky při spojování a připojování dokumentů aplikace Word.

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

## Krok 3: Aktualizujte rozvržení stránky pro cílový dokument

 Chcete-li zajistit, aby se rozvržení stránky před připojením zdrojového dokumentu správně aktualizovalo, můžete zavolat`UpdatePageLayout` na cílovém dokumentu.

```csharp
dstDoc.UpdatePageLayout();
```

## Krok 4: Připojte zdrojový dokument k cílovému dokumentu

 Nyní můžete připojit zdrojový dokument k cílovému dokumentu pomocí`AppendDocument` metoda`Document` třída. The`ImportFormatMode.KeepSourceFormatting` Parametr zajišťuje zachování formátování zdroje během operace připojení.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 5: Znovu aktualizujte rozvržení stránky

 Po připojení zdrojového dokumentu musíte zavolat`UpdatePageLayout`metodu znovu na cílovém dokumentu, abyste zajistili, že všechny změny provedené po operaci připojení se projeví ve vykresleném výstupu.

```csharp
dstDoc.UpdatePageLayout();
```

## Krok 6: Uložte konečný dokument

 Nakonec uložte sloučený dokument s povolenou funkcí Aktualizovat rozvržení stránky pomocí`Save` metoda`Document` třída.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Příklad zdrojového kódu pro aktualizaci rozvržení stránky pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód pro funkci "Aktualizovat rozvržení stránky" v C# pomocí Aspose.Words pro .NET:

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Pokud je cílový dokument vykreslen jako PDF, obrázek atd.
	// nebo UpdatePageLayout se volá před zdrojovým dokumentem. Je připojeno,
	// pak se žádné změny provedené poté neprojeví ve vykresleném výstupu
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Aby se změny aktualizovaly na vykreslený výstup, je nutné znovu zavolat UpdatePageLayout.
	// Pokud nebude znovu volána, připojený dokument se neobjeví ve výstupu dalšího vykreslování.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

je to! Úspěšně jste implementovali funkci Update Page Layout pomocí Aspose.Words for .NET. Konečný dokument bude obsahovat sloučený obsah se správně aktualizovaným rozložením stránky.