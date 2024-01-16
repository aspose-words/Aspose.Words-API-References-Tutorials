---
title: Důrazy
linktitle: Důrazy
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat důrazy (tučné a kurzíva) s Aspose.Words pro .NET Podrobný průvodce.
type: docs
weight: 10
url: /cs/net/working-with-markdown/emphases/
---

V tomto příkladu vysvětlíme, jak používat důrazy s Aspose.Words pro .NET. zvýraznění se používá ke zdůraznění určitých částí textu, jako je tučné písmo a kurzíva.

## Krok 1: Inicializace dokumentu

 Nejprve dokument inicializujeme vytvořením instance souboru`Document` třída.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Krok 2: Použití generátoru dokumentů

Dále použijeme generátor dokumentů k přidání obsahu do našeho dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Přidejte text pomocí důrazů

Zvýraznění textu můžeme přidat změnou vlastností písma generátoru dokumentu. V tomto příkladu používáme tučné písmo a kurzívu ke zdůraznění různých částí textu.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## Krok 4: Uložení dokumentu

 Nakonec můžeme dokument uložit v požadovaném formátu. V tomto příkladu používáme`.md` rozšíření pro formát Markdown.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

gratuluji! Nyní jste se naučili, jak používat důrazy s Aspose.Words pro .NET.

### Příklad zdrojového kódu pro Emphases pomocí Aspose.Words pro .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### FAQ

#### Otázka: Jak zvýrazním text pomocí Markdown?

 A: Chcete-li zvýraznit text pomocí Markdown, jednoduše obklopte text příslušnými symboly. Použití`*` nebo`_` pro kurzívu,`**` nebo`__` pro tučné, a`~~` pro přeškrtnutí.

#### Otázka: Můžeme kombinovat různá zvýraznění ve stejném textu?

 Odpověď: Ano, je možné kombinovat různá zvýraznění ve stejném textu. Například můžete slovo zvýraznit tučným písmem a kurzívou pomocí obou`**` a`*`kolem slova.

#### Otázka: Jaké možnosti zvýraznění jsou v Markdown k dispozici?

Odpověď: Možnosti zvýraznění dostupné v Markdown jsou kurzívou (`*` nebo`_`), tučně (`**` nebo`__`) a přeškrtnutí (`~~`).

#### Otázka: Jak mám řešit případy, kdy text obsahuje speciální znaky používané Markdownem pro zvýraznění?

 Odpověď: Pokud váš text obsahuje speciální znaky používané Markdownem pro zvýraznění, můžete jim uniknout tak, že je předáte s a`\` . Například,`\*` zobrazí doslovnou hvězdičku.

#### Otázka: Můžeme upravit vzhled zvýraznění pomocí CSS?

Odpověď: Zvýraznění v Markdown se obvykle vykresluje pomocí výchozích stylů prohlížeče. Pokud převedete svůj Markdown do HTML, můžete upravit vzhled zvýraznění pomocí pravidel CSS.