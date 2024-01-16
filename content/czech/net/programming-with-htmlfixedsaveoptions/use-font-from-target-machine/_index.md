---
title: Použít písmo z cílového stroje
linktitle: Použít písmo z cílového stroje
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak převést dokument aplikace Word na pevný HTML pomocí písem cílového počítače pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

Při převodu dokumentu aplikace Word na pevný HTML v aplikaci C# můžete chtít použít fonty cílového počítače, abyste zajistili, že vykreslený HTML zachová původní vzhled a styl dokumentu. S knihovnou Aspose.Words pro .NET můžete tuto funkci snadno určit pomocí možností uložení HtmlFixedSaveOptions. V tomto podrobném průvodci vás provedeme tím, jak používat zdrojový kód C# Aspose.Words for .NET k převodu dokumentu aplikace Word do pevného HTML pomocí písem cílového počítače pomocí HtmlFixedSaveOptions.

## Porozumění knihovně Aspose.Words

Než se ponoříte do kódu, je důležité porozumět knihovně Aspose.Words pro .NET. Aspose.Words je výkonná knihovna pro vytváření, úpravu, převod a ochranu dokumentů aplikace Word na různých platformách včetně .NET. Nabízí mnoho funkcí pro manipulaci s dokumenty, jako je vkládání textu, změna formátování, přidávání oddílů a mnoho dalšího.

## Načítání dokumentu aplikace Word

Prvním krokem je načtení dokumentu aplikace Word, který chcete převést do pevného HTML. Pomocí třídy Document načtěte dokument ze zdrojového souboru. Zde je příklad:

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

V tomto příkladu načteme dokument "Odrážky s alternativním fontem.docx" umístěný v adresáři dokumentů.

## Konfigurace možností zálohování

Dalším krokem je konfigurace možností uložení pro převod do pevného HTML. Použijte třídu HtmlFixedSaveOptions a nastavte vlastnost UseTargetMachineFonts na hodnotu true, abyste Aspose.Words řekli, že má používat písma z cílového počítače. Jak na to:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

Vytvoříme nový objekt HtmlFixedSaveOptions a nastavíme vlastnost UseTargetMachineFonts na true, abychom při převodu použili písma cílového počítače.

## Opravena konverze HTML dokumentů

Nyní, když jsme nakonfigurovali možnosti uložení, můžeme přistoupit k převodu dokumentu do pevného HTML. Pomocí metody Save třídy Document uložte převedený dokument v pevném formátu HTML zadáním voleb uložení. Zde je příklad:

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

V tomto příkladu uložíme převedený dokument jako "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" pomocí zadaných možností uložení.

### Příklad zdrojového kódu pro HtmlFixedSaveOptions s funkcí "Použít písma z cílového počítače" pomocí Aspose.Words for .NET

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Načtěte dokument aplikace Word
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

//Nakonfigurujte možnosti zálohování pomocí funkce „Použít písma z cílového počítače“.
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// Převést dokument do pevného HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## Závěr

V této příručce jsme vysvětlili, jak převést dokument aplikace Word do pevného HTML pomocí písem cílového počítače pomocí knihovny Aspose.Words pro .NET. Dodržováním uvedených kroků a použitím poskytnutého zdrojového kódu C# můžete tuto funkci snadno použít ve své aplikaci C#. Převod do pevného HTML s fonty cílového stroje zaručuje věrné a konzistentní vykreslení dokumentu ve formátu HTML.
