---
title: Přejmenujte slučovací pole
linktitle: Přejmenujte slučovací pole
second_title: Aspose.Words API pro zpracování dokumentů
description: V tomto tutoriálu se naučíte, jak přejmenovat slučovací pole v dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fields/rename-merge-fields/
---

Zde je průvodce krok za krokem, který vysvětluje zdrojový kód C# níže, který používá funkci přejmenování slučovacích polí Aspose.Words pro .NET. Pečlivě dodržujte každý krok, abyste dosáhli požadovaných výsledků.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém kódu musíte zadat adresář vašich dokumentů. Nahraďte hodnotu „VÁŠ ADRESÁŘ DOKUMENTŮ“ příslušnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření dokumentu a vložení slučovacích polí

Začneme vytvořením nového dokumentu a pomocí a`DocumentBuilder` pro vložení slučovacích polí.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## Krok 3: Přejmenování slučovacích polí

Procházíme každým polem v rozsahu dokumentů, a pokud se jedná o slučovací pole, přejmenujeme pole přidáním "_Přejmenovaná" přípona.

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## Krok 4: Uložení dokumentu

 Nakonec zavoláme`Save()` způsob uložení upraveného dokumentu.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Příklad zdrojového kódu pro přejmenování slučovacích polí pomocí Aspose.Words pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte dokument a vložte slučovací pole.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Přejmenujte slučovací pole.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Uložte dokument.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Chcete-li přejmenovat slučovací pole v dokumentu pomocí Aspose.Words for .NET, postupujte takto.

### FAQ

#### Otázka: Jak mohu přejmenovat sloučená pole v dokumentu aplikace Word pomocí Aspose.Words for .NET?

 A: Chcete-li přejmenovat sloučená pole v dokumentu aplikace Word pomocí Aspose.Words for .NET, můžete procházet pole v dokumentu pomocí`FieldMergingArgs` třídy a použijte`FieldMergingArgs.FieldName` způsob přejmenování pole.

#### Otázka: Je možné pomocí Aspose.Words for .NET přejmenovat pouze určitá sloučená pole v dokumentu aplikace Word?

Odpověď: Ano, pomocí Aspose.Words for .NET je možné přejmenovat pouze určitá sloučená pole v dokumentu aplikace Word. Pole, která chcete přejmenovat, můžete filtrovat pomocí specifických kritérií, jako je název pole nebo jiné relevantní vlastnosti. Poté můžete odpovídající pole přejmenovat pomocí`FieldMergingArgs.FieldName` metoda.

#### Otázka: Jak mohu zkontrolovat, zda bylo sloučené pole úspěšně přejmenováno v dokumentu aplikace Word pomocí Aspose.Words for .NET?

 Odpověď: Chcete-li zkontrolovat, zda bylo sloučené pole úspěšně přejmenováno v dokumentu aplikace Word pomocí Aspose.Words for .NET, můžete použít`FieldMergedArgs` třídy a přístup k`FieldMergedArgs.IsMerged` vlastnost k určení, zda bylo pole přejmenováno pomocí hitu.

#### Otázka: Jaké jsou důsledky přejmenování sloučeného pole v dokumentu aplikace Word pomocí Aspose.Words for .NET?

Odpověď: Když přejmenujete sloučené pole v dokumentu aplikace Word pomocí Aspose.Words for .NET, změní se název pole v dokumentu, což může ovlivnit další funkce nebo procesy, které závisí na názvu pole. Před přejmenováním sloučených polí nezapomeňte zvážit tyto možné důsledky.

#### Otázka: Je možné obnovit původní název sloučeného pole po jeho přejmenování pomocí Aspose.Words for .NET?

Odpověď: Ano, je možné obnovit původní název sloučeného pole po jeho přejmenování pomocí Aspose.Words for .NET. Původní název pole můžete uložit do proměnné nebo seznamu a poté v případě potřeby použít tyto informace k obnovení původního názvu.