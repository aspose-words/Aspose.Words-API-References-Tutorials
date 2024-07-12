---
title: Kód pole
linktitle: Kód pole
second_title: Aspose.Words API pro zpracování dokumentů
description: Průvodce krok za krokem k získání kódu pole a výsledku pole ve vašich dokumentech aplikace Word pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/working-with-fields/field-code/
---

Zde je podrobný návod k vysvětlení zdrojového kódu C# níže, který používá funkci "Získat kód pole" Aspose.Words pro .NET. Ujistěte se, že pečlivě dodržujete každý krok, abyste dosáhli požadovaných výsledků.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém kódu musíte zadat adresář vašich dokumentů. Nahraďte hodnotu „VÁŠ ADRESÁŘ DOKUMENTŮ“ příslušnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Načtení dokumentu

Prvním krokem je nahrání dokumentu, kam chcete získat kódy polí.

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

Nezapomeňte nahradit "Hyperlinks.docx" názvem svého vlastního souboru.

## Krok 3: Procházení polí dokumentu

 Používáme a`foreach` loop pro procházení všech polí přítomných v dokumentu.

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

 Při každé iteraci smyčky získáme kód pole pomocí`GetFieldCode()` metoda. Výsledek pole uložíme také do proměnné.

### Příklad zdrojového kódu pro Get Field Code s Aspose.Words pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument.
Document doc = new Document(dataDir + "Hyperlinks.docx");

// Procházet poli dokumentu.
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     //Udělejte něco s kódem pole a výsledkem.
}
```

V tomto příkladu jsme načetli dokument a poté cyklicky prošli všemi poli v dokumentu. Při každé iteraci jsme dostali kód a výsledek pole. Můžete přidat vlastní logiku pro zpracování polí kódu a výsledků podle potřeby.

Tímto končí náš průvodce používáním funkce „Získat kód pole“ s Aspose.Words pro .NET.

### FAQ

#### Otázka: Jak mohu vložit pole do dokumentu aplikace Word pomocí Aspose.Words for .NET?

 A: Chcete-li vložit pole do dokumentu aplikace Word pomocí Aspose.Words for .NET, můžete použít`DocumentBuilder.InsertField` metoda specifikující příslušný kód pole. Můžete například použít`builder.InsertField("MERGEFIELD CustomerName")` pro vložení slučovacího pole do dokumentu.

#### Otázka: Jak mohu aktualizovat pole v dokumentu pomocí Aspose.Words for .NET?

 A: Chcete-li aktualizovat pole dokumentu pomocí Aspose.Words pro .NET, můžete použít`Document.UpdateFields` metoda. Tím se aktualizují všechna pole přítomná v dokumentu, jako jsou slučovací pole, datová pole atd.

#### Otázka: Jak mohu získat hodnotu konkrétního pole v Aspose.Words pro .NET?

 A: Chcete-li získat hodnotu konkrétního pole v Aspose.Words pro .NET, můžete použít`Field.GetResult` metodou zadáním indexu pole v`Document.Range.Fields` sbírka. Můžete například použít`string value = document.Range.Fields[0].GetResult()` k načtení hodnoty prvního pole v dokumentu.

#### Otázka: Jak mohu odstranit pole z dokumentu pomocí Aspose.Words for .NET?

 A: Chcete-li odstranit pole z dokumentu pomocí Aspose.Words for .NET, můžete použít`Field.Remove` způsob upřesňující`Field` objekt, který chcete odstranit. Tím pole z dokumentu odstraníte.