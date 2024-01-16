---
title: Přijímat upozornění na písma
linktitle: Přijímat upozornění na písma
second_title: Aspose.Words API pro zpracování dokumentů
description: Přečtěte si, jak přijímat upozornění na chybějící nebo nahrazená písma při používání Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fonts/receive-notifications-of-fonts/
---

V tomto tutoriálu vás provedeme tím, jak přijímat upozornění na písma při používání Aspose.Words pro .NET. Upozornění na písma vám umožňují detekovat a spravovat chybějící nebo nahrazená písma ve vašich dokumentech. Provedeme vás krok za krokem, abychom vám pomohli pochopit a implementovat kód ve vašem projektu .NET.

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

## Krok 2: Načtěte dokument a nakonfigurujte nastavení písma
 Dále načteme dokument pomocí`Document` třídy a nakonfigurujte nastavení písma pomocí`FontSettings` třída. Nastavíme výchozí písmo, které se použije v případě chybějících písem.

```csharp
// Načtěte dokument a nakonfigurujte nastavení písma
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

## Krok 3: Nastavte obsluhu oznámení
Dále definujeme obsluhu oznámení implementací`IWarningCallback` rozhraní. To nám umožní shromažďovat upozornění na písmo při ukládání dokumentu.

```csharp
// Definujte obslužnou rutinu oznámení
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc. WarningCallback = callback;
```

## Krok 4: Použijte nastavení písma a uložte dokument
Nakonec na dokument aplikujeme nastavení písma a uložíme jej. Jakákoli upozornění na písma budou zachycena obslužným programem oznámení, který jsme definovali dříve.

```csharp
// Použijte nastavení písma a uložte dokument
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");
```

### Ukázkový zdrojový kód pro příjem oznámení písem pomocí Aspose.Words pro .NET 
```csharp

// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Můžeme si vybrat výchozí písmo, které se použije v případě chybějících písem.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
// Pro testování nastavíme Aspose.Words, aby hledal fonty pouze ve složce, která neexistuje. Protože Aspose.Words nebude
// najít všechna písma v zadaném adresáři, pak během vykreslování budou písma v dokumentu podřízena výchozímu
// písmo určené v části FontSettings.DefaultFontName. Tuto dílčí nabídku můžeme vyzvednout pomocí našeho zpětného volání.
fontSettings.SetFontsFolder(string.Empty, false);
//Vytvořte novou třídu implementující IWarningCallback, která shromažďuje všechna varování vytvořená během ukládání dokumentu.
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");

```

## Závěr
V tomto tutoriálu jsme viděli, jak přijímat upozornění na písma při používání Aspose.Words pro .NET. Upozornění na písma vám umožňují detekovat a spravovat chybějící nebo nahrazená písma ve vašich dokumentech. Tuto funkci použijte k zajištění konzistence písem ve vašich dokumentech a v případě chybějících písem podnikněte příslušné kroky.

### FAQ

#### Otázka: Jak mohu přijímat upozornění na chybějící písma v Aspose.Words?

 A: Chcete-li dostávat upozornění na chybějící písma v Aspose.Words, můžete použít`FontSettings` třída a`FontSubstitutionCallback` událost. Můžete nastavit metodu zpětného volání, která bude upozorněna, když při zpracování dokumentů narazíte na chybějící písma.

#### Otázka: Jak mohu řešit chybějící písma v dokumentech aplikace Word?

Odpověď: Chcete-li se vypořádat s chybějícími písmy v dokumentech aplikace Word, můžete použít různé strategie. Chybějící fonty můžete nainstalovat do systému, kde spouštíte aplikaci Aspose.Words, nebo můžete chybějící fonty nahradit alternativními fonty, které jsou k dispozici.

#### Otázka: Je možné v Aspose.Words přijímat upozornění na nahrazená písma?

 Odpověď: Ano, v Aspose.Words je možné přijímat upozornění na nahrazená písma. Když jsou písma nahrazena během zpracování dokumentu, můžete být upozorněni pomocí`FontSubstitutionCallback` událost a proveďte příslušné kroky k úpravě vzhledu textu.

#### Otázka: Jak mohu zachovat konzistentní vzhled textu, když jsou v Aspose.Words nahrazena písma?

Odpověď: Chcete-li zachovat konzistenci vzhledu textu při nahrazení písem, můžete upravit vlastnosti formátování textu, jako je velikost písma, styl a barva. Můžete také zvážit použití náhradních písem, která jsou vizuálně podobná původním písmům.