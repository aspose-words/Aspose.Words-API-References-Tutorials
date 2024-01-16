---
title: Napište všechna pravidla CSS do jednoho souboru
linktitle: Napište všechna pravidla CSS do jednoho souboru
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak převést dokument aplikace Word na pevný HTML zápisem všech pravidel CSS do jednoho souboru pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

Při převodu dokumentu aplikace Word na pevný HTML v aplikaci C# možná budete chtít sloučit všechna pravidla CSS do jednoho souboru pro lepší organizaci a přenositelnost. S knihovnou Aspose.Words pro .NET můžete tuto funkci snadno určit pomocí možností uložení HtmlFixedSaveOptions. V tomto podrobném průvodci vás provedeme tím, jak používat zdrojový kód Aspose.Words for .NET C# k převodu dokumentu aplikace Word na pevný HTML zápisem všech pravidel CSS do jednoho souboru pomocí možností uložení HtmlFixedSaveOptions.

## Porozumění knihovně Aspose.Words

Než se ponoříte do kódu, je důležité porozumět knihovně Aspose.Words pro .NET. Aspose.Words je výkonná knihovna pro vytváření, úpravu, převod a ochranu dokumentů aplikace Word na různých platformách včetně .NET. Nabízí mnoho funkcí pro manipulaci s dokumenty, jako je vkládání textu, změna formátování, přidávání oddílů a mnoho dalšího.

## Načítání dokumentu aplikace Word

Prvním krokem je načtení dokumentu aplikace Word, který chcete převést do pevného HTML. Pomocí třídy Document načtěte dokument ze zdrojového souboru. Zde je příklad:

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

V tomto příkladu načteme dokument "Document.docx" umístěný v adresáři dokumentů.

## Konfigurace možností zálohování

Dalším krokem je konfigurace možností uložení pro převod do pevného HTML. Chcete-li zapsat všechna pravidla CSS do jednoho souboru, použijte třídu HtmlFixedSaveOptions a nastavte vlastnost SaveFontFaceCssSeparately na hodnotu false. Jak na to:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

Vytvoříme nový objekt HtmlFixedSaveOptions a nastavíme vlastnost SaveFontFaceCssSeparately na false, abychom zapsali všechna pravidla CSS do jednoho souboru.

## Opravena konverze HTML dokumentů

Nyní, když jsme nakonfigurovali možnosti uložení, můžeme přistoupit k převodu dokumentu do pevného HTML. Pomocí metody Save třídy Document uložte převedený dokument v pevném formátu HTML zadáním voleb uložení. Zde je příklad:

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

tomto příkladu uložíme převedený dokument jako „WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html“ pomocí zadaných možností uložení.

### Příklad zdrojového kódu pro HtmlFixedSaveOptions s funkcí "Zapsat všechna pravidla CSS do jednoho souboru" pomocí Aspose.Words for .NET

```csharp
// Přístupová cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Načtěte dokument aplikace Word
Document doc = new Document(dataDir + "Document.docx");

// Nakonfigurujte možnosti zálohování pomocí funkce „Zapsat všechna pravidla CSS do jednoho souboru“.
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Převést dokument do pevného HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Závěr

V této příručce jsme se zabývali tím, jak převést dokument aplikace Word na pevný HTML zápisem všech pravidel CSS do jednoho souboru pomocí HtmlFixedSaveOptions s knihovnou Aspose.Words pro .NET. Dodržováním uvedených kroků a použitím poskytnutého zdrojového kódu C# můžete tuto funkci snadno použít ve své aplikaci C#. Zápis všech pravidel CSS do jednoho souboru usnadňuje organizaci a správu kódu HTML generovaného během převodu dokumentu.