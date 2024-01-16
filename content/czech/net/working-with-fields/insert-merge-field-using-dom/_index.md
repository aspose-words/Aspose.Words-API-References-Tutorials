---
title: Vložit slučovací pole pomocí DOM
linktitle: Vložit slučovací pole pomocí DOM
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vložit vlastní pole slučování polí do dokumentů aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fields/insert-merge-field-using-dom/
---

Zde je průvodce krok za krokem vysvětlující níže uvedený zdrojový kód C#, který používá funkci "Vložit pole slučovacího pole" Aspose.Words for .NET. Ujistěte se, že pečlivě dodržujete každý krok, abyste dosáhli požadovaných výsledků.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém kódu musíte zadat adresář vašich dokumentů. Nahraďte hodnotu „VÁŠ ADRESÁŘ DOKUMENTŮ“ příslušnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření dokumentu a DocumentBuilderu

Začneme vytvořením nového dokumentu a inicializací DocumentBuilderu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Přesunutí kurzoru na odstavec

 Používáme`MoveTo()` metodou DocumentBuilderu přesuneme kurzor na odstavec, kam chceme vložit pole pro sloučení pole.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Krok 4: Vložení pole sloučení polí

 Používáme DocumentBuilder's`InsertField()` metoda pro vložení pole slučovacího pole do odstavce.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Poté nakonfigurujeme vlastnosti pole sloučení polí zadáním příslušných možností, jako je název pole, text před a za polem a možnosti vertikálního formátování.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Nakonec zavoláme`Update()` způsob aktualizace pole.

```csharp
field. Update();
```

### Ukázkový zdrojový kód pro vložení pole sloučení pole s Aspose.Words pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte dokument a DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Přesuňte kurzor na odstavec.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Vložit pole sloučení pole.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Aktualizujte pole.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

V tomto příkladu jsme vytvořili nový dokument, přesunuli kurzor na požadovaný odstavec a pak do dokumentu vložili pole pro sloučení polí.

### FAQ

#### Otázka: Jak mohu vložit slučovací pole do dokumentu aplikace Word pomocí Aspose.Words for .NET s DOM?

Odpověď: Chcete-li vložit slučovací pole do dokumentu aplikace Word pomocí Aspose.Words for .NET s DOM, můžete postupovat takto:

1. Přejděte na odstavec, kam chcete vložit slučovací pole.
2.  Vytvořit`FieldMergeField` objekt.
3. Nastavte vlastnosti slučovacího pole, jako je název pole a možnosti formátování.
4.  Přidejte slučovací pole do odstavce pomocí`Paragraph.AppendChild` metoda.

#### Otázka: Jak mohu zadat zdrojová data pro slučovací pole v Aspose.Words pro .NET?

Odpověď: Chcete-li zadat zdrojová data pro slučovací pole v Aspose.Words pro .NET, můžete použít`FieldMergeField.FieldName` metoda pro nastavení názvu slučovacího pole, což je název pole v externím zdroji dat, jako je soubor CSV, databáze atd. Můžete také použít`FieldMergeField.Text` metodu pro přímé nastavení hodnoty slučovacího pole.

#### Otázka: Mohu upravit vzhled slučovacího pole v dokumentu aplikace Word pomocí Aspose.Words for .NET?

 Odpověď: Ano, vzhled slučovacího pole v dokumentu aplikace Word můžete upravit pomocí Aspose.Words for .NET. Můžete nastavit možnosti formátování, jako je velikost písmen, písmo, barva atd. pomocí vlastností souboru`FieldMergeField` objekt.

#### Otázka: Jak mohu zkontrolovat, zda bylo slučovací pole úspěšně vloženo do dokumentu aplikace Word pomocí Aspose.Words for .NET?

 Odpověď: Chcete-li zkontrolovat, zda bylo slučovací pole vloženo úspěšně, můžete procházet obsah dokumentu a hledat instance slučovacího pole. Můžete použít metody a vlastnosti`Document` objekt pro přístup k odstavcům, polím a dalším prvkům dokumentu.

#### Otázka: Má vložení slučovacího pole pomocí DOM vliv na strukturu dokumentu Word s Aspose.Words pro .NET?

Odpověď: Vložení slučovacího pole pomocí modelu DOM přímo neovlivní strukturu dokumentu aplikace Word. Do obsahu dokumentu však přidá nový prvek pole. Strukturu dokumentu můžete upravovat přidáním, odstraněním nebo úpravou stávajících prvků podle vašich potřeb.