---
title: Nadpis setextu
linktitle: Nadpis setextu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat záhlaví Setext k formátování dokumentů pomocí Aspose.Words for .NET Podrobný průvodce.
type: docs
weight: 10
url: /cs/net/working-with-markdown/setext-heading/
---

V tomto tutoriálu vás provedeme tím, jak používat funkci Setext Heading s Aspose.Words pro .NET. Setext Heading jsou alternativní metodou formátování titulků v dokumentech Markdown.

## Krok 1: Použití generátoru dokumentů

Nejprve použijeme generátor dokumentů k přidání obsahu do našeho dokumentu.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Použití stylu nadpisu Setext

K vytvoření nadpisu úrovně 1 v našem dokumentu použijeme výchozí styl odstavce "Nadpis 1".

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## Krok 3: Resetování stylů

Obnovili jsme dříve použité styly písem, abychom se vyhnuli nechtěné kombinaci stylů mezi odstavci.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Krok 4: Přizpůsobení úrovní nadpisů Setextu

Úrovně nadpisů Setextu můžeme přizpůsobit přidáním nových stylů odstavců na základě existujících stylů nadpisů. V tomto příkladu vytváříme styl "SetextHeading1" založený na stylu "Nadpis 1", který bude reprezentovat nadpis úrovně 1 ve formátu Setext.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Krok 5: Uložení dokumentu

Nakonec můžeme dokument uložit v požadovaném formátu.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Příklad zdrojového kódu pro titulky Setext s Aspose.Words pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// K přidání obsahu do dokumentu použijte tvůrce dokumentů.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// Obnovte styly z předchozího odstavce, aby se styly mezi odstavci nekombinovaly.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// Obnovte styly z předchozího odstavce, aby se styly mezi odstavci nekombinovaly.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// Úroveň nadpisu Setex bude resetována na 2, pokud má základní odstavec úroveň nadpisu vyšší než 2.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### FAQ

#### Otázka: Co je záhlaví Setext Markdown?

Odpověď: Záhlaví Setext Markdown je alternativní způsob, jak vytvořit nadpisy v dokumentu Markdown. Používá znaky podtržení (= nebo -) k označení různých úrovní nadpisů.

#### Otázka: Jak používat záhlaví Setext Markdown?

Odpověď: Chcete-li použít nadpisy Setext Markdown, umístěte pod text nadpisu podtržítka. Pro záhlaví 1. úrovně použijte rovnítko (=) a pro záhlaví 2. úrovně pomlčky (-).

#### Otázka: Existují nějaká omezení při používání záhlaví Setext Markdown?

Odpověď: Nadpisy Setext Markdown mají omezení z hlediska hierarchie nadpisů a nejsou tak vizuálně odlišné jako standardní nadpisy Markdown.

#### Otázka: Mohu přizpůsobit vzhled záhlaví Setext Markdown?

Odpověď: Ve standardním Markdown není možné upravit vzhled záhlaví Setext Markdown. Mají předdefinovaný vzhled na základě použitých znaků podtržení.

#### Otázka: Podporují hlavičky Setext Markdown všechny editory Markdown?

Odpověď: Podpora záhlaví Setext Markdown se může mezi editory Markdown lišit. Abyste si byli jisti, zkontrolujte konkrétní dokumentaci vydavatele.