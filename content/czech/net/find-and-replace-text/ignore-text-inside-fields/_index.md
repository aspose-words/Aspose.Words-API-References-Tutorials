---
title: Ignorovat text uvnitř polí
linktitle: Ignorovat text uvnitř polí
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat funkci "Ignorovat text uvnitř polí" Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/find-and-replace-text/ignore-text-inside-fields/
---
V tomto článku prozkoumáme zdrojový kód C# výše, abychom pochopili, jak používat funkci Ignore Text Inside Fields v knihovně Aspose.Words for .NET. Tato funkce je užitečná, když chceme při manipulaci s dokumenty ignorovat text uvnitř polí.

## Předpoklady

- Základní znalost jazyka C#.
- Vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

## Krok 1: Vytvoření nového dokumentu

 Než začneme manipulovat s textem uvnitř polí, musíme vytvořit nový dokument pomocí Aspose.Words for .NET. To lze provést vytvořením instance a`Document` objekt:

```csharp
Document doc = new Document();
```

## Krok 2: Vložení pole s textem uvnitř

 Jakmile máme dokument, můžeme do něj vložit pole obsahující text pomocí a`DocumentBuilder` objekt. Například pro vložení pole "INCLUDETEXT" s textem "Text v poli" můžeme použít`InsertField` metoda:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

## Krok 3: Použití funkce Ignorovat text uvnitř polí

 K ignorování textu uvnitř polí při následných operacích můžeme použít a`FindReplaceOptions` objekt a nastavte`IgnoreFields`majetek do`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

## Krok 4: Použití regulárních výrazů pro vyhledávání a nahrazování

K provádění operací vyhledávání a nahrazování v textu dokumentu použijeme regulární výrazy. V našem příkladu vyhledáme všechny výskyty písmene "e" a nahradíme je hvězdičkou "* ". Použijeme .NET`Regex` třída pro toto:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Krok 5: Zobrazení upraveného výstupu dokumentu

 Po použití hledání a nahrazování můžeme zobrazit změněný obsah dokumentu pomocí`GetText` metoda:

```csharp
Console.WriteLine(doc.GetText());
```

## Krok 6: Změna možností tak, aby zahrnovala pole

 zahrneme text uvnitř polí do výstupního výsledku, můžeme změnit možnosti tak, aby pole neignorovala. K tomu nastavíme`IgnoreFields`majetek do`false`:

```csharp
options.IgnoreFields = false;
```

## Krok 7: Zobrazení upraveného dokumentu s poli

Po změně možností můžeme provést vyhledávání a nahrazování znovu, abychom získali výsledek s textem uvnitř zahrnutých polí:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Příklad zdrojového kódu pro Ignorovat text uvnitř polí pomocí Aspose.Words pro .NET

Zde je úplný ukázkový zdrojový kód, který demonstruje použití funkce Ignore Text Inside Fields s Aspose.Words pro .NET:

```csharp
    
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Vložte pole s textem uvnitř.
	builder.InsertField("INCLUDETEXT", "Text in field");
	
	FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
	
	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreFields = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
  
```

## Závěr

V tomto článku jsme prozkoumali zdrojový kód C#, abychom pochopili, jak používat funkci Ignorovat text uvnitř polí v Aspose.Words pro .NET. Postupovali jsme podle podrobného průvodce vytvořením dokumentu, vložením pole s textem dovnitř, použitím funkce Ignorovat text uvnitř polí, provedením operací hledání a nahrazení regulárními výrazy a zobrazením upraveného dokumentu .

### FAQ

#### Otázka: Co je funkce "Ignorovat text uvnitř polí" v Aspose.Words pro .NET?

Odpověď: Funkce "Ignorovat text uvnitř polí" v Aspose.Words for .NET umožňuje určit, zda má být text uvnitř polí ignorován při určitých operacích, jako je hledání a nahrazování textu. Když je tato funkce povolena, text uvnitř polí se během operací nebere v úvahu.

#### Otázka: Jak mohu vytvořit nový dokument pomocí Aspose.Words for .NET?

 A: Chcete-li vytvořit nový dokument pomocí Aspose.Words for .NET, můžete vytvořit instanci a`Document` objekt. Zde je příklad kódu C# pro vytvoření nového dokumentu:

```csharp
Document doc = new Document();
```

#### Otázka: Jak mohu vložit pole s textem do dokumentu pomocí Aspose.Words for .NET?

 A: Jakmile máte dokument, můžete vložit pole s textem uvnitř pomocí a`DocumentBuilder` objekt. Chcete-li například vložit pole "INCLUDETEXT" s textem "Text v poli", můžete použít`InsertField` metoda:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

#### Otázka: Jak mohu ignorovat text uvnitř polí v Aspose.Words pro .NET?

 A: Chcete-li ignorovat text uvnitř polí během následujících operací, můžete použít a`FindReplaceOptions` objekt a nastavte`IgnoreFields`majetek do`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
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

#### Otázka: Jak mohu zahrnout pole do výsledku výstupu v Aspose.Words pro .NET?

 Odpověď: Chcete-li zahrnout text do polí ve výsledku výstupu, můžete změnit možnosti tak, aby pole neignorovala. K tomu můžete nastavit`IgnoreFields` vlastnictvím`FindReplaceOptions` namítat proti`false`:

```csharp
options.IgnoreFields = false;
```

#### Otázka: Jak mohu zobrazit upravený dokument s poli v Aspose.Words pro .NET?

Odpověď: Po změně možností tak, aby zahrnovala pole, můžete provést vyhledávání a nahradit znovu, abyste získali výsledek s textem uvnitř zahrnutých polí:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```