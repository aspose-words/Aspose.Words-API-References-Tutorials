---
title: Vložený kód
linktitle: Vložený kód
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vkládat kód pomocí Aspose.Words for .NET Podrobný průvodce.
type: docs
weight: 10
url: /cs/net/working-with-markdown/inline-code/
---

V tomto příkladu vás provedeme tím, jak používat funkci vloženého kódu s Aspose.Words pro .NET. Vložený kód se používá k vizuální reprezentaci částí kódu uvnitř odstavce.

## Krok 1: Použití generátoru dokumentů

Nejprve použijeme generátor dokumentů k přidání obsahu do našeho dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Přidejte styl pro vložený kód

 Přidáme vlastní styl pro vložený kód pomocí`Styles.Add` metoda`Document` objekt. V tomto příkladu vytváříme styl nazvaný "InlineCode" pro vložený kód s výchozím zpětným zaškrtnutím.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Krok 3: Přidejte vložený kód

Nyní můžeme přidat vložený kód pomocí vlastního stylu „InlineCode“. V tomto příkladu přidáme dva kusy textu s různým počtem zpětných zatržení.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Příklad zdrojového kódu pro Inline Code s Aspose.Words pro .NET

```csharp
// K přidání obsahu do dokumentu použijte tvůrce dokumentů.
DocumentBuilder builder = new DocumentBuilder();

// Chybí počet zpětných tahů, ve výchozím nastavení bude použit jeden zpětný tah.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// Budou 3 zpětné tahy.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

gratuluji! Nyní jste se naučili, jak používat funkce vloženého kódu s Aspose.Words pro .NET.


### FAQ

#### Otázka: Jak mohu použít vložený kód v Aspose.Words?

 A: Chcete-li použít vložený kód v Aspose.Words, můžete použít vhodné značky k obklopení textu, který má být formátován jako vložený kód. Můžete například použít`<code>` nebo`<kbd>` tag na obklopující text, který má být formátován jako vložený kód.

#### Otázka: Je možné v Aspose.Words určit písmo nebo barvu vloženého kódu?

 Odpověď: Ano, můžete určit písmo nebo barvu vloženého kódu v Aspose.Words. Můžete použít`Font.Name`a`Font.Color` vlastnosti`Run` objekt pro nastavení písma a barvy vloženého kódu. Můžete například použít`run.Font.Name = "Courier New"` k určení písma pro vložený kód a`run.Font.Color = Color.Blue` určení barvy.

#### Otázka: Mohu použít vložený kód v odstavci obsahujícím jiné textové prvky?

 Odpověď: Ano, vložený kód můžete použít v odstavci obsahujícím jiné textové prvky. Můžete vytvořit více`Run` objekty, které reprezentují různé části odstavce, pak použijte značky vloženého kódu k formátování pouze konkrétních částí jako vloženého kódu. Poté je můžete přidat do odstavce pomocí`Paragraph.AppendChild(run)` metoda.