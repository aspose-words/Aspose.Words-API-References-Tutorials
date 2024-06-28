---
title: Meta Znaky Ve Vyhledávání Vzoru
linktitle: Meta Znaky Ve Vyhledávání Vzoru
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat metaznaky ve vyhledávacím vzoru pomocí Aspose.Words for .NET k manipulaci s dokumenty aplikace Word.
type: docs
weight: 10
url: /cs/net/find-and-replace-text/meta-characters-in-search-pattern/
---
V tomto článku prozkoumáme výše uvedený zdrojový kód C#, abychom pochopili, jak používat funkci Meta Characters In Search Pattern v knihovně Aspose.Words for .NET. Tato funkce umožňuje používat speciální metaznaky k provádění pokročilého vyhledávání a nahrazování v dokumentech aplikace Word.

## Předpoklady

- Základní znalost jazyka C#.
- Vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

## Krok 1: Vytvoření nového dokumentu

 Než začneme ve vyhledávacím vzoru používat metaznaky, musíme vytvořit nový dokument pomocí Aspose.Words for .NET. To lze provést vytvořením instance a`Document` objekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Krok 2: Vložte text do dokumentu

 Jakmile máme dokument, můžeme vložit text pomocí a`DocumentBuilder` objekt. V našem příkladu používáme`Writeln` a`Write` metody pro vložení dvou řádků textu:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## Krok 3: Najděte a nahraďte text metaznaky

 Nyní použijeme`Range.Replace` funkce pro vyhledávání a nahrazování textu pomocí vyhledávacího vzoru obsahujícího speciální metaznaky. V našem příkladu nahradíme frázi „Toto je řádek 1&pToto je řádek 2“ za „Tento řádek je nahrazen“ pomocí`&p` metaznak reprezentující konec odstavce:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## Krok 4: Vložení konce stránky do dokumentu

 Abychom ilustrovali použití dalšího metaznaku, vložíme do dokumentu konec stránky pomocí`InsertBreak` metoda s`BreakType.PageBreak` parametry. Nejprve přesuneme kurzor z`DocumentBuilder` na konec dokumentu vložíme konec stránky a nový řádek textu:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## Krok 5: Najděte a nahraďte jiným metaznakem

 Nyní provedeme další hledání a nahrazení pomocí`&m` metaznak reprezentující konec stránky. Fráze „Toto je řádek 1&mToto je řádek 2“ nahrazujeme slovy „Konec stránky je nahrazen novým textem.“ :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## Krok 6: Uložení upraveného dokumentu

Nakonec upravený dokument uložíme do určeného adresáře pomocí`Save` metoda:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Příklad zdrojového kódu pro vzor Meta Characters In Search pomocí Aspose.Words for .NET

Zde je úplný ukázkový zdrojový kód, který demonstruje použití metaznaků ve vyhledávacím vzoru s Aspose.Words pro .NET:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## Závěr

V tomto článku jsme prozkoumali zdrojový kód C#, abychom pochopili, jak používat metaznaky ve vyhledávacím vzoru Aspose.Words pro .NET. Postupovali jsme podle podrobného průvodce, jak vytvořit dokument, vložit text, provést vyhledávání a nahrazování pomocí speciálních metaznaků, vkládat konce stránek a uložit upravený dokument.

### FAQ

#### Otázka: Co je funkce Meta Characters in Search Pattern v Aspose.Words for .NET?

Odpověď: Funkce Meta Characters In Search Pattern v Aspose.Words for .NET umožňuje používat speciální meta znaky k provádění pokročilého vyhledávání a nahrazování v dokumentech aplikace Word. Tyto metaznaky vám umožňují reprezentovat konce odstavců, sekce, stránky a další speciální prvky ve vašem vyhledávacím vzoru.

#### Otázka: Jak vytvořit nový dokument v Aspose.Words pro .NET?

 Odpověď: Před použitím metaznaků v šabloně vyhledávání musíte vytvořit nový dokument pomocí Aspose.Words for .NET. To lze provést vytvořením instance a`Document` objekt. Zde je ukázkový kód pro vytvoření nového dokumentu:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### Otázka: Jak vložit text do dokumentu pomocí Aspose.Words for .NET?

 Odpověď: Jakmile máte dokument, můžete vložit text pomocí a`DocumentBuilder` objekt. V našem příkladu používáme`Writeln` a`Write` metody pro vložení dvou řádků textu:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### Otázka: Jak vyhledávat a nahrazovat text metaznaky v dokumentu pomocí Aspose.Words for .NET?

 Odpověď: Chcete-li vyhledat a nahradit text metaznaky, můžete použít`Range.Replace` metoda. V našem příkladu nahradíme frázi „Toto je řádek 1&pToto je řádek 2“ za „Tento řádek je nahrazen“ pomocí`&p` metaznak reprezentující konec odstavce:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### Otázka: Jak vložit konec stránky do dokumentu pomocí Aspose.Words for .NET?

A: Pro ilustraci použití jiného metaznaku vložíme do dokumentu zalomení stránky pomocí`InsertBreak` metoda s`BreakType.PageBreak` parametry. Nejprve přesuneme kurzor z`DocumentBuilder` na konec dokumentu vložíme konec stránky a nový řádek textu:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### Otázka: Jak vyhledat a nahradit jiným metaznakem v dokumentu pomocí Aspose.Words for .NET?

 Odpověď: Nyní provedeme další hledání a nahrazení pomocí`&m` metaznak reprezentující konec stránky. Fráze „Toto je řádek 1&mToto je řádek 2“ nahrazujeme slovy „Konec stránky je nahrazen novým textem.“ :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### Otázka: Jak uložit upravený dokument v Aspose.Words pro .NET?

 Odpověď: Jakmile provedete změny v dokumentu, můžete jej uložit do určeného adresáře pomocí`Save` metoda:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```