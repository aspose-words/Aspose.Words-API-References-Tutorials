---
title: Nastavit složku písem
linktitle: Nastavit složku písem
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak nastavit adresář písem v Aspose.Words pro .NET a zajistit dostupnost písem používaných ve vašich dokumentech.
type: docs
weight: 10
url: /cs/net/working-with-fonts/set-fonts-folder/
---
V tomto tutoriálu vám ukážeme, jak nastavit adresář písem v Aspose.Words pro .NET. Dozvíte se, jak určit adresář obsahující písma použitá v dokumentu aplikace Word.

## Předpoklady
Než začnete, ujistěte se, že máte následující položky:
- Pracovní znalost programovacího jazyka C#
- Knihovna Aspose.Words pro .NET nainstalovaná ve vašem projektu

## Krok 1: Definujte adresář dokumentů
Začněte nastavením cesty k adresáři na umístění vašeho dokumentu aplikace Word. Nahradit`"YOUR DOCUMENT DIRECTORY"` v kódu s příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Nastavte adresář písem
 Vytvořte instanci souboru`FontSettings` třídy a použijte`SetFontsFolder` metoda k určení adresáře obsahujícího fonty. Nahradit`"Fonts"` s názvem aktuálního adresáře písem.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Krok 3: Načtěte dokument s nastavením písma
 Použijte`LoadOptions` třídy k určení nastavení písma v`FontSettings` volba. Poté použijte`Document` třídy k načtení dokumentu pomocí těchto možností.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Ukázka zdrojového kódu pro složku Set Fonts pomocí Aspose.Words pro .NET 

```csharp

// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Závěr
gratuluji! Nyní víte, jak nastavit adresář písem v Aspose.Words pro .NET. Tuto funkci můžete použít k zajištění dostupnosti písem použitých ve vašem dokumentu a k zajištění konzistence zobrazení písem.

### FAQ

#### Otázka: Jak mohu nastavit vlastní složku písem v Aspose.Words?

 A: Chcete-li nastavit vlastní složku písem v Aspose.Words, můžete použít`FontsFolder` třída a`SetFontsFolders` metoda určující cestu ke složce obsahující vaše písma.

#### Otázka: Mohu v Aspose.Words nastavit více složek písem?

 Odpověď: Ano, můžete nastavit více složek písem v Aspose.Words voláním`SetFontsFolders` metodu vícekrát s cestami různých složek písem, které chcete použít.

#### Otázka: Co se stane, když písmo použité v dokumentu není přítomno v definovaných složkách písem?

Odpověď: Pokud se písmo použité v dokumentu nenachází ve složkách písem definovaných v Aspose.Words, použije se místo něj náhradní písmo. Tím je zajištěno, že text v dokumentu bude vždy zobrazen správně, i když není k dispozici původní písmo.

#### Otázka: Mají složky písem definované v Aspose.Words přednost před písmy nainstalovanými v systému?

Odpověď: Ano, složky písem definované v Aspose.Words mají přednost před písmy nainstalovanými v systému. To znamená, že pokud je písmo se stejným názvem přítomno jak v definovaných složkách písem, tak v systémových písmech, bude při zpracování dokumentů aplikace Word použita verze ve složce písem.