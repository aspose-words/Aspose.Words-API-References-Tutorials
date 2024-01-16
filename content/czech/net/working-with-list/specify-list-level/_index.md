---
title: Zadejte úroveň seznamu
linktitle: Zadejte úroveň seznamu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak určit úroveň seznamu v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-list/specify-list-level/
---

V tomto podrobném tutoriálu vám ukážeme, jak určit úroveň seznamu v dokumentu aplikace Word pomocí Aspose.Words for .NET. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat do vašich vlastních projektů.

 Chcete-li začít, ujistěte se, že máte Aspose.Words for .NET nainstalovaný a nakonfigurovaný ve svém vývojovém prostředí. Pokud jste tak ještě neučinili, stáhněte si a nainstalujte knihovnu z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Vytvoření dokumentu a generátoru dokumentů

Nejprve vytvořte nový dokument a přidružený generátor dokumentů:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Vytvoření a použití číslovaného seznamu

Dále vytvořte číslovaný seznam založený na jedné ze šablon seznamu Microsoft Word a použijte jej na aktuální odstavec v nástroji pro tvorbu dokumentů:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## Krok 3: Specifikace úrovně seznamu

 Použijte nástroj pro tvorbu dokumentů`ListLevelNumber` vlastnost k určení úrovně seznamu a přidání textu do odstavce:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Opakujte tyto kroky pro určení úrovní seznamu a přidání textu na každé úrovni.

## Krok 4: Vytvoření a použití seznamu s odrážkami

Můžete také vytvořit a použít seznam s odrážkami pomocí jedné ze šablon seznamu v aplikaci Microsoft Word:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Krok 5: Přidání textu do úrovní seznamu s odrážkami

 Použijte`ListLevelNumber` vlastnost znovu určit úroveň seznamu s odrážkami a přidat text:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## Krok 6: Zastavte formátování seznamu

 Chcete-li zastavit formátování seznamu, nastavte`null` k`List` vlastnost generátoru dokumentů:

```csharp
builder. ListFormat. List = null;
```

## Krok 7: Uložení upraveného dokumentu

Uložte upravený dokument:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

Tak ! Úspěšně jste zadali úroveň seznamu v dokumentu aplikace Word pomocí Aspose.Words for .NET.

### Ukázkový zdrojový kód pro specifikaci úrovně seznamu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Vytvořte číslovaný seznam založený na jedné ze šablon seznamu Microsoft Word
// použijte jej na aktuální odstavec tvůrce dokumentů.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// V tomto seznamu je devět úrovní, pojďme si je všechny vyzkoušet.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Vytvořte seznam s odrážkami založený na jedné ze šablon seznamu Microsoft Word
// použijte jej na aktuální odstavec tvůrce dokumentů.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Toto je způsob, jak zastavit formátování seznamu.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### FAQ

#### Otázka: Jak mohu určit úroveň seznamu v Aspose.Words?

 A: Chcete-li určit úroveň seznamu v Aspose.Words, musíte vytvořit instanci souboru`List` třídy a dejte jí číslovaný seznam. Poté můžete použít`Paragraph.ListFormat.ListLevelNumber` vlastnost k určení úrovně každé položky seznamu. Tento seznam můžete přiřadit k části dokumentu, aby položky seznamu měly požadovanou úroveň.

#### Otázka: Je možné změnit formát číslování položek seznamu v Aspose.Words?

 Odpověď: Ano, můžete změnit formát číslování položek seznamu v Aspose.Words. The`ListLevel` třída k tomu nabízí několik vlastností, jako např`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`, atd. Pomocí těchto vlastností můžete nastavit formát číslování položek seznamu, jako jsou arabské číslice, římské číslice, písmena atd.

#### Otázka: Mohu přidat další úrovně do číslovaného seznamu v Aspose.Words?

 Odpověď: Ano, je možné přidat další úrovně do číslovaného seznamu v Aspose.Words. The`ListLevel` class umožňuje nastavit vlastnosti formátování pro každou úroveň seznamu. Můžete nastavit možnosti, jako je předpona, přípona, zarovnání, odsazení atd. To vám umožní vytvářet seznamy s více úrovněmi hierarchie.


