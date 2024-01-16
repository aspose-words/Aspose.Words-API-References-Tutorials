---
title: Přístup k záložkám v dokumentu aplikace Word
linktitle: Přístup k záložkám v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se přistupovat k záložkám v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-bookmarks/access-bookmarks/
---

V tomto článku prozkoumáme zdrojový kód C# výše, abychom pochopili, jak používat funkci Access Bookmarks v knihovně Aspose.Words for .NET. Tato funkce poskytuje přístup ke konkrétním záložkám v dokumentu aplikace Word.

## Předpoklady

- Základní znalost jazyka C#.
- Vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

## Krok 1: Načtení dokumentu

 Než začneme přistupovat k záložkám, musíme načíst dokument aplikace Word pomocí Aspose.Words for .NET. To lze provést vytvořením instance a`Document` objekt určující cestu k souboru dokumentu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Krok 2: Přístup k záložkám

Jakmile je dokument načten, můžeme přistupovat k záložkám v dokumentu. K záložkám lze přistupovat dvěma způsoby: podle indexu a podle názvu.

- Přístup podle indexu: V našem příkladu používáme index 0 pro přístup k první záložce dokumentu:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Přístup podle jména: V našem příkladu používáme název „MyBookmark3“ pro přístup ke konkrétní záložce v dokumentu:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

### Příklad zdrojového kódu pro Access Bookmarks pomocí Aspose.Words for .NET

Zde je úplný ukázkový zdrojový kód, který demonstruje přístup k záložkám pomocí Aspose.Words pro .NET:

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");
	
	// Podle indexu:
	Bookmark bookmark1 = doc.Range.Bookmarks[0];
	// Podle jména:
	Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
   
```

## Závěr

V tomto článku jsme prozkoumali zdrojový kód C#, abychom pochopili, jak používat funkci Access Bookmarks v Aspose.Words for .NET. Postupovali jsme podle podrobného průvodce k nahrání dokumentu a přístupu k záložkám pomocí indexu a názvu.

### Časté dotazy pro přístup k záložkám v dokumentu aplikace Word

#### Otázka: Jak mohu nahrát dokument aplikace Word pomocí Aspose.Words for .NET?

 A: Chcete-li načíst dokument aplikace Word pomocí Aspose.Words for .NET, můžete vytvořit instanci a`Document`objekt zadáním cesty k souboru dokumentu. Zde je ukázkový kód:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

#### Otázka: Jak mohu získat přístup k záložkám v dokumentu aplikace Word?

 Odpověď: K záložkám v dokumentu aplikace Word můžete přistupovat pomocí`Bookmarks` vlastnictvím`Range` objekt. K záložkám můžete přistupovat podle indexu nebo podle jména. Zde je ukázkový kód:

- Přístup podle indexu:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Přístup podle jména:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

#### Otázka: Jaká knihovna je nutná k použití funkce přístupu k záložkám v Aspose.Words for .NET?

A: Chcete-li použít funkci přístupu k záložkám v Aspose.Words pro .NET, potřebujete knihovnu Aspose.Words. Ujistěte se, že máte tuto knihovnu nainstalovanou ve svém vývojovém prostředí .NET.

#### Otázka: Existují jiné způsoby přístupu k záložkám v dokumentu aplikace Word?

 Odpověď: Ano, kromě přístupu k záložkám podle rejstříku nebo názvu můžete také procházet všechny záložky v dokumentu pomocí smyčky. Celkový počet záložek v dokumentu můžete získat pomocí`Count` vlastnictvím`Bookmarks` sbírka. Ke každé záložce pak můžete přistupovat pomocí rejstříku. Zde je ukázkový kód:

```csharp
int bookmarkCount = doc.Range.Bookmarks.Count;

for (int i = 0; i < bookmarkCount; i++)
{
     Bookmark bookmark = doc.Range.Bookmarks[i];
     // Udělejte něco se záložkou...
}
```