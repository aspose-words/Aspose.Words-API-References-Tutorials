---
title: Vložit pokročilé pole bez Tvůrce dokumentů
linktitle: Vložit pokročilé pole bez Tvůrce dokumentů
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vložit pokročilé pole do dokumentů aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Zde je podrobný návod k vysvětlení zdrojového kódu C# níže, který používá funkci "Pokročilé vkládání polí bez DocumentBuilder" Aspose.Words for .NET. Ujistěte se, že pečlivě dodržujete každý krok, abyste dosáhli požadovaných výsledků.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém kódu musíte zadat adresář vašich dokumentů. Nahraďte hodnotu „VÁŠ ADRESÁŘ DOKUMENTŮ“ příslušnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření dokumentu a odstavce

Začneme vytvořením nového dokumentu a načtením prvního odstavce.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Krok 3: Vložení rozšířeného pole

 Používáme`AppendField()` metoda pro vložení rozšířeného pole do odstavce.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

Poté nakonfigurujeme různé vlastnosti rozšířeného pole zadáním požadovaných hodnot.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 Nakonec zavoláme`Update()` způsob aktualizace pole.

```csharp
field. Update();
```

### Příklad zdrojového kódu pro vložení pokročilého pole bez DocumentBuilder s Aspose.Words for .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvoření dokumentu.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Vložte pokročilé pole.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

V tomto příkladu jsme vytvořili nový dokument, vložili pokročilé pole bez použití DocumentBuilder, nakonfigurovali různé vlastnosti pole a uložili dokument se zadaným názvem souboru.

Tímto končí náš průvodce, jak používat funkci "Vložit pokročilé pole bez DocumentBuilder" s Aspose.Words pro .NET.

### FAQ

#### Otázka: Co je to pokročilé pole v Aspose.Words?

A: Pole Advance v Aspose.Words je speciální typ pole, které vám umožňuje provádět výpočty, zahrnout podmínky a provádět složité operace v dokumentu aplikace Word. Nabízí velkou flexibilitu pro vytváření dynamických a vlastních polí.

#### Otázka: Jak vložit pokročilé pole do dokumentu aplikace Word bez použití Tvůrce dokumentů v Aspose.Words?

Odpověď: Chcete-li vložit rozšířené pole do dokumentu aplikace Word bez použití Tvůrce dokumentů v Aspose.Words, můžete postupovat takto:

1. Importujte třídu Document a Field z oboru názvů Aspose.Words.Fields.
2. Vytvořte instanci dokumentu načtením existujícího dokumentu.
3. Pomocí metody InsertField vložte rozšířené pole zadáním kódu rozšířeného pole.
4. Uložte dokument.

#### Otázka: Jak získat výsledek pokročilého pole v dokumentu aplikace Word?

Odpověď: Chcete-li získat výsledek pokročilého pole v dokumentu aplikace Word, můžete použít vlastnost Výsledek dostupnou ve třídě Pole. Tato vlastnost vrací vypočítaný výsledek pole.

#### Otázka: Mohu upravit vzorec rozšířeného pole po jeho vložení do dokumentu aplikace Word?

Odpověď: Ano, vzorec pokročilého pole můžete upravit po jeho vložení do dokumentu aplikace Word. Můžete to udělat tak, že přistoupíte k vlastnosti FieldCode třídy Field a aktualizujete vzorec úpravou textu vzorce.