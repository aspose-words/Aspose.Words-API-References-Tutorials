---
title: Ignorujte text uvnitř revizí vložení
linktitle: Ignorujte text uvnitř revizí vložení
second_title: Aspose.Words API pro zpracování dokumentů
description: Zjistěte, jak používat funkci "Ignorovat text uvnitř revizí vkládání" Aspose.Words for .NET k manipulaci s revizemi vkládání v dokumentech aplikace Word.
type: docs
weight: 10
url: /cs/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

V tomto článku prozkoumáme zdrojový kód jazyka C# výše, abychom pochopili, jak používat funkci Ignorovat text uvnitř vkládání revizí v knihovně Aspose.Words for .NET. Tato funkce je užitečná, když chceme při manipulaci s dokumenty ignorovat text ve vložených revizích.

## Předpoklady

- Základní znalost jazyka C#.
- Vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

## Krok 1: Vytvoření nového dokumentu

 Než začneme manipulovat s textem uvnitř vložených revizí, musíme vytvořit nový dokument pomocí Aspose.Words for .NET. To lze provést vytvořením instance a`Document` objekt:

```csharp
Document doc = new Document();
```

## Krok 2: Vložte text se sledováním revizí

 Jakmile máme dokument, můžeme vložit text se sledováním revizí pomocí a`DocumentBuilder`objekt. Například pro vložení textu "Vložený" se sledováním revize můžeme použít`StartTrackRevisions`, `Writeln` a`StopTrackRevisions` metody:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## Krok 3: Vložte nezkontrolovaný text

 Kromě textu se sledováním revizí můžeme také vložit neupravený text pomocí`DocumentBuilder` objekt. Například pro vložení textu "Text" bez revize můžeme použít`Write` metoda:

```csharp
builder.Write("Text");
```

## Krok 4: Použití funkce Ignorovat text uvnitř Vložit revize

 Chcete-li ignorovat text uvnitř vkládání revizí při následných operacích, můžeme použít a`FindReplaceOptions` objekt a nastavte`IgnoreInserted`majetek do`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## Krok 5: Použití regulárních výrazů pro vyhledávání a nahrazování

K provádění vyhledávacích operací a nahrazování v textu dokumentu použijeme regulární výrazy. V našem příkladu vyhledáme všechny výskyty písmene "e" a nahradíme je hvězdičkou "* ". Použijeme .NET`Regex` třída pro toto:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Krok 6: Zobrazení upraveného výstupu dokumentu

 Po použití hledání a nahrazování můžeme zobrazit změněný obsah dokumentu pomocí`GetText` metoda:

```csharp
Console.WriteLine(doc.GetText());
```

## Krok 7: Změna možností tak, aby zahrnovaly revize vložení

Pokud chceme do výstupního výsledku zahrnout text uvnitř vložených revizí, můžeme změnit možnosti tak, aby nebyly ignorovány vložené revize. K tomu nastavíme`IgnoreInserted`majetek do`false`:

```csharp
options.IgnoreInserted = false;
```

## Krok 8: Zobrazení upraveného dokumentu s vložením revizí

Po změně možností můžeme provést vyhledávání a nahradit znovu, abychom získali výsledek s textem uvnitř vložených revizí:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Příklad zdrojového kódu pro Ignorování textu uvnitř vkládání revizí pomocí Aspose.Words for .NET

Zde je úplný ukázkový zdrojový kód, který demonstruje použití funkce Ignore Text Inside Insert Revisions s Aspose.Words for .NET:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Vložit text s revizemi sledování.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Vložit neupravený text.
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## Závěr

tomto článku jsme prozkoumali zdrojový kód C#, abychom pochopili, jak používat funkci Ignorovat text uvnitř vkládání revizí v Aspose.Words pro .NET. Postupovali jsme podle podrobného průvodce vytvářením dokumentu, vkládáním textu se sledovacími revizemi a nerevidovaným textem, pomocí funkce Ignorovat text uvnitř vkládání revizí, prováděním operací hledání a nahrazování regulárními výrazy a zobrazením upraveného dokumentu.

### FAQ

#### Otázka: Co je funkce "Ignorovat text uvnitř revizí vložení" v Aspose.Words pro .NET?

Odpověď: Funkce "Ignorovat text uvnitř revizí vložení" v Aspose.Words for .NET umožňuje určit, zda má být text uvnitř revizí vložení ignorován při určitých operacích, jako je hledání a nahrazování textu. Když je tato funkce povolena, text uvnitř revizí vložení se během operací nebere v úvahu.

#### Otázka: Jak mohu vytvořit nový dokument pomocí Aspose.Words for .NET?

 A: Chcete-li vytvořit nový dokument pomocí Aspose.Words for .NET, můžete vytvořit instanci a`Document` objekt. Zde je příklad kódu C# pro vytvoření nového dokumentu:

```csharp
Document doc = new Document();
```

#### Otázka: Jak mohu vložit text se sledováním revizí do Aspose.Words pro .NET?

Odpověď: Jakmile máte dokument, můžete vložit text se sledováním revizí pomocí a`DocumentBuilder` objekt. Chcete-li například vložit text "Vložený" se sledováním revize, můžete použít`StartTrackRevisions`, `Writeln` , a`StopTrackRevisions` metody:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### Otázka: Jak mohu vložit neupravený text do Aspose.Words pro .NET?

 A: Kromě textu se sledováním revizí můžete také vložit neupravený text pomocí`DocumentBuilder` objekt. Chcete-li například vložit text "Text" bez revize, můžete použít`Write` metoda:

```csharp
builder.Write("Text");
```

#### Otázka: Jak mohu ignorovat text uvnitř vložených revizí v Aspose.Words pro .NET?

 A: Chcete-li ignorovat text uvnitř revizí vložení během následujících operací, můžete použít a`FindReplaceOptions` objekt a nastavte`IgnoreInserted`majetek do`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

#### Otázka: Jak mohu provádět vyhledávání a nahrazování pomocí regulárních výrazů v Aspose.Words pro .NET?

 Odpověď: Chcete-li provádět operace vyhledávání a nahrazování v textu dokumentu pomocí regulárních výrazů, můžete použít .NET`Regex` třída. Chcete-li například vyhledat všechny výskyty písmene "e" a nahradit je hvězdičkou "* “, můžete vytvořit a`Regex` objekt a použijte jej s`Replace` metoda:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Otázka: Jak mohu zobrazit upravený výstup dokumentu v Aspose.Words pro .NET?

 Odpověď: Po použití operací vyhledávání a nahrazování můžete zobrazit změněný obsah dokumentu pomocí`GetText` metoda:

```csharp
Console.WriteLine(doc.GetText());
```

#### Otázka: Jak mohu zahrnout revize vložení do výsledku výstupu v Aspose.Words pro .NET?

 Odpověď: Chcete-li do výsledku zahrnout text uvnitř revizí vložení, můžete změnit možnosti tak, aby nebyly ignorovány revize vložení. K tomu můžete nastavit`IgnoreInserted` vlastnictvím`FindReplaceOptions` namítat proti`false`:

```csharp
options.IgnoreInserted = false;
```

#### Otázka: Jak mohu zobrazit upravený dokument s vloženými revizemi v Aspose.Words pro .NET?

Odpověď: Po změně možností tak, aby zahrnovaly vkládání revizí, můžete provést vyhledávání a nahradit znovu, abyste získali výsledek s textem uvnitř vložených revizí:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```