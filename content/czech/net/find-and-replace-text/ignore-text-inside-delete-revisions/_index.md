---
title: Ignorovat text uvnitř Odstranit revize
linktitle: Ignorovat text uvnitř Odstranit revize
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat funkci "Ignorovat text uvnitř Delete Revisions" Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

tomto článku prozkoumáme zdrojový kód C# výše, abychom pochopili, jak používat funkci "Ignorovat text uvnitř Delete Revisions" v knihovně Aspose.Words for .NET. Tato funkce je užitečná, když chceme ignorovat text uvnitř odstraněných revizí při zpracování textu s dokumenty.

## Přehled knihovny Aspose.Words for .NET

Než se ponořím do podrobností kódu, dovolte mi krátce představit knihovnu Aspose.Words for .NET. Je to výkonná knihovna, která umožňuje vytvářet, upravovat a převádět dokumenty Wordu v aplikacích .NET. Nabízí mnoho pokročilých funkcí pro textové zpracování dokumentů, včetně správy revizí.

## Pochopení funkce "Ignorovat text uvnitř odstranění revizí".

Funkce "Ignorovat text uvnitř Delete Revisions" v Aspose.Words for .NET umožňuje určit, zda má být text uvnitř odstraněných revizí ignorován během určitých operací, jako je hledání a nahrazování textu. Když je tato funkce povolena, smazaný text uvnitř revizí se během operací nebere v úvahu.

## Krok 1: Vytvoření nového dokumentu pomocí Aspose.Words for .NET

 Než začneme s textem v dokumentu manipulovat, musíme vytvořit nový dokument pomocí Aspose.Words for .NET. To lze provést vytvořením instance a`Document` objekt:

```csharp
Document doc = new Document();
```

## Krok 2: Vložení neupraveného textu do dokumentu

 Jakmile máme dokument, můžeme vložit nezkontrolovaný text pomocí a`DocumentBuilder` objekt. Například pro vložení textu "Smazaný text" můžeme použít`Writeln` a`Write` metody:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## Krok 3: Odebrání odstavce se sledováním revizí

Pro ilustraci použití funkce "Ignorovat text uvnitř odstranění revizí" odstraníme odstavec z dokumentu pomocí sledování revizí. To nám umožní vidět, jak tato funkce ovlivňuje následné operace.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## Krok 4: Použití funkce "Ignorovat text uvnitř odstranění revizí".

 Nyní, když jsme připravili náš dokument odstraněním odstavce, můžeme povolit funkci "Ignorovat text uvnitř odstranění revizí" pomocí`FindReplaceOptions` objekt. Nastavíme`IgnoreDeleted`majetek do`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## Krok 5: Použití regulárních výrazů pro hledání a nahrazování

K provádění operací vyhledávání a nahrazování v textu dokumentu použijeme regulární výrazy. V našem příkladu vyhledáme všechny výskyty písmene "e" a nahradíme je hvězdičkou "* ". .SÍŤ`Regex` třída se k tomu používá:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Krok 6: Zobrazení výstupu upraveného dokumentu

 Po použití hledání a nahrazování můžeme zobrazit změněný obsah dokumentu pomocí`GetText` metoda:

```csharp
Console.WriteLine(doc.GetText());
```

## Krok 7: Úprava možností tak, aby zahrnovaly smazaný text

 Pokud chceme do výsledku zahrnout smazaný text, můžeme změnit možnosti tak, aby se smazaný text neignoroval. K tomu nastavíme`IgnoreDeleted`majetek do`false`:

```csharp
options. IgnoreDeleted = false;
```

## Krok 8: Výstup upraveného dokumentu s odstraněným textem

Po změně možností můžeme provést vyhledávání a nahradit znovu, abychom získali výsledek včetně smazaného textu:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Příklad zdrojového kódu pro Ignore Text Inside Delete Revisions pomocí Aspose.Words for .NET

Zde je úplný ukázkový zdrojový kód, který demonstruje použití funkce "Ignorovat text uvnitř Delete Revisions" s Aspose.Words pro .NET:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Vložit neupravený text.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// Odstraňte první odstavec s revizemi sledování.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## Závěr

tomto článku jsme prozkoumali zdrojový kód C#, abychom pochopili, jak používat funkci "Ignorovat text uvnitř Delete Revisions" v Aspose.Words pro .NET. Tato funkce je užitečná pro ignorování textu uvnitř odstraněných revizí při manipulaci s dokumenty. Postupovali jsme podle podrobného průvodce vytvořením dokumentu, vložením textu, odstraněním odstavce se sledováním revizí, použitím funkce "Ignorovat text uvnitř odstranění revizí" a provedením operací hledání a nahrazení.

### FAQ

#### Otázka: Co je funkce "Ignorovat text uvnitř Delete Revisions" v Aspose.Words for .NET?

A: Funkce "Ignorovat text uvnitř Delete Revisions" v Aspose.Words for .NET umožňuje určit, zda má být text uvnitř odstraněných revizí ignorován během určitých operací, jako je hledání a nahrazování textu. Když je tato funkce povolena, smazaný text uvnitř revizí se během operací nebere v úvahu.

#### Otázka: Co je Aspose.Words for .NET?

A: Aspose.Words for .NET je výkonná knihovna pro vytváření, úpravy a převod dokumentů Wordu do aplikací .NET. Nabízí mnoho pokročilých funkcí pro textové zpracování dokumentů, včetně správy revizí.

#### Otázka: Jak vytvořit nový dokument v Aspose.Words pro .NET?

 A: Než začnete manipulovat s textem v dokumentu, musíte vytvořit nový dokument pomocí Aspose.Words for .NET. To lze provést vytvořením instance a`Document` objekt. Zde je ukázkový kód pro vytvoření nového dokumentu:

```csharp
Document doc = new Document();
```

#### Otázka: Jak vložit neupravený text do dokumentu pomocí Aspose.Words for .NET?

 Odpověď: Jakmile máte dokument, můžete vložit nezkontrolovaný text pomocí a`DocumentBuilder` objekt. Například pro vložení textu "Smazaný text" můžete použít`Writeln` a`Write` metody:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### Otázka: Jak odstraním odstavec se sledováním revizí v Aspose.Words pro .NET?

Odpověď: Abychom ilustrovali použití funkce "Ignorovat text uvnitř odstranění revizí", odstraníme odstavec z dokumentu pomocí sledování revizí. To nám umožní vidět, jak tato funkce ovlivňuje následné operace.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### Otázka: Jak povolit funkci "Ignorovat text uvnitř Delete Revisions" v Aspose.Words for .NET?

 Odpověď: Nyní, když jsme připravili náš dokument odstraněním odstavce, můžeme povolit funkci "Ignorovat text uvnitř odstranění revizí" pomocí`FindReplaceOptions` objekt. Nastavíme`IgnoreDeleted`majetek do`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### Otázka: Jak vyhledávat a nahrazovat pomocí regulárních výrazů v Aspose.Words pro .NET?

Odpověď: K provádění operací vyhledávání a nahrazování v textu dokumentu použijeme regulární výrazy. V našem příkladu vyhledáme všechny výskyty písmene "e" a nahradíme je hvězdičkou "* ". Budeme používat .NET`Regex` třída pro toto:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Otázka: Jak zobrazit změněný obsah dokumentu v Aspose.Words pro .NET?

Odpověď: Po použití vyhledávání a nahrazování můžeme zobrazit změněný obsah dokumentu pomocí`GetText` metoda:

```csharp
Console.WriteLine(doc.GetText());
```

#### Otázka: Jak zahrnout smazaný text do výstupního výsledku v Aspose.Words pro .NET?

 Odpověď: Pokud chceme do výsledku zahrnout smazaný text, můžeme změnit možnosti tak, aby se smazaný text neignoroval. Za tímto účelem nastavíme`IgnoreDeleted`majetek do`false`:

```csharp
options. IgnoreDeleted = false;
```

#### Otázka: Jak zobrazit upravený dokument s odstraněným textem v Aspose.Words pro .NET?

Odpověď: Po změně možností můžeme provést nové vyhledávání a nahradit, abychom získali výsledek včetně smazaného textu:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
