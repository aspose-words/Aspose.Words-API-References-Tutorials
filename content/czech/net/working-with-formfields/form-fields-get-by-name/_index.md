---
title: Pole formuláře získat podle názvu
linktitle: Pole formuláře získat podle názvu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak načíst a upravit pole formuláře podle názvu v dokumentech aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-formfields/form-fields-get-by-name/
---

V tomto podrobném tutoriálu vás provedeme tím, jak používat Aspose.Words pro .NET k načítání polí formuláře podle názvu z dokumentu aplikace Word. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat do vašich vlastních projektů.

 Chcete-li začít, ujistěte se, že máte Aspose.Words for .NET nainstalovaný a nastavený ve svém vývojovém prostředí. Pokud jste tak neučinili, stáhněte si a nainstalujte knihovnu z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Inicializace objektu dokumentu

 Nejprve inicializujte`Document` objekt poskytnutím cesty ke zdrojovému dokumentu obsahujícímu pole formuláře:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## Krok 2: Načtení polí formuláře

 Dále přejděte na`FormFields` vlastnictvím`Range` objekt v dokumentu pro načtení všech polí formuláře:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

Pole formuláře můžete načíst buď podle indexu, nebo podle názvu. V tomto příkladu načteme pole formuláře pomocí obou metod:

```csharp
FormField formField1 = documentFormFields[3]; // Načítání podle indexu
FormField formField2 = documentFormFields["Text2"]; // Načítání podle jména
```

## Krok 3: Úprava vlastností pole formuláře

Jakmile načtete pole formuláře, můžete upravit jejich vlastnosti podle potřeby. V tomto příkladu změníme velikost písma`formField1` do 20 a barvu písma`formField2` na červenou:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## Krok 4: Uložení dokumentu

Nakonec upravený dokument uložte:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

A je to! Úspěšně jste získali pole formuláře podle názvu a upravili jste jejich vlastnosti v dokumentu aplikace Word pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro pole formuláře Get By Name pomocí Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Neváhejte použít tento kód ve svých vlastních projektech a upravit jej podle svých konkrétních požadavků.

### FAQ

#### Otázka: Jak mohu získat pole formuláře podle názvu v Aspose.Words?

 A: Chcete-li získat pole formuláře podle názvu v Aspose.Words, můžete použít`Document.Range.FormFields[name]` metoda. Tato metoda vrátí pole formuláře odpovídající zadanému názvu.

#### Otázka: Co když pole formuláře se zadaným názvem v dokumentu neexistuje?

 Odpověď: Pokud pole formuláře se zadaným názvem v dokumentu neexistuje,`Document.Range.FormFields[name]` metoda se vrátí`null`. Tento výsledek můžete zkontrolovat, abyste zvládli případy, kdy není pole formuláře nalezeno.

#### Otázka: Jak mohu upravit vlastnosti nalezeného pole formuláře?

Odpověď: Jakmile získáte pole formuláře podle názvu, můžete přistupovat k jeho jednotlivým vlastnostem a upravovat je. Můžete například změnit hodnotu pole, povolit nebo zakázat jeho viditelnost nebo upravit další vlastnosti podle potřeby.

#### Otázka: Mohu v dokumentu získat více polí formuláře se stejným názvem?

 Odpověď: Ano, v dokumentu je možné mít více polí formuláře se stejným názvem. V tomto případě je`Document.Range.FormFields[name]` metoda vrátí první nalezené pole formuláře se zadaným názvem. Pokud máte více polí formuláře se stejným názvem, budete to muset vzít v úvahu při manipulaci s poli.

#### Otázka: Jak mohu iterovat všechna pole formuláře v dokumentu?

 A: Chcete-li iterovat přes všechna pole formuláře v dokumentu, můžete použít a`foreach` smyčka na`Document.Range.FormFields` sbírka. To vám umožní přistupovat ke každému poli formuláře jednotlivě a provádět operace s každým z nich.