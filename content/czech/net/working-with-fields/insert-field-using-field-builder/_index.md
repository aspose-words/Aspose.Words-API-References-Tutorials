---
title: Vložit pole pomocí Tvůrce polí
linktitle: Vložit pole pomocí Tvůrce polí
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vkládat vlastní pole do dokumentů aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fields/insert-field-using-field-builder/
---

Zde je podrobný návod k vysvětlení zdrojového kódu C# níže, který používá funkci "Vložit pole pomocí FieldBuilder" Aspose.Words for .NET. Ujistěte se, že pečlivě dodržujete každý krok, abyste dosáhli požadovaných výsledků.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém kódu musíte zadat adresář vašich dokumentů. Nahraďte hodnotu „VÁŠ ADRESÁŘ DOKUMENTŮ“ příslušnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření dokumentu

Začneme vytvořením nového dokumentu.

```csharp
Document doc = new Document();
```

## Krok 3: Vytvoření pole IF pomocí FieldBuilderu

Třídu FieldBuilder používáme ke konstrukci pole IF se dvěma vnořenými poli MERGEFIELD. V tomto příkladu pole KDYŽ zobrazuje jméno a příjmení na základě podmínky.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Krok 4: Vložení pole IF do dokumentu

 Používáme`BuildAndInsert()` metoda k sestavení a vložení pole IF na určité místo v dokumentu.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Příklad zdrojového kódu pro vložení pole pomocí FieldBuilder s Aspose.Words for .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvoření dokumentu.
Document doc = new Document();

// Konstrukce IF pole pomocí FieldBuilderu.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// Vložte pole IF do dokumentu.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

V tomto příkladu jsme vytvořili nový dokument, vytvořili pole IF s vnořenými poli MERGEFIELD a poté jsme toto pole vložili do dokumentu na určené místo. Dokument se poté uloží pod určitým názvem souboru.

### FAQ

#### Otázka: Co je konstruktor pole v Aspose.Words?

A: Field Builder v Aspose.Words je výkonný nástroj pro vytváření a manipulaci s poli v dokumentu aplikace Word. Nabízí pokročilé funkce pro vytváření a přizpůsobení polí, včetně vkládání kódů polí a správy možností formátování.

#### Otázka: Jaké typy polí lze vložit pomocí nástroje pro tvorbu polí?

A: Tvůrce polí v Aspose.Words umožňuje vkládat různé typy polí do dokumentu aplikace Word. Zde je několik příkladů běžně používaných typů polí:

- MERGEFIELD: používá se ke sloučení dat z externích zdrojů.
- DATE: zobrazí aktuální datum.
- PAGE: zobrazí číslo aktuální stránky.
- IF: umožňuje podmínit zobrazení obsahu podle podmínky.
- TOC: automaticky generuje obsah na základě stylů titulků dokumentu.

#### Otázka: Jak přizpůsobit pole vložená pomocí nástroje pro tvorbu polí?

Odpověď: Tvůrce polí nabízí možnosti přizpůsobení pro vložená pole. K nastavení voleb, jako je formátování pole, argumenty, přepínače a výchozí hodnoty, můžete použít metody a vlastnosti konstruktoru polí. Můžete například nastavit formát data, formát čísla, oddělovač tisíců atd.
  