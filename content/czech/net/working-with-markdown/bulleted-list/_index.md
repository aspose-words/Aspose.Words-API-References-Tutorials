---
title: Seznam s odrážkami
linktitle: Seznam s odrážkami
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit seznam s odrážkami pomocí Aspose.Words for .NET Podrobný průvodce.
type: docs
weight: 10
url: /cs/net/working-with-markdown/bulleted-list/
---

V tomto tutoriálu vám řekneme, jak vytvořit seznam s odrážkami pomocí Aspose.Words pro .NET. Seznam s odrážkami se používá k výpisu položek bez použití číslování.

## Krok 1: Použití generátoru dokumentů

Nejprve použijeme generátor dokumentů k přidání obsahu do našeho dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Použití výchozího seznamu s odrážkami

 Můžeme použít výchozí seznam s odrážkami pomocí nástroje pro tvorbu dokumentů`ApplyBulletDefault` metoda.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Krok 3: Přizpůsobení formátu odrážky

 Můžeme přizpůsobit formát odrážky přístupem k vlastnostem`ListFormat.List.ListLevels[0]`. V tomto příkladu používáme jako odrážku pomlčku „-“.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Krok 4: Přidání položek do seznamu

 Nyní můžeme přidat položky do seznamu s odrážkami pomocí nástroje pro tvorbu dokumentů`Writeln` metoda.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Krok 5: Odebrání odsazení ze seznamu

 Pokud chceme vytvořit podseznam, můžeme zvětšit odsazení pomocí`ListFormat.ListIndent()` metoda. V tomto příkladu přidáváme podseznam k položkám 2a a 2b.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Příklad zdrojového kódu pro Bulleted List pomocí Aspose.Words pro .NET


```csharp
// K přidání obsahu do dokumentu použijte tvůrce dokumentů.
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

gratuluji! Nyní jste se naučili, jak vytvořit seznam s odrážkami pomocí Aspose.Words pro .NET.

### FAQ

#### Otázka: Jak vytvořit seznam s odrážkami v Markdown?

Odpověď: Chcete-li vytvořit seznam s odrážkami v Markdown, začněte každou položku seznamu symbolem odrážky (`-`, `*` nebo`+`), za kterým následuje mezera.

#### Otázka: Můžete v Markdown vnořit seznamy s odrážkami?

Odpověď: Ano, v Markdown je možné vnořit seznamy s odrážkami přidáním čtyř odsazených mezer před každou položku vnořeného seznamu.

#### Otázka: Jak přizpůsobit symboly odrážek?

A: Ve standardním Markdown jsou symboly odrážek předdefinovány. Některé editory Markdown vám však umožňují přizpůsobit je pomocí konkrétních rozšíření.

#### Otázka: Podporují seznamy s odrážkami v Markdown odsazení?

Odpověď: Ano, seznamy s odrážkami v Markdown podporují odsazení. Posun doleva můžete přidat pomocí mezer nebo tabulátorů.

#### Otázka: Lze k položkám seznamu přidat odkazy nebo vložený text?

Odpověď: Ano, do seznamu položek můžete přidat odkazy nebo vložený text pomocí příslušné syntaxe Markdown.
