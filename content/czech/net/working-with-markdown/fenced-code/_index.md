---
title: Oplocený kód
linktitle: Oplocený kód
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat funkci chráněného kódu pomocí Aspose.Words for .NET Podrobný průvodce.
type: docs
weight: 10
url: /cs/net/working-with-markdown/fenced-code/
---

V tomto příkladu vás provedeme tím, jak používat funkci chráněného kódu s Aspose.Words for .NET. chráněný kód se používá k reprezentaci bloků kódu se specifickým formátováním.

## Krok 1: Použití generátoru dokumentů

Nejprve použijeme generátor dokumentů k přidání obsahu do našeho dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Přidání stylu pro chráněný kód

 Přidáme vlastní styl pro chráněný kód pomocí`Styles.Add` metoda`Document` objekt. V tomto příkladu vytváříme styl nazvaný "FencedCode" pro chráněný kód.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## Krok 3: Přidání chráněného kódu bez informací

Nyní můžeme přidat chráněný blok kódu bez informačního řetězce pomocí vlastního stylu „FencedCode“.

```csharp
builder.Writeln("This is an fenced code");
```

## Krok 4: Přidejte chráněný kód s informačním řetězcem

Můžeme také přidat chráněný blok kódu s řetězcem informací pomocí jiného vlastního stylu. V tomto příkladu vytváříme styl nazvaný "FencedCode.C#", který představuje blok kódu C#.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Příklad zdrojového kódu pro chráněný kód pomocí Aspose.Words pro .NET

```csharp
// K přidání obsahu do dokumentu použijte tvůrce dokumentů.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### FAQ

#### Otázka: Co je oddělený kód v Markdown?

Odpověď: Oddělovací kód v Markdown je metoda formátování používaná k zobrazení kódu v dokumentu Markdown. Skládá se z orámování kódu pomocí specifických oddělovačů.

#### Otázka: Jaké jsou výhody odděleného kódu v Markdown?

Odpověď: Kód s oddělovači v Markdown zlepšuje čitelnost kódu a usnadňuje čtenářům porozumění. Umožňuje také zachovat zvýraznění syntaxe v některých editorech Markdown.

#### Otázka: Jaký je rozdíl mezi odděleným a odsazeným kódem v Markdown?

Odpověď: Kód s oddělovači používá specifické oddělovače k uzavření kódu, zatímco odsazený kód zahrnuje odsazení každého řádku kódu mezerami nebo tabulátory.

#### Otázka: Je oddělovací kód v Markdown podporován všemi editory Markdown?

Odpověď: Podpora odděleného kódu v Markdown se může mezi editory Markdown lišit. Abyste si byli jisti, zkontrolujte konkrétní dokumentaci vydavatele.

