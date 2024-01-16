---
title: Kultura aktualizace pole
linktitle: Kultura aktualizace pole
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak aktualizovat kulturu pole v dokumentech aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fields/field-update-culture/
---

Zde je podrobný návod k vysvětlení zdrojového kódu C# níže, který používá funkci "Field Culture Update" Aspose.Words for .NET. Ujistěte se, že pečlivě dodržujete každý krok, abyste dosáhli požadovaných výsledků.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém kódu musíte zadat adresář vašich dokumentů. Nahraďte hodnotu „VÁŠ ADRESÁŘ DOKUMENTŮ“ příslušnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření dokumentu a generátoru dokumentů

Začneme vytvořením nového dokumentu a generátoru dokumentů.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Vložení pole času

 Používáme`InsertField()` metoda pro vložení časového pole do dokumentu.

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

Tím se do dokumentu vloží časové pole.

## Krok 4: Konfigurace kultury aktualizace pole

Možnosti pole nakonfigurujeme tak, aby specifikovalo, že kultura aktualizace pole by měla být založena na kódu pole.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

Tyto možnosti určují kulturu použitou pro aktualizaci polí.

### Ukázkový zdrojový kód pro aktualizaci Field Culture pomocí Aspose.Words pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte dokument a generátor dokumentů.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Vložte časové pole.
builder. InsertField(FieldType.FieldTime, true);

// Nakonfigurujte kulturu aktualizace pole.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

// Uložte dokument.
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

V tomto příkladu jsme vytvořili nový dokument, vložili pole času a nakonfigurovali kulturu aktualizace pole. Poté jsme dokument uložili se zadaným názvem souboru.

Tímto končí náš průvodce používáním funkce "Aktualizovat kulturu pole" s Aspose.Words pro .NET.

### FAQ

#### Otázka: Jaká je kultura aktualizace pole v Aspose.Words?

Odpověď: Kultura aktualizace polí v Aspose.Words odkazuje na kulturu používanou k formátování a aktualizaci hodnot polí v dokumentu aplikace Word. Kultura určuje, jak jsou čísla, data a další data prezentována v polích při jejich aktualizaci.

#### Otázka: Jak nastavit kulturu aktualizace pro pole v dokumentu aplikace Word pomocí Aspose.Words?

Odpověď: Chcete-li nastavit kulturu aktualizace pro pole v dokumentu aplikace Word pomocí Aspose.Words, můžete postupovat takto:

1. Importujte třídu Document z oboru názvů Aspose.Words.
2. Vytvořte instanci dokumentu načtením existujícího dokumentu.
3. Pomocí vlastnosti Document.UpdateFieldsCultureInfo nastavte kulturu aktualizace pro pole.

#### Otázka: Jaké jsou podporované kultury pro aktualizaci polí v Aspose.Words?

Odpověď: Aspose.Words podporuje různé kultury pro aktualizaci polí. Můžete zadat jakoukoli kulturu podporovanou operačním systémem. Například „en-US“ pro americkou angličtinu, „fr-FR“ pro francouzštinu, „de-DE“ pro němčinu atd.

#### Otázka: Je možné nastavit specifickou kulturu pro jednotlivou oblast spíše než pro celý dokument?

Odpověď: Ano, je možné nastavit specifickou kulturu pro jednotlivou oblast spíše než pro celý dokument. V Aspose.Words má každé pole vlastnost Format, kterou lze použít k nastavení kultury formátování specifické pro dané pole. To vám umožní řídit, jak se toto pole zobrazí a aktualizuje nezávisle na ostatních polích v dokumentu.

#### Otázka: Jak mohu zkontrolovat aktuálně definovanou kulturu aktualizace polí v dokumentu aplikace Word?

Odpověď: Chcete-li zkontrolovat aktuálně definovanou kulturu aktualizace polí v dokumentu aplikace Word, můžete použít vlastnost Document.UpdateFieldsCultureInfo. Tato vlastnost vrací objekt CultureInfo představující kulturu aktuálně používanou pro nastavení aktualizací polí.