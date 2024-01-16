---
title: Jednotka měření
linktitle: Jednotka měření
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak určit měrnou jednotku při převodu dokumentu aplikace Word na ODT pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-odtsaveoptions/measure-unit/
---

Když převádíte dokument aplikace Word do formátu OpenDocument Text (ODT) v aplikaci C#, možná budete chtít zadat měrnou jednotku použitou pro měřitelné formátování a vlastnosti obsahu. S knihovnou Aspose.Words pro .NET můžete tuto funkci snadno určit pomocí možností uložení OdtSaveOptions. V tomto podrobném průvodci vás provedeme tím, jak používat zdrojový kód Aspose.Words for .NET C# k převodu dokumentu aplikace Word na ODT zadáním měrné jednotky pomocí OdtSaveOptions.

## Porozumění knihovně Aspose.Words

Než se ponoříte do kódu, je důležité porozumět knihovně Aspose.Words pro .NET. Aspose.Words je výkonná knihovna pro vytváření, úpravu, převod a ochranu dokumentů aplikace Word na různých platformách včetně .NET. Nabízí mnoho funkcí pro manipulaci s dokumenty, jako je vkládání textu, změna formátování, přidávání oddílů a mnoho dalšího.

## Načítání dokumentu aplikace Word

Prvním krokem je načtení dokumentu aplikace Word, který chcete převést na ODT. Pomocí třídy Document načtěte dokument ze zdrojového souboru. Zde je příklad:

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

V tomto příkladu načteme dokument "Document.docx" umístěný v adresáři dokumentů.

## Konfigurace možností zálohování

Dalším krokem je konfigurace možností zálohování pro převod na ODT. Použijte třídu OdtSaveOptions a nastavte vlastnost MeasureUnit na požadovanou hodnotu. Pokud například chcete jako jednotku měření použít palce, nastavte MeasureUnit na OdtSaveMeasureUnit.Inches. Jak na to:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

Vytvoříme nový objekt OdtSaveOptions a nastavíme vlastnost MeasureUnit na požadovanou hodnotu, v našem případě OdtSaveMeasureUnit.Inches, abychom jako měrnou jednotku použili palce.

## Převést dokument na ODT

Nyní, když jsme nakonfigurovali možnosti uložení, můžeme přistoupit k převodu dokumentu na ODT. Použijte metodu Uložit třídy Document k uložení převedeného dokumentu ve formátu ODT zadáním možností uložení. Zde je příklad:

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

tomto příkladu uložíme převedený dokument jako "WorkingWithOdtSaveOptions.MeasureUnit.odt" pomocí zadaných možností uložení.

### Ukázkový zdrojový kód pro OdtSaveOptions s funkcí "Měrná jednotka" pomocí Aspose.Words for .NET



```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Načtěte dokument aplikace Word
Document doc = new Document(dataDir + "Document.docx");

// Konfigurace možností zálohování pomocí funkce "Měrná jednotka".
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// Převeďte dokument na ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Závěr

V této příručce jsme vysvětlili, jak převést dokument aplikace Word na ODT zadáním měrné jednotky pomocí možností uložení OdtSaveOptions s knihovnou Aspose.Words pro .NET. Dodržováním uvedených kroků a použitím poskytnutého zdrojového kódu C# můžete tuto funkci snadno použít ve své aplikaci C#. Zadání měrné jednotky při převodu do ODT umožňuje řídit formátování a rozměry výsledného dokumentu podle vašich konkrétních potřeb.