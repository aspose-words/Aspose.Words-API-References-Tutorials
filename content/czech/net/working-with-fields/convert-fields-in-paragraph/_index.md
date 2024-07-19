---
title: Převést pole v odstavci
linktitle: Převést pole v odstavci
second_title: Aspose.Words API pro zpracování dokumentů
description: Převeďte pole IF na prostý text v odstavci pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fields/convert-fields-in-paragraph/
---

Zde je výukový program, který ukazuje, jak používat funkci Převést pole na odstavec s Aspose.Words pro .NET. Tento kód převede všechna pole typu IF nalezená v posledním odstavci dokumentu na prostý text. Chcete-li tento kód pochopit a spustit, postupujte podle následujících kroků.

Než začnete, ujistěte se, že jste nainstalovali Aspose.Words for .NET a nastavili vývojové prostředí.

## Krok 1: Import referencí

Chcete-li použít Aspose.Words ve svém projektu, musíte přidat potřebné odkazy. Ujistěte se, že jste do projektu přidali odkaz na knihovnu Aspose.Words.

## Krok 2: Načtení dokumentu

Než budete moci převádět pole, musíte načíst dokument obsahující pole, která chcete převést. Ujistěte se, že jste zadali správnou cestu k adresáři obsahujícímu dokument. Postup nahrání dokumentu:

```csharp
//Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument.
Document doc = new Document(dataDir + "Linked fields.docx");
```

Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" skutečnou cestou k adresáři vašich dokumentů.

## Krok 3: Převod polí na text

Nyní, když je dokument načten, můžeme přistoupit k převodu typových polí na prostý text. V tomto příkladu se zaměřujeme pouze na pole uvedená v posledním odstavci dokumentu. Zde je kód, který provádí tuto konverzi:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

 Tento kód používá kombinaci metod LINQ k odfiltrování polí v posledním odstavci dokumentu a poté je převede na prostý text voláním`Unlink()` metoda.

## Krok 4: Uložení upraveného dokumentu

 Jakmile budou pole převedena, můžete upravený dokument uložit. Použijte`Save()` metoda pro toto. Zde je příklad:

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro zálohu.

### Příklad zdrojového kódu pro Převést pole v odstavci pomocí Aspose.Words pro .NET

```csharp
//Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument.
Document doc = new Document(dataDir + "Linked fields.docx");

// Převeďte pole IF na prostý text v posledním odstavci dokumentu.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// Uložte upravený dokument.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

### FAQ

#### Otázka: Co je převodní pole v Aspose.Words?

A: Konverzní pole v Aspose.Words je typ pole, které převádí hodnotu nebo výraz do jiného formátu nebo datového typu. Pole převodu můžete například použít k převodu data do určitého formátu, čísla na text nebo k provedení jiných typů převodů.

#### Otázka: Jak vložit převodní pole do odstavce pomocí Aspose.Words?

Odpověď: Chcete-li vložit konverzní pole do odstavce pomocí Aspose.Words, můžete postupovat takto:

1. Importujte třídu Document z oboru názvů Aspose.Words.
2. Vytvořte instanci dokumentu načtením existujícího dokumentu.
3. Získejte odstavec, kam chcete vložit pole převodu.
4. Pomocí metody InsertField vložte převodní pole se správnou syntaxí.

#### Otázka: Jaké formáty převodu Aspose.Words podporuje?

Odpověď: Aspose.Words podporuje širokou škálu formátů převodu v polích, včetně formátů data, číselných formátů, textových formátů, formátů měn, procentuálních formátů a dalších. Úplný seznam dostupných konverzních formátů naleznete v dokumentaci Aspose.Words.

#### Otázka: Jak aktualizovat pole převodu v dokumentu aplikace Word pomocí Aspose.Words?

Odpověď: Chcete-li aktualizovat pole převodu v dokumentu aplikace Word pomocí Aspose.Words, můžete použít metodu UpdateFields. Tato metoda prochází dokumentem a aktualizuje všechna pole, včetně převodních polí, přepočítává hodnoty na základě aktuálních dat.