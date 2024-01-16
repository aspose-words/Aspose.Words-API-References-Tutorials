---
title: Přesunout do slučovacího pole v dokumentu aplikace Word
linktitle: Přesunout do slučovacího pole v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak implementovat funkci Přesunout do slučovacího pole ve wordovém dokumentu Aspose.Words for .NET pomocí podrobného průvodce.
type: docs
weight: 10
url: /cs/net/add-content-using-documentbuilder/move-to-merge-field/
---
tomto příkladu prozkoumáme funkci Přesunout do slučovacího pole ve wordovém dokumentu Aspose.Words for .NET. Aspose.Words je výkonná knihovna pro manipulaci s dokumenty, která umožňuje vývojářům vytvářet, upravovat a převádět dokumenty aplikace Word programově. Funkce Přesunout do slučovacího pole nám umožňuje navigaci ke sloučení polí v dokumentu a provádění různých operací s nimi.


## Vysvětlení zdrojového kódu krok za krokem

Pojďme si projít zdrojový kód krok za krokem, abychom pochopili, jak používat funkci Move To Merge Field pomocí Aspose.Words for .NET.

## Krok 1: Inicializace dokumentu a tvůrce dokumentů

Nejprve inicializujte objekty Document a DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2 Vložení slučovacího pole a přidání textu za něj

Pomocí metody InsertField třídy DocumentBuilder vložte slučovací pole a poté za něj přidejte text:

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## Krok 3: Kurzor stavitele je aktuálně na konci dokumentu.

```csharp
Assert.Null(builder.CurrentNode);
```
## Krok 4: Přesunutí kurzoru tvůrce dokumentů do slučovacího pole

Chcete-li přesunout kurzor tvůrce dokumentů do slučovacího pole, použijte metodu MoveToField třídy DocumentBuilder:

```csharp
builder.MoveToField(field, true);
```

## Přidání textu ihned za slučovací pole

Jakmile je kurzor tvůrce dokumentů uvnitř slučovacího pole, můžete přidat text bezprostředně za něj pomocí metody Write:

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### Příklad zdrojového kódu pro Move To Merge Field pomocí Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Vložte pole pomocí DocumentBuilderu a přidejte za něj řadu textu.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// Kurzor stavitele je aktuálně na konci dokumentu.
Assert.Null(builder.CurrentNode);
// Tvůrce můžeme přesunout do pole, jako je toto, umístěním kurzoru na bezprostředně za pole.
builder.MoveToField(field, true);

// Všimněte si, že kurzor je na místě za uzlem FieldEnd pole, což znamená, že ve skutečnosti nejsme uvnitř pole.
// Pokud chceme přesunout DocumentBuilder dovnitř pole,
// budeme jej muset přesunout do uzlu FieldStart nebo FieldSeparator pole pomocí metody DocumentBuilder.MoveTo().
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## Závěr

prozkoumali jsme funkci Přesunout do slučovacího pole Aspose.Words pro .NET. Naučili jsme se navigovat ke slučování polí v dokumentu pomocí třídy DocumentBuilder a provádět s nimi operace. Tato funkce je užitečná při programovém zpracování textu se sloučením

### Nejčastější dotazy pro přesun do slučovacího pole v dokumentu aplikace Word

#### Otázka: Jaký je účel funkce Přesunout do slučovacího pole v Aspose.Words pro .NET?

Odpověď: Funkce Přesunout do slučovacího pole v Aspose.Words for .NET umožňuje vývojářům přejít ke slučování polí v dokumentu aplikace Word a programově s nimi provádět různé operace. Slučovací pole jsou speciální zástupné symboly používané v dokumentech aplikace Word pro operace hromadné korespondence.

#### Otázka: Jak mohu vložit slučovací pole do dokumentu aplikace Word pomocí Aspose.Words for .NET?

Odpověď: K vložení slučovacího pole do dokumentu můžete použít metodu InsertField třídy DocumentBuilder. Po vložení slučovacího pole můžete přidat obsah, například text, před nebo za pole pomocí metody Write.

#### Otázka: Jak přesunu kurzor Tvůrce dokumentů do určitého slučovacího pole?

Odpověď: Chcete-li přesunout kurzor tvůrce dokumentů na konkrétní slučovací pole, použijte metodu MoveToField třídy DocumentBuilder a předejte pole jako parametr. Tím se kurzor umístí hned za slučovací pole.

#### Otázka: Mohu přidat text do slučovacího pole pomocí funkce Přesunout do slučovacího pole?

Odpověď: Ne, funkce Přesunout do slučovacího pole umístí kurzor tvůrce dokumentů bezprostředně za slučovací pole. Chcete-li přidat text do slučovacího pole, můžete pomocí metody DocumentBuilder.MoveTo přesunout kurzor na uzel FieldStart nebo FieldSeparator slučovacího pole.

#### Otázka: Jak mohu provádět operace hromadné korespondence pomocí Aspose.Words for .NET?

A: Aspose.Words for .NET poskytuje rozsáhlou podporu pro operace hromadné korespondence. Třídu MailMerge můžete použít k provádění hromadné korespondence pomocí dat z různých zdrojů, jako jsou pole, datové sady nebo vlastní zdroje dat.