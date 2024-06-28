---
title: Vložit pole
linktitle: Vložit pole
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vložit pole do dokumentů aplikace Word pomocí Aspose.Words for .NET. Přizpůsobte si své dokumenty pomocí dynamických polí.
type: docs
weight: 10
url: /cs/net/working-with-fields/insert-field/
---

Zde je podrobný návod k vysvětlení zdrojového kódu C# níže, který používá funkci "Vložit pole" Aspose.Words pro .NET. Ujistěte se, že pečlivě dodržujete každý krok, abyste dosáhli požadovaných výsledků.

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

## Krok 3: Vložení pole

 Používáme`InsertField()` metoda DocumentBuilder pro vložení pole do dokumentu. V tomto příkladu vložíme slučovací pole (MERGEFIELD) s názvem pole "MyFieldName" a formátem sloučení.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Příklad zdrojového kódu pro vložení pole s Aspose.Words pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte dokument a DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Vložte pole.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

V tomto příkladu jsme vytvořili nový dokument, inicializovali DocumentBuilder a pak vložili slučovací pole s názvem pole "MyFieldName" a formátem sloučení. Dokument se poté uloží se zadaným názvem souboru.

Tímto končí náš průvodce používáním funkce "Vložit pole" s Aspose.Words pro .NET.

### FAQ

#### Otázka: Co je pole ve Wordu?

Odpověď: Pole ve Wordu je prvek, který umožňuje vkládat dynamická data do dokumentu a manipulovat s nimi. Lze jej použít k zobrazení proměnných informací, jako jsou data, čísla stránek, tabulky, matematické vzorce atd.

#### Otázka: Jak vložit pole do dokumentu aplikace Word?

Odpověď: Chcete-li vložit pole do dokumentu aplikace Word, postupujte takto:

1. Umístěte kurzor na místo, kam chcete pole vložit.
2. Přejděte na kartu "Vložit" na pásu karet.
3. Kliknutím na tlačítko "Pole" ve skupině "Text" otevřete dialogové okno polí.
4. Z rozevíracího seznamu vyberte typ pole, které chcete vložit.
5. Podle potřeby nakonfigurujte možnosti pole.
6. Klepnutím na tlačítko "OK" vložte pole do dokumentu.

#### Otázka: Jaké jsou běžně používané typy polí ve Wordu?

Odpověď: Word nabízí širokou škálu typů polí, které můžete použít ve svých dokumentech. Zde jsou některé z běžně používaných typů polí:

- Datum a čas: zobrazuje aktuální datum a čas.
- Číslo stránky: zobrazí číslo aktuální stránky.
- Obsah: automaticky generuje obsah na základě stylů vašich titulků.
- Výpočet: provádí matematické výpočty pomocí vzorců.
- Text výplně: Generuje náhodný text, který vyplní váš dokument.

#### Otázka: Mohu přizpůsobit vzhled polí ve Wordu?

Odpověď: Ano, vzhled polí ve Wordu můžete upravit pomocí dostupných možností formátování. Můžete například změnit písmo, velikost, barvu a styl textu v poli. Můžete také použít efekty formátování, jako je tučné písmo, kurzíva a podtržení.
  