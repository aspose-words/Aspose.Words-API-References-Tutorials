---
title: Víceúrovňové formátování seznamu v dokumentu aplikace Word
linktitle: Víceúrovňové formátování seznamu v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit víceúrovňový seznam a použít vlastní formátování v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/document-formatting/multilevel-list-formatting/
---
V tomto tutoriálu vám ukážeme, jak používat víceúrovňové formátování seznamu ve funkci dokumentu aplikace Word pomocí Aspose.Words pro .NET. Chcete-li porozumět zdrojovému kódu a použít změny, postupujte podle následujících kroků.

## Krok 1: Vytvoření a konfigurace dokumentu

Chcete-li začít, vytvořte nový dokument a přidružený objekt DocumentBuilder. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Formátování víceúrovňového seznamu

Nyní použijeme víceúrovňové formátování seznamu pomocí metod dostupných v objektu DocumentBuilder. Zde je postup:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## Krok 3: Uložení dokumentu

 Po vložení pole formuláře pro zadání textu uložte dokument na požadované místo pomocí`Save` metoda. Ujistěte se, že jste zadali správnou cestu k souboru:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Příklad zdrojového kódu pro víceúrovňové formátování seznamu pomocí Aspose.Words pro .NET

Zde je kompletní zdrojový kód pro funkci víceúrovňového formátování seznamu pomocí Aspose.Words pro .NET:


```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

tímto kódem budete moci vytvořit víceúrovňový seznam a použít správné formátování pro každou úroveň pomocí Aspose.Words for .NET.


## Závěr

V tomto tutoriálu jsme prozkoumali proces využití funkce víceúrovňového formátování seznamu v dokumentu aplikace Word pomocí Aspose.Words pro .NET. Dodržováním nastíněných kroků můžete vytvořit dobře uspořádané seznamy s více úrovněmi, což zlepší strukturu a čitelnost vašich dokumentů.

### FAQ

#### Otázka: Co je víceúrovňový seznam v dokumentu aplikace Word?

Odpověď: Víceúrovňový seznam v dokumentu aplikace Word je hierarchický seznam, který umožňuje organizovat položky do různých úrovní podpoložek. Pomáhá prezentovat informace strukturovaným způsobem, což čtenářům usnadňuje pochopení obsahu.

#### Otázka: Mohu přizpůsobit vzhled víceúrovňového seznamu?

Odpověď: Ano, vzhled víceúrovňového seznamu v dokumentu aplikace Word můžete přizpůsobit. Použitím různých stylů, jako jsou odrážky, čísla nebo písmena, a úpravou odsazení a mezer můžete vytvořit vizuálně přitažlivý a uspořádaný seznam.

#### Otázka: Podporuje Aspose.Words for .NET další možnosti formátování seznamu?

Odpověď: Ano, Aspose.Words for .NET poskytuje komplexní sadu funkcí pro formátování seznamu. Podporuje různé typy seznamů, včetně seznamů s odrážkami, číslovaných seznamů a víceúrovňových seznamů. Můžete manipulovat s formátováním seznamů, přidávat nebo odebírat položky a přizpůsobovat jejich vzhled.

#### Otázka: Mohu použít Aspose.Words pro .NET pro práci s jinými prvky dokumentu?

Odpověď: Ano, Aspose.Words for .NET nabízí rozsáhlé možnosti pro práci s různými prvky dokumentu, jako jsou odstavce, tabulky, obrázky a další. Umožňuje vytvářet, upravovat a převádět dokumenty aplikace Word programově, čímž zjednodušuje úlohy zpracování dokumentů.