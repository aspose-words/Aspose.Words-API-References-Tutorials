---
title: Citát
linktitle: Citát
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat nabídku s Aspose.Words pro .NET Podrobný průvodce.
type: docs
weight: 10
url: /cs/net/working-with-markdown/quote/
---

V tomto příkladu si vysvětlíme, jak používat funkci citace s Aspose.Slova pro .NET Quote se používají ke zvýraznění částí textu tak, že je obklopíte speciálním okrajem.

## Krok 1: Použití generátoru dokumentů

Nejprve použijeme generátor dokumentů k přidání obsahu do našeho dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Použití výchozího stylu citace

Pro použití formátování citací na text použijeme výchozí styl odstavce nazvaný "Citace".

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## Krok 3: Vytvoření stylů pro vnořené úrovně

 Můžeme vytvořit styly pro vnořené úrovně pomocí`Styles.Add` metoda`Document` objekt. V tomto příkladu vytváříme styl nazvaný "Citace1", který představuje úroveň vnořené nabídky.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Příklad zdrojového kódu pro citace s Aspose.Words pro .NET


```csharp
// K přidání obsahu do dokumentu použijte tvůrce dokumentů.
DocumentBuilder builder = new DocumentBuilder();

// Ve výchozím nastavení dokument ukládá styl blockquote pro první úroveň.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Vytvářejte styly pro vnořené úrovně prostřednictvím dědičnosti stylů.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

gratuluji! Nyní jste se naučili používat funkci citací s Aspose.Words pro .NET.


### FAQ

#### Otázka: Co je to citace v Markdown?

Odpověď: Citace v Markdown je způsob, jak zvýraznit pasáže textu z jiných zdrojů nebo odkazovat na slavné citáty.

#### Otázka: Jak používat uvozovky v Markdown?

Odpověď: Chcete-li použít citaci v Markdown, uzavřete text citace do lomených závorek (`>`). Každý řádek citace musí začínat šipkou.

#### Otázka: Podporují uvozovky Markdown atributy?

Odpověď: Citace Markdown nepodporují konkrétní atributy. Jsou jednoduše zvýrazněny formátováním citovaného textu.

#### Q: Můžete vložit uvozovky do Markdown?

Odpověď: Ano, je možné vnořit uvozovky do Markdown přidáním další úrovně lomených závorek (`>`).