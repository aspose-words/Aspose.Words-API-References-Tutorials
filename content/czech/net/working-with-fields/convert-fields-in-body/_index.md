---
title: Převést pole v těle
linktitle: Převést pole v těle
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat Aspose.Words for .NET k převodu polí stránky na text v těle dokumentu aplikace Word.
type: docs
weight: 10
url: /cs/net/working-with-fields/convert-fields-in-body/
---

V tomto tutoriálu krok za krokem vás provedeme tím, jak používat funkci ConvertFieldsInBody Aspose.Words for .NET pomocí poskytnutého zdrojového kódu C#. Tato funkce umožňuje převést určitá pole v těle dokumentu na prostý text, což usnadňuje zpracování dokumentů. Chcete-li tuto funkci efektivně používat, postupujte podle následujících kroků.

## Krok 1: Předpoklady

Než začnete, ujistěte se, že jste nainstalovali Aspose.Words for .NET a že máte dokument připravený ke zpracování. Také se ujistěte, že máte cestu k adresáři svých dokumentů.

## Krok 2: Vložte dokument

Začněte deklarováním proměnné pro cestu k adresáři vašich dokumentů a poté tuto proměnnou použijte k inicializaci objektu Document ze zadaného dokumentu. V našem příkladu se dokument nazývá „Propojená pole.docx“.

```csharp
// Cesta k adresáři vašich dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument
Document doc = new Document(dataDir + "Linked fields.docx");
```

## Krok 3: Převeďte pole stránky na prostý text

 Nyní, když je dokument načten, můžeme přejít ke krokům převodu. Chcete-li převést pole stránky na prostý text v těle první sekce, můžete použít`Range.Fields` metodou získat všechna pole v zadaném rozsahu a poté odfiltrovat pole typu`FieldType.FieldPage` . Poté můžete použít`ForEach` metoda pro procházení každého pole a volání`Unlink()` způsob, jak jej převést na prostý text.

```csharp
// Předejte příslušné parametry pro převod polí stránky na prostý text v těle první sekce.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## Krok 4: Uložte upravený dokument

Jakmile převedete pole stránky na prostý text, můžete upravený dokument uložit pomocí`Save()` a zadáním cesty a názvu výstupního souboru. V našem příkladu jej uložíme jako „WorkingWithFields.ConvertFieldsInBody.docx“.

```csharp
// Uložte upravený dokument
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Příklad zdrojového kódu pro převod polí v těle pomocí Aspose.Words pro .NET

Zde je úplný příklad zdrojového kódu pro převod polí do těla pomocí Aspose.Words pro .NET:

```csharp
// Cesta k adresáři vašich dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument
Document doc = new Document(dataDir + "Linked fields.docx");

// Předejte příslušné parametry pro převod polí stránky na prostý text v těle první sekce.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### FAQ

#### Otázka: Je Aspose.Words kompatibilní s různými verzemi aplikace Microsoft Word?

Odpověď: Ano, Aspose.Words je kompatibilní s různými verzemi Microsoft Word, včetně Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 a Word 2019.

#### Otázka: Dokáže Aspose.Words zvládnout složité struktury polí?

A: Rozhodně! Aspose.Words poskytuje rozsáhlou podporu pro složité struktury polí, včetně vnořených polí, výpočtů a podmíněných výrazů. Výkonné API můžete využít pro práci s libovolným typem struktury pole.

#### Otázka: Podporuje Aspose.Words operace aktualizace pole?

Odpověď: Ano, Aspose.Words vám umožňuje programově aktualizovat pole. Pomocí API můžete snadno aktualizovat hodnoty polí, aktualizovat výpočty a provádět další operace související s poli.

#### Otázka: Mohu převést pole na prostý text pomocí Aspose.Words?

A: Určitě! Aspose.Words poskytuje metody pro převod polí na prostý text. To může být užitečné, když potřebujete extrahovat obsah bez jakéhokoli formátování nebo funkcí souvisejících s polem.

#### Otázka: Je možné generovat dokumenty aplikace Word s dynamickými poli pomocí Aspose.Words?

A: Rozhodně! Aspose.Words nabízí robustní funkce pro generování dokumentů aplikace Word s dynamickými poli. Můžete vytvářet šablony s předdefinovanými poli a dynamicky je plnit daty, což poskytuje flexibilní a efektivní řešení pro generování dokumentů.