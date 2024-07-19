---
title: Při vykreslování zadejte výchozí písmo
linktitle: Při vykreslování zadejte výchozí písmo
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce určením výchozího písma při vykreslování dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fonts/specify-default-font-when-rendering/
---

tomto tutoriálu vás provedeme krok za krokem procesem zadání výchozího písma při vykreslování dokumentu pomocí Aspose.Words for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak určit výchozí písmo, které se použije při vykreslování dokumentů pomocí Aspose.Words for .NET.

## Krok 1: Definujte adresář dokumentů
Nejprve musíte nastavit cestu k adresáři dokumentů. Toto je umístění, kam chcete uložit upravený vykreslený dokument. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Načtěte dokument k vykreslení
 Dále musíte načíst dokument k vykreslení pomocí`Document` třída. Ujistěte se, že jste zadali správnou cestu dokumentu.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 3: Nastavte výchozí písmo
 Nyní můžete určit výchozí písmo, které se má použít při vykreslování, vytvořením instance souboru`FontSettings` třídy a nastavení`DefaultFontName` vlastnictvím`DefaultFontSubstitution` namítat proti`DefaultFontSubstitution` objekt`SubstitutionSettings` z`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## Krok 4: Uložte vykreslený dokument
 Nakonec můžete vykreslený dokument uložit do souboru pomocí`Save()` metoda`Document` třída. Ujistěte se, že jste zadali správnou cestu a název souboru.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Ukázkový zdrojový kód pro specifikaci výchozího písma při vykreslování pomocí Aspose.Words for .NET 

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Pokud zde definované výchozí písmo nelze během vykreslování najít
// místo toho se použije nejbližší písmo na stroji.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Závěr
tomto tutoriálu jsme se naučili, jak určit výchozí písmo při vykreslování dokumentu pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce můžete snadno nastavit výchozí písmo, které se použije při vykreslování dokumentů. Aspose.Words nabízí výkonné a flexibilní API pro zpracování textu s písmy ve vašich dokumentech. S těmito znalostmi můžete řídit a přizpůsobovat vykreslování svých dokumentů svým konkrétním potřebám.

### FAQ

#### Otázka: Jak mohu určit výchozí písmo při převodu do PDF v Aspose.Words?

 A: Chcete-li určit výchozí písmo při převodu do PDF v Aspose.Words, můžete použít`PdfOptions` třídu a nastavte`DefaultFontName` vlastnost na název požadovaného písma.

#### Otázka: Co když není při převodu do PDF k dispozici výchozí písmo?

Odpověď: Pokud zadané výchozí písmo není při převodu do PDF dostupné, Aspose.Words použije náhradní písmo pro zobrazení textu v převedeném dokumentu. To může způsobit mírný rozdíl ve vzhledu od původního písma.

#### Otázka: Mohu určit výchozí písmo pro jiné výstupní formáty, jako je DOCX nebo HTML?

Odpověď: Ano, můžete určit výchozí písmo pro jiné výstupní formáty, jako je DOCX nebo HTML, pomocí příslušných voleb převodu a nastavením odpovídající vlastnosti pro každý formát.

#### Otázka: Jak mohu zkontrolovat výchozí písmo určené v Aspose.Words?

 A: Chcete-li zkontrolovat výchozí písmo určené v Aspose.Words, můžete použít`DefaultFontName` vlastnictvím`PdfOptions` třídy a načte název nakonfigurovaného písma.

#### Otázka: Je možné určit jiné výchozí písmo pro každou část dokumentu?

Odpověď: Ano, je možné určit různé výchozí písmo pro každou část dokumentu pomocí možností formátování specifických pro každou část. To by však vyžadovalo pokročilejší manipulaci s dokumentem pomocí funkcí Aspose.Words.