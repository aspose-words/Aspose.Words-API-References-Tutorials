---
title: Získejte názvy polí hromadné korespondence
linktitle: Získejte názvy polí hromadné korespondence
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak získat názvy polí hromadné korespondence v dokumentech aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fields/get-mail-merge-field-names/
---

Zde je podrobný průvodce vysvětlením níže uvedeného zdrojového kódu C#, který používá funkci "Get Merge Field Names" Aspose.Words for .NET. Ujistěte se, že pečlivě dodržujete každý krok, abyste dosáhli požadovaných výsledků.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém kódu musíte zadat adresář vašich dokumentů. Nahraďte hodnotu „VÁŠ ADRESÁŘ DOKUMENTŮ“ příslušnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Načtení dokumentu

Prvním krokem je načtení dokumentu, kde chcete získat názvy slučovacích polí.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

Nezapomeňte nahradit "VÁŠ SOUBOR DOKUMENTU" názvem svého vlastního souboru.

## Krok 3: Získejte názvy slučovacích polí

 Používáme`GetFieldNames()` metoda k získání pole obsahujícího názvy slučovacích polí přítomných v dokumentu.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 The`fieldNames` proměnná nyní obsahuje názvy slučovacích polí.

### Příklad zdrojového kódu pro získání názvů slučovacích polí s Aspose.Words pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Získejte názvy slučovacích polí.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Zobrazte počet slučovacích polí.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 V tomto příkladu jsme načetli dokument a získali názvy slučovacích polí pomocí`GetFieldNames()` a zobrazil počet slučovacích polí přítomných v dokumentu.

Tímto končí náš průvodce používáním funkce „Získat názvy polí sloučení“ s Aspose.Words pro .NET.

### Nejčastější dotazy

#### Q1: Co je hromadná korespondence v Aspose.Words?

Hromadná korespondence v Aspose.Words je proces slučování dat z externího zdroje (např. tabulky Excel nebo databáze) se šablonou dokumentu aplikace Word za účelem vytvoření personalizovaných dokumentů. To usnadňuje automatizované generování dopisů, zpráv a dalších podobných dokumentů.

#### Q2: Jak získám seznam polí hromadné korespondence dostupných v dokumentu aplikace Word?

Chcete-li získat seznam polí hromadné korespondence dostupných v dokumentu aplikace Word, postupujte takto:

1. Importujte třídy Document a MailMergeFieldNames z oboru názvů Aspose.Words.
2. Vytvořte instanci dokumentu načtením dokumentu aplikace Word.
3. Pomocí metody GetMailMergeFieldNames objektu Document získáte seznam dostupných polí hromadné korespondence.

Zde je ukázkový kód pro ilustraci procesu:

```csharp
// Importujte potřebné jmenné prostory
using Aspose.Words;
using Aspose.Words.MailMerging;

// Načtěte existující dokument
Document document = new Document("FilePath");

// Získejte seznam polí hromadné korespondence
MailMergeFieldNames fieldNames = document.MailMerge.GetFieldNames();

// Procházejte dostupná pole hromadné korespondence
foreach (string fieldName in fieldNames)
{
     // Udělejte něco s názvem pole
     Console.WriteLine(fieldName);
}
```
### FAQ

#### Otázka: Co je hromadná korespondence v Aspose.Words?

Odpověď: Hromadná korespondence v Aspose.Words je proces slučování dat z externího zdroje (např. tabulky Excel nebo databáze) se šablonou dokumentu Word za účelem vytvoření personalizovaných dokumentů. To usnadňuje automatizované generování dopisů, zpráv a dalších podobných dokumentů.

#### Otázka: Jak získám seznam polí hromadné korespondence dostupných v dokumentu aplikace Word?

Odpověď: Chcete-li získat seznam polí hromadné korespondence dostupných v dokumentu aplikace Word, postupujte takto:

1. Importujte třídy Document a MailMergeFieldNames z oboru názvů Aspose.Words.
2. Vytvořte instanci dokumentu načtením dokumentu aplikace Word.
3. Pomocí metody GetMailMergeFieldNames objektu Document získáte seznam dostupných polí hromadné korespondence.

#### Otázka: Mohu získat pole hromadné korespondence z externího zdroje dat, jako je například tabulka aplikace Excel?

Odpověď: Ano, pole hromadné korespondence můžete získat z externího zdroje dat, jako je například tabulka aplikace Excel. K tomu můžete použít funkce datové vazby Aspose.Words k navázání spojení se zdrojem dat a získání názvů dostupných polí.

#### Otázka: Je možné filtrovat pole hromadné korespondence na základě určitých kritérií?

Odpověď: Ano, je možné filtrovat pole hromadné korespondence na základě určitých kritérií. K filtrování polí hromadné korespondence můžete použít regulární výrazy nebo specifické podmínky a získat pouze ta, která splňují vaše konkrétní kritéria.

#### Otázka: Jak mohu manipulovat s poli hromadné korespondence v Aspose.Words?

Odpověď: Pro manipulaci s poli hromadné korespondence v Aspose.Words můžete použít metody a vlastnosti poskytované objekty Document a MailMergeField. Můžete přidávat, odebírat nebo aktualizovat pole hromadné korespondence a také načítat a upravovat hodnoty spojené s poli.