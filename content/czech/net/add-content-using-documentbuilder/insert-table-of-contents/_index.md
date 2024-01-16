---
title: Vložit obsah do dokumentu aplikace Word
linktitle: Vložit obsah do dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vložit obsah do dokumentů aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/add-content-using-documentbuilder/insert-table-of-contents/
---
V tomto komplexním tutoriálu se naučíte, jak vložit obsah do dokumentu aplikace Word pomocí Aspose.Words for .NET. Provedeme vás celým procesem a poskytneme vám potřebné úryvky kódu C#. Na konci této příručky budete schopni vygenerovat obsah s příslušnými nadpisy a čísly stránek.

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Knihovna Aspose.Words for .NET nainstalovaná ve vašem systému.

## Krok 1: Vytvořte nový dokument a DocumentBuilder
Chcete-li začít, vytvořte nový dokument pomocí třídy Document a inicializujte objekt DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Vložte obsah
Dále použijte metodu InsertTableOfContents třídy DocumentBuilder k vložení obsahu. Zadejte požadované možnosti formátování v rámci metody:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Krok 3: Přidejte obsah dokumentu
Po vložení obsahu přidejte skutečný obsah dokumentu. Nastavte vhodné styly nadpisů pomocí StyleIdentifier:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Krok 4: Aktualizujte obsah
Nově vložený obsah bude zpočátku prázdný. Chcete-li jej naplnit, aktualizujte pole v dokumentu:

```csharp
doc.UpdateFields();
```

## Krok 5: Uložte dokument
Po vložení obsahu a aktualizaci polí uložte dokument do souboru pomocí metody Save třídy Document:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Příklad zdrojového kódu pro vložení obsahu pomocí Aspose.Words pro .NET
Zde je úplný zdrojový kód pro vložení obsahu pomocí Aspose.Words pro .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inicializujte DocumentBuilder pomocí objektu Document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Vložit obsah
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Vlastní obsah dokumentu začněte na druhé stránce.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// Nově vložený obsah bude zpočátku prázdný.
// Je třeba jej vyplnit aktualizací polí v dokumentu.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak vložit obsah do dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete nyní vygenerovat obsah s příslušnými nadpisy a čísly stránek pro vaše dokumenty.

### Časté dotazy pro vložení obsahu do dokumentu aplikace Word

#### Otázka: Mohu přizpůsobit vzhled obsahu?

 Odpověď: Ano, vzhled obsahu můžete upravit úpravou možností formátování uvedených v`InsertTableOfContents` metoda. Parametry vám umožňují ovládat čísla stránek, odsazení a další styly.

#### Otázka: Co když chci do obsahu zahrnout konkrétní úrovně nadpisů?

 Odpověď: Můžete určit požadované úrovně nadpisů, které mají být zahrnuty do obsahu, úpravou hodnoty v rámci`InsertTableOfContents` metoda. Například pomocí`"\\o \"1-3\""` bude zahrnovat úrovně nadpisů 1 až 3.

#### Otázka: Mohu obsah aktualizovat automaticky, pokud provedu změny v obsahu dokumentu?

 Odpověď: Ano, obsah můžete aktualizovat automaticky zavoláním na`UpdateFields` metoda na dokumentu. Tím zajistíte, že všechny změny provedené v obsahu dokumentu, jako je přidání nebo odebrání nadpisů, se projeví v obsahu.

#### Otázka: Jak mohu odlišně stylizovat úrovně nadpisů v obsahu?

 Odpověď: Úrovně nadpisů můžete stylovat odlišně pomocí různých stylů odstavců pro každou úroveň nadpisu. Přiřazením různé`StyleIdentifier` hodnoty k`ParagraphFormat` z`DocumentBuilder`, můžete vytvořit odlišné styly pro každou úroveň nadpisu.

#### Otázka: Je možné přidat další formátování k nadpisům v obsahu?

 Odpověď: Ano, k nadpisům v obsahu můžete přidat další formátování, jako jsou styly písma, barvy nebo jiné vlastnosti. Úpravou`Font` vlastnosti`DocumentBuilder`, můžete na nadpisy použít vlastní formátování.