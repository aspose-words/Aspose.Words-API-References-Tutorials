---
title: Odsazený kód
linktitle: Odsazený kód
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat odsazený kód s Aspose.Words pro .NET Podrobný průvodce.
type: docs
weight: 10
url: /cs/net/working-with-markdown/indented-code/
---

V tomto příkladu vysvětlíme, jak používat funkci odsazeného kódu s Aspose.Words pro .NET. Odsazený kód se používá k vizuální reprezentaci bloků kódu se specifickým formátováním.

## Krok 1: Použití generátoru dokumentů

Nejprve použijeme generátor dokumentů k přidání obsahu do našeho dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Přidejte styl pro odsazený kód

Přidáme vlastní styl pro odsazený kód pomocí`Styles.Add` metoda`Document` objekt. V tomto příkladu vytváříme styl nazvaný "IndentedCode" pro odsazený kód.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Krok 3: Přidejte odsazený kód

Nyní můžeme přidat odsazený blok kódu pomocí vlastního stylu „IndentedCode“.

```csharp
builder.Writeln("This is an indented code block");
```

### Příklad zdrojového kódu pro odsazený kód s Aspose.Words pro .NET

```csharp
// K přidání obsahu do dokumentu použijte tvůrce dokumentů.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

gratuluji! Nyní jste se naučili, jak používat funkci odsazeného kódu s Aspose.Words pro .NET.


### FAQ

#### Otázka: Co je odsazený kód v Markdown?

Odpověď: Odsazený kód v Markdown je metoda formátování používaná k zobrazení kódu v dokumentu Markdown. Skládá se z odsazení každého řádku kódu mezerami nebo tabulátory.

#### Otázka: Jak používat odsazený kód v Markdown?

Odpověď: Chcete-li v Markdown použít odsazený kód, odsaďte každý řádek kódu mezerami nebo tabulátory.

#### Otázka: Jaké jsou výhody odsazeného kódu v Markdown?

Odpověď: Odsazený kód v Markdown zlepšuje čitelnost kódu a usnadňuje čtenářům porozumění.

#### Otázka: Jaký je rozdíl mezi odsazeným kódem a bloky kódu v Markdown?

Odpověď: Odsazený kód se používá pro malé úryvky kódu vložené do textu, zatímco bloky kódu se používají k zobrazení větších částí kódu v samostatném formátování.

#### Otázka: Je odsazený kód v Markdown podporován všemi editory Markdown?

Odpověď: Podpora odsazeného kódu v Markdown se může mezi editory Markdown lišit. Abyste si byli jisti, zkontrolujte konkrétní dokumentaci vydavatele.