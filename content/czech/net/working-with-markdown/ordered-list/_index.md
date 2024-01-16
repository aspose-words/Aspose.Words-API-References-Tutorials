---
title: Objednaný seznam
linktitle: Objednaný seznam
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit uspořádaný seznam pomocí Aspose.Words for .NET Podrobný průvodce.
type: docs
weight: 10
url: /cs/net/working-with-markdown/ordered-list/
---

V tomto příkladu vysvětlíme, jak používat funkcionalitu uspořádaného seznamu s Aspose.Words pro .NET. Objednaný seznam vám umožňuje uspořádat položky sekvenčně podle čísel.

## Krok 1: Použití generátoru dokumentů

Nejprve použijeme generátor dokumentů k vytvoření nového dokumentu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Použití formátu seřazeného seznamu

 Použijeme formát uspořádaného seznamu pomocí nástroje pro tvorbu dokumentů`ApplyBulletDefault`metoda. Můžeme také přizpůsobit formát číslování tím, že přejdeme na úrovně seznamu a nastavíme požadovaný formát.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## Krok 3: Přidání položek do seznamu

 Položky můžeme do seznamu přidávat pomocí generátoru dokumentů`Writeln` metoda.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Krok 4: Odsazení seznamu

 Seznam můžeme odsadit pomocí generátoru dokumentů`ListIndent` metoda.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Krok 5: Uložení dokumentu

Nakonec můžeme dokument uložit v požadovaném formátu.

### Příklad zdrojového kódu pro uspořádaný seznam s Aspose.Words pro .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

gratuluji! Nyní jste se naučili, jak používat funkci uspořádaného seznamu s Aspose.Words pro .NET.


### FAQ

#### Otázka: Jak vytvořit uspořádaný seznam v Markdown?

Odpověď: Chcete-li vytvořit uspořádaný seznam v Markdown, začněte každou položku seznamu číslem následovaným tečkou (`1.`, `2.`, `3.`), za kterým následuje mezera.

#### Otázka: Můžeme v Markdown vnořit uspořádané seznamy?

Odpověď: Ano, v Markdown je možné vnořit uspořádané seznamy přidáním čtyř odsazených mezer před každou vnořenou položku seznamu.

#### Otázka: Jak přizpůsobit číslování objednaných seznamů?

A: Ve standardním Markdown se číslování uspořádaných seznamů generuje automaticky. Některé editory Markdown vám však umožňují upravit jej pomocí konkrétních rozšíření.

#### Otázka: Podporují uspořádané seznamy v Markdown odsazení?

Odpověď: Ano, uspořádané seznamy v Markdown podporují odsazení. Posun doleva můžete přidat pomocí mezer nebo tabulátorů.

#### Otázka: Lze k položkám seznamu přidat odkazy nebo vložený text?

Odpověď: Ano, do seznamu položek můžete přidat odkazy nebo vložený text pomocí příslušné syntaxe Markdown.