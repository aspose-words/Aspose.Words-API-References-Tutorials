---
title: Rozpoznávání a substituce v rámci náhradních vzorů
linktitle: Rozpoznávání a substituce v rámci náhradních vzorů
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat vzory nahrazování s rozpoznáváním a substitucemi v Aspose.Words for .NET k manipulaci s dokumenty Wordu.
type: docs
weight: 10
url: /cs/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

V tomto článku prozkoumáme výše uvedený zdrojový kód C#, abychom porozuměli tomu, jak používat funkci Recognize And Substitutions Within Replacement Patterns v knihovně Aspose.Words for .NET. Tato funkce pomáhá rozpoznat složité vzorce vyhledávání a provádět substituce na základě skupin zachycených během manipulace s dokumenty.

## Předpoklady

- Základní znalost jazyka C#.
- Vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

## Krok 1: Vytvoření nového dokumentu

Než začneme používat shody a substituce v nahrazovacích vzorech, musíme vytvořit nový dokument pomocí Aspose.Words for .NET. To lze provést vytvořením instance a`Document` objekt:

```csharp
Document doc = new Document();
```

## Krok 2: Vložte text do dokumentu

 Jakmile máme dokument, můžeme vložit text pomocí a`DocumentBuilder` objekt. V našem příkladu používáme`Write` metoda vložit frázi "Jason dává Paulovi nějaké peníze." :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## Krok 3: Rozpoznávání a substituce v náhradních vzorech

 Nyní použijeme`Range.Replace` funkce pro vyhledávání a nahrazování textu pomocí regulárního výrazu k rozpoznání konkrétních vzorů. V našem příkladu používáme regulární výraz`([A-z]+) gives money to ([A-z]+)` rozpoznat věty, kde někdo dává peníze někomu jinému. Používáme náhradní vzor`$2 takes money from $1` provést substituci obrácením rolí. Použití`$1` a`$2` odkazuje na skupiny zachycené regulárním výrazem:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### Příklad zdrojového kódu pro rozpoznávání a substituce v rámci nahrazovacích vzorů pomocí Aspose.Words for .NET

Zde je úplný ukázkový zdrojový kód pro ilustraci použití shod a substitucí ve vzorcích nahrazení pomocí Aspose.Words pro .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## Závěr

V tomto článku jsme prozkoumali zdrojový kód C#, abychom porozuměli tomu, jak používat funkci Rozpoznat a nahradit náhradní vzory v Aspose.Words pro .NET. Postupovali jsme podle podrobného průvodce, jak vytvořit dokument, vložit text, provést vyhledávání a nahrazování pomocí regulárních výrazů a substitučních vzorů na základě zachycených skupin a manipulovat s dokumentem.

### FAQ

#### Otázka: Co je funkce "Rozpoznat a nahradit v rámci vzorů nahrazení" v Aspose.Words pro .NET?

Odpověď: Funkce „Rozpoznat a nahradit v rámci nahrazovacích vzorů“ v Aspose.Words for .NET vám umožňuje rozpoznat složité vzorce vyhledávání pomocí regulárních výrazů a provádět substituce na základě zachycených skupin během manipulace s dokumenty. Umožňuje vám dynamicky transformovat odpovídající text odkazováním na zachycené skupiny v náhradním vzoru.

#### Otázka: Jak mohu vytvořit nový dokument pomocí Aspose.Words for .NET?

 A: Chcete-li vytvořit nový dokument pomocí Aspose.Words for .NET, můžete vytvořit instanci a`Document` objekt. Zde je příklad kódu C# pro vytvoření nového dokumentu:

```csharp
Document doc = new Document();
```

#### Otázka: Jak mohu vložit text do dokumentu pomocí Aspose.Words for .NET?

 Odpověď: Jakmile máte dokument, můžete vložit text pomocí a`DocumentBuilder` objekt. Chcete-li například vložit frázi "Jason dává peníze Paulovi.", můžete použít`Write` metoda:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

#### Otázka: Jak mohu v Aspose.Words for .NET provádět textové vyhledávání a nahrazování pomocí regulárních výrazů?

 Odpověď: Chcete-li v Aspose.Words pro .NET provádět vyhledávání a nahrazování textu pomocí regulárních výrazů, můžete použít`Range.Replace` fungovat spolu se vzorem regulárního výrazu. Můžete vytvořit a`Regex` objekt s požadovaným vzorem a předat jej`Replace` metoda:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### Otázka: Jak mohu použít zachycené skupiny ve vzoru nahrazení během hledání a nahrazování textu v Aspose.Words pro .NET?

 Odpověď: Chcete-li použít zachycené skupiny ve vzoru nahrazení během vyhledávání a nahrazování textu v Aspose.Words pro .NET, můžete povolit`UseSubstitutions` vlastnictvím`FindReplaceOptions` objekt. To vám umožní odkazovat na zachycené skupiny pomocí`$1`, `$2`atd. v náhradním vzoru:

```csharp
FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### Otázka: Co demonstruje ukázkový zdrojový kód pro funkci "Rozpoznání a nahrazení v rámci nahrazovacích vzorů" v Aspose.Words for .NET?

Odpověď: Ukázkový zdrojový kód demonstruje použití funkce "Rozpoznat a nahradit v rámci nahrazovacích vzorů" v Aspose.Words pro .NET. Ukazuje, jak vytvořit dokument, vložit text, provádět textové vyhledávání a nahrazování pomocí regulárních výrazů a používat zachycené skupiny ve vzoru nahrazení k dynamické transformaci shodného textu.

#### Otázka: Kde najdu další informace a příklady použití regulárních výrazů v Aspose.Words pro .NET?

Odpověď: Další informace a příklady použití regulárních výrazů v Aspose.Words pro .NET naleznete v[Aspose.Words for .NET API odkazy](https://reference.aspose.com/words/net/). Dokumentace poskytuje podrobná vysvětlení a příklady kódu pro různé scénáře zahrnující regulární výrazy a manipulaci s textem v Aspose.Words for .NET.

#### Otázka: Mohu během vyhledávání a nahrazování textu manipulovat s jinými aspekty dokumentu na základě zachycených skupin?

Odpověď: Ano, během vyhledávání a nahrazování textu můžete manipulovat s dalšími aspekty dokumentu na základě zachycených skupin. Kromě provádění náhrad textu můžete upravit formátování, styly, strukturu dokumentu a další prvky na základě zachycených skupin pomocí různých rozhraní API poskytovaných Aspose.Words pro .NET.

#### Otázka: Existují nějaká omezení nebo úvahy při používání regulárních výrazů a zachycených skupin v Aspose.Words pro .NET?

Odpověď: I když regulární výrazy a zachycené skupiny nabízejí výkonné možnosti pro vyhledávání a nahrazování textu v Aspose.Words pro .NET, je důležité vzít v úvahu jejich složitost a dopady na výkon. Vysoce složité regulární výrazy a velký počet zachycených skupin mohou ovlivnit výkon. Doporučuje se otestovat a optimalizovat regulární výrazy pro vaše konkrétní případy použití, abyste zajistili efektivní manipulaci s dokumenty.

#### Otázka: Mohu použít funkci "Rozpoznat a nahradit náhradní vzory" s jinými jazyky než angličtinou?

Odpověď: Ano, funkci "Rozpoznat a nahradit v rámci nahrazovacích vzorů" v Aspose.Words pro .NET lze použít s jinými jazyky než s angličtinou. Regulární výrazy jsou jazykově agnostické a lze je vytvořit tak, aby odpovídaly konkrétním vzorům v jakémkoli jazyce. Vzor regulárního výrazu můžete upravit tak, aby vyhovoval požadovanému jazyku a konkrétním textovým vzorům, které chcete rozpoznat a nahradit.