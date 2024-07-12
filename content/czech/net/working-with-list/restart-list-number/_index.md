---
title: Restartovat číslo seznamu
linktitle: Restartovat číslo seznamu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se resetovat číslo seznamu v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-list/restart-list-number/
---
V tomto podrobném tutoriálu vám ukážeme, jak resetovat číslo seznamu v dokumentu aplikace Word pomocí Aspose.Words for .NET. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat do vašich vlastních projektů.

 Chcete-li začít, ujistěte se, že máte Aspose.Words for .NET nainstalovaný a nakonfigurovaný ve svém vývojovém prostředí. Pokud jste tak ještě neučinili, stáhněte si a nainstalujte knihovnu z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Vytvoření dokumentu a generátoru dokumentů

Nejprve vytvořte nový dokument a přidružený generátor dokumentů:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Vytvoření a přizpůsobení prvního seznamu

Dále vytvořte seznam založený na existující šabloně a poté přizpůsobte jeho úrovně:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## Krok 3: Přidání položek do prvního seznamu

Pomocí nástroje pro tvorbu dokumentů přidejte položky do prvního seznamu a odeberte čísla seznamu:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Krok 4: Vytvoření a přizpůsobení druhého seznamu

Chcete-li znovu použít první seznam resetováním čísla, vytvořte kopii původního rozvržení seznamu:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

V případě potřeby můžete také provést další změny ve druhém seznamu.

## Krok 5: Přidání položek do druhého seznamu

Pomocí nástroje pro tvorbu dokumentů znovu přidejte položky do druhého seznamu a odstraňte čísla seznamu:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Krok 6: Uložte upravený dokument

Nakonec upravený dokument uložte:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

Tak ! Úspěšně jste resetovali číslo seznamu v dokumentu aplikace Word pomocí Aspose.Words for .NET.

### Ukázkový zdrojový kód pro resetování čísla seznamu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Vytvořte seznam na základě šablony.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// Chcete-li znovu použít první seznam, musíme restartovat číslování vytvořením kopie původního formátování seznamu.
List list2 = doc.Lists.AddCopy(list1);

// Novou soupisku můžeme jakkoli upravit, včetně nastavení nového startovního čísla.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### FAQ

#### Otázka: Jak mohu restartovat číslování seznamu v Aspose.Words?

 A: Chcete-li restartovat číslování seznamu v Aspose.Words, můžete použít`ListRestartAtNumber` metoda`List` třída. Tato metoda umožňuje nastavit novou hodnotu číselníku, od které se má seznam restartovat. Můžete například použít`list.ListRestartAtNumber(1)` pro obnovení číslování od 1.

#### Otázka: Je možné upravit předponu a příponu číslování restartovaných seznamů v Aspose.Words?

 Odpověď: Ano, můžete upravit předponu a příponu číslování restartovaných seznamů v Aspose.Words. The`ListLevel` třída nabízí vlastnosti jako např`ListLevel.NumberPrefix`a`ListLevel.NumberSuffix`které umožňují zadat předponu a příponu pro každou úroveň v seznamu. Tyto vlastnosti můžete použít k přizpůsobení předpony a přípony podle potřeby.

#### Otázka: Jak mohu zadat konkrétní hodnotu číslování, od které má být seznam restartován?

 A: Chcete-li zadat konkrétní číselnou hodnotu, od které se má seznam restartovat, můžete použít`ListRestartAtNumber` metoda předávající požadovanou hodnotu jako argument. Chcete-li například restartovat číslování od 5, můžete použít`list.ListRestartAtNumber(5)`.

#### Otázka: Je možné restartovat víceúrovňové číslování seznamů v Aspose.Words?

 Odpověď: Ano, Aspose.Words podporuje restartování číslování více úrovní seznamu. Můžete použít`ListRestartAtNumber` metoda na každé úrovni seznamu pro opětovné zahájení číslování jednotlivě. Můžete například použít`list.Levels[0].ListRestartAtNumber(1)` restartujte první úroveň seznamu od 1 a`list.Levels[1].ListRestartAtNumber(1)` restartovat seznam druhé úrovně počínaje 1 a tak dále.



