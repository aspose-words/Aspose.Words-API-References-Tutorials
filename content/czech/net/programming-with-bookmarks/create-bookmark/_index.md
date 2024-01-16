---
title: Vytvořit záložku v dokumentu aplikace Word
linktitle: Vytvořit záložku v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vytvářet záložky v dokumentu aplikace Word a určit úrovně náhledu záložek v PDF pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-bookmarks/create-bookmark/
---

V tomto článku prozkoumáme zdrojový kód C# výše, abychom pochopili, jak používat funkci Create Bookmark v knihovně Aspose.Words for .NET. Tato funkce umožňuje vytvářet záložky v dokumentu a určit úrovně náhledu záložek ve výstupním souboru PDF.

## Předpoklady

- Základní znalost jazyka C#.
- Vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

## Krok 1: Vytvoření dokumentu a generátoru

 Před vytvořením záložek musíme vytvořit dokument a tvůrce dokumentů pomocí`Document` a`DocumentBuilder` objekty:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Vytvoření hlavní záložky

 Používáme`StartBookmark` způsob spuštění hlavní záložky a`EndBookmark` způsob, jak to ukončit. Mezitím můžeme přidat text a další záložky:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Zde přidejte další záložky nebo text.

builder. EndBookmark("My Bookmark");
```

## Krok 3: Vytvoření vnořených záložek

Můžeme také vytvořit vnořené záložky uvnitř hlavní záložky. Používáme to samé`StartBookmark` a`EndBookmark` metody pro vytvoření a ukončení vnořených záložek:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Krok 4: Určení úrovní náhledu záložek ve výstupním souboru PDF

 Používáme`PdfSaveOptions` objekt k určení úrovní náhledu záložek ve výstupním souboru PDF. Používáme`BookmarksOutlineLevels` vlastnictví

  pro přidání hlavních záložek a vnořených záložek s jejich příslušnými úrovněmi:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Příklad zdrojového kódu pro Create Bookmark using Aspose.Words for .NET

Zde je úplný ukázkový zdrojový kód, který demonstruje vytváření záložek pomocí Aspose.Words pro .NET:

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## Závěr

V tomto článku jsme prozkoumali zdrojový kód C#, abychom pochopili, jak používat funkci Create Bookmark Aspose.Words for .NET. Postupovali jsme podle podrobného průvodce vytvářením záložek v dokumentu a určením úrovní náhledu záložek ve výstupním souboru PDF.

### Nejčastější dotazy

#### Otázka: Jaké jsou předpoklady pro použití funkce "Vytvořit záložky" v Aspose.Words pro .NET?

A: Chcete-li použít funkci "Vytvořit záložky" v Aspose.Words pro .NET, musíte mít základní znalosti jazyka C#. Potřebujete také vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

#### Otázka: Jak vytvořit dokument v Aspose.Words pro .NET?

 A: Chcete-li vytvořit dokument v Aspose.Words pro .NET, můžete použít`Document` třída. Zde je ukázkový kód:

```csharp
Document doc = new Document();
```

#### Otázka: Jak vytvořit hlavní záložku v dokumentu pomocí Aspose.Words for .NET?

 A: Chcete-li vytvořit hlavní záložku v dokumentu pomocí Aspose.Words pro .NET, můžete použít`StartBookmark` metodu pro spuštění záložky, přidání textu nebo jiných záložek dovnitř a poté použijte` EndBookmark` abych to ukončil. Zde je ukázkový kód:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Otázka: Jak vytvořit vnořenou záložku uvnitř hlavní záložky pomocí Aspose.Words for .NET?

 A: Chcete-li vytvořit vnořenou záložku uvnitř hlavní záložky pomocí Aspose.Words pro .NET, můžete použít stejný`StartBookmark` a`EndBookmark` metody pro spuštění a ukončení vnořené záložky. Zde je ukázkový kód:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### Otázka: Jak určit úrovně náhledu záložek ve výstupním PDF pomocí Aspose.Words for .NET?

 Odpověď: Chcete-li určit úrovně náhledu záložek ve výstupním PDF pomocí Aspose.Words pro .NET, můžete použít`PdfSaveOptions` třída a`BookmarksOutlineLevels` vlastnictví. Můžete přidat hlavní záložky a vnořené záložky s jejich příslušnými úrovněmi. Zde je ukázkový kód:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### Otázka: Jak uložit dokument po vytvoření záložek pomocí Aspose.Words for .NET?

 Odpověď: Chcete-li uložit dokument po vytvoření záložek pomocí Aspose.Words pro .NET, můžete použít`Save` metoda`Document` objekt určující cestu k cílovému souboru. Zde je ukázkový kód:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### Otázka: Jak určit úrovně náhledu záložek ve výstupním PDF pomocí Aspose.Words for .NET?

 Odpověď: Chcete-li určit úrovně náhledu záložek ve výstupním PDF pomocí Aspose.Words pro .NET, můžete použít`PdfSaveOptions` třída a`BookmarksOutlineLevels` vlastnictví. Můžete přidat hlavní záložky a vnořené záložky s jejich příslušnými úrovněmi. Zde je ukázkový kód:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### Otázka: Jak vytvořit vnořené záložky uvnitř hlavní záložky pomocí Aspose.Words for .NET?

 A: Chcete-li vytvořit vnořené záložky uvnitř hlavní záložky pomocí Aspose.Words pro .NET, můžete použít stejné`StartBookmark` a`EndBookmark` metody pro spuštění a ukončení vnořených záložek. Nezapomeňte zadat nadřazenou záložku jako parametr při volání`StartBookmark` metoda. Zde je ukázkový kód:

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### Otázka: Jak přidat text do záložky pomocí Aspose.Words for .NET?

 A: Chcete-li přidat text do záložky pomocí Aspose.Words pro .NET, můžete použít`Write` metoda`DocumentBuilder`objekt určující text, který se má přidat. Zde je ukázkový kód:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Otázka: Jak vytvořit hlavní záložku v dokumentu pomocí Aspose.Words for .NET?

 A: Chcete-li vytvořit hlavní záložku v dokumentu pomocí Aspose.Words pro .NET, můžete použít`StartBookmark` způsob spuštění záložky a`EndBookmark` způsob, jak to ukončit. Zde je ukázkový kód:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```