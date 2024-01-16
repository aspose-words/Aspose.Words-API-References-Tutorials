---
title: Zdroj Příklad zdroje písma Steam
linktitle: Zdroj Příklad zdroje písma Steam
second_title: Aspose.Words API pro zpracování dokumentů
description: Zjistěte, jak používat zdroj písma Resource Stream k načtení vlastních písem do Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fonts/resource-steam-font-source-example/
---

V tomto tutoriálu vás provedeme tím, jak používat zdroj písma toku zdrojů s Aspose.Words pro .NET. Tento zdroj písem vám umožňuje načíst písma z toku prostředků, což může být užitečné, když chcete do aplikace začlenit vlastní písma.

## Předpoklady
Než začnete, ujistěte se, že máte následující položky:
- Pracovní znalost programovacího jazyka C#
- Knihovna Aspose.Words pro .NET nainstalovaná ve vašem projektu

## Krok 1: Definujte adresář dokumentů
 Nejprve musíte nastavit cestu k adresáři na umístění vašeho dokumentu aplikace Word. Nahradit`"YOUR DOCUMENT DIRECTORY"` v kódu s příslušnou cestou.

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Nahrajte dokument a nastavte zdroj písma pro streamování zdrojů
 Dále načteme dokument pomocí`Document` třídy a nastavte zdroj písem zdroje streamu pomocí`FontSettings.DefaultInstance.SetFontsSources()` třída. To umožní Aspose.Words najít písma v proudu zdrojů.

```csharp
// Načtěte dokument a nastavte zdroj písem zdroje streamu
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{ new SystemFontSource(), new ResourceSteamFontSource() });
```

## Krok 3: Uložte dokument
Nakonec dokument uložíme. Písma budou načtena ze zadaného toku prostředků a vložena do dokumentu.

```csharp
// Uložte dokument
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Ukázka zdrojového kódu pro Resource Steam Příklad zdroje písem pomocí Aspose.Words pro .NET 

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{ new SystemFontSource(), new ResourceSteamFontSource() });
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Závěr
tomto tutoriálu jste se naučili používat zdroj písem Resource Flow s Aspose.Words for .NET. Tato funkce vám umožňuje načíst písma ze zdroje, což je užitečné, když chcete do dokumentů vložit vlastní písma. Experimentujte s různými písmy a prozkoumejte možnosti, které nabízí Aspose.Words pro správu písem.

### FAQ

#### Otázka: Jak mohu načíst písmo z proudu prostředků do Aspose.Words?

 A: Chcete-li načíst písmo ze streamu prostředků v Aspose.Words, můžete použít`FontSettings` třída a`SetFontsSources` metoda k určení zdroje písem pomocí toku prostředků. To umožňuje, aby bylo písmo načteno přímo z datového proudu prostředků, nikoli z fyzického souboru.

#### Otázka: Jaké jsou výhody použití toků prostředků k určení zdrojů písem v Aspose.Words?

Odpověď: Použití proudů zdrojů k určení zdrojů písem má několik výhod:
- Umožňuje načíst písma ze zdrojů zabudovaných ve vaší aplikaci, což usnadňuje nasazení a distribuci dokumentů.
- Poskytuje zvýšenou flexibilitu při správě písem, protože můžete načítat písma z různých toků zdrojů v závislosti na vašich potřebách.

#### Otázka: Jak mohu přidat písma do proudu prostředků v mé aplikaci .NET?

 Odpověď: Chcete-li přidat písma do proudu prostředků ve vaší aplikaci .NET, musíte soubory písem vložit do prostředků projektu. K těmto souborům písem pak můžete přistupovat pomocí metod specifických pro vaši vývojovou platformu (např.`GetManifestResourceStream` za použití`System.Reflection` jmenný prostor).

#### Otázka: Je možné načíst více písem z různých zdrojů do jednoho dokumentu Aspose.Words?

 Odpověď: Ano, je zcela možné načíst více písem z různých zdrojů zdrojů do jednoho dokumentu Aspose.Words. Můžete zadat více zdrojů písem pomocí`SetFontsSources` metoda`FontSettings` třída, která poskytuje příslušné proudy prostředků pro každé písmo.

#### Otázka: Jaké typy toků prostředků mohu použít k načtení písem do Aspose.Words?

Odpověď: K načtení písem do Aspose.Words můžete použít různé typy toků prostředků, jako jsou toky zdrojů zabudované do vaší aplikace .NET, toky zdrojů z externího souboru, toky zdrojů z databáze atd. Ujistěte se, že jste poskytli odpovídající toky zdrojů na základě vašeho nastavení a potřeb.