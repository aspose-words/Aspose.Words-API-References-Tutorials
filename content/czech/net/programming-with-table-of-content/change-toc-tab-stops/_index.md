---
title: Změnit zarážky tabulátoru obsahu v dokumentu aplikace Word
linktitle: Změnit zarážky tabulátoru obsahu v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak změnit karty obsahu v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words for .NET je výkonná knihovna pro vytváření, úpravy a manipulaci s dokumenty Wordu v aplikaci C#. Mezi funkcemi, které Aspose.Words nabízí, existuje možnost úpravy karet použitých v obsahu dokumentu aplikace Word. V této příručce vám ukážeme, jak používat zdrojový kód C# Aspose.Words for .NET ke změně karet v obsahu dokumentu.

## Porozumění knihovně Aspose.Words

Než se ponoříte do kódu, je důležité porozumět knihovně Aspose.Words pro .NET. Aspose.Words je oblíbená knihovna, která usnadňuje a zefektivňuje zpracování textu s dokumenty aplikace Word. Nabízí širokou škálu funkcí pro vytváření, úpravy a manipulaci s dokumenty aplikace Word, včetně změny karet obsahu.

## Načítání dokumentu obsahujícího obsah

Prvním krokem je načtení dokumentu aplikace Word obsahující obsah, který chcete upravit. Pomocí třídy Document načtěte dokument ze zdrojového souboru. Zde je příklad:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

V tomto příkladu načteme dokument "Tabulka obsahu.docx" umístěný v adresáři dokumentů.

## Změna karet v obsahu

Jakmile je dokument načten, projdeme každý odstavec dokumentu a zkontrolujeme, zda je formátován pomocí stylů výsledků obsahu (TOC). Pokud ano, upravíme tabulátory používané k zarovnání čísel stránek. Zde je postup:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

tomto příkladu používáme smyčku k procházení každého odstavce v dokumentu. Poté zkontrolujeme, zda je odstavec formátován pomocí stylů výsledků obsahu (TOC). Pokud ano, přistoupíme k první kartě použité v tomto odstavci a upravíme ji odstraněním staré karty a přidáním nové karty s upravenou pozicí.

## Uložte upravený dokument

Jakmile provedete potřebné změny na kartách v obsahu, můžete upravený dokument uložit pomocí metody Save třídy Document. Zde je příklad:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

V tomto příkladu uložíme upravený dokument jako „WorkingWithTableOfContent.ChangeTocTabStops.docx“.

### Ukázkový zdrojový kód pro funkci "Upravit obsah karet" s Aspose.Words pro .NET

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument obsahující obsah
Document doc = new Document(dataDir + "Table of contents.docx");

// Upravte záložky obsahu
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

// Uložte upravený dokument
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Závěr

této příručce jsme se zabývali tím, jak používat Aspose.Words pro .NET ke změně karet v obsahu dokumentu aplikace Word pomocí poskytnutého zdrojového kódu C#. Podle uvedených kroků můžete snadno přizpůsobit karty obsahu v dokumentech aplikace Word v aplikaci C#. Aspose.Words nabízí obrovskou flexibilitu a výkon pro práci se styly a formátováním vašich dokumentů, což vám umožňuje vytvářet atraktivní a profesionální dokumenty Word.

### Nejčastější dotazy pro změnu zarážky tabulátoru v dokumentu aplikace Word

#### Otázka: Jaký je účel funkce "Změnit zarážky Toc v dokumentu Word" v Aspose.Words for .NET?

Odpověď: Funkce "Změnit zarážky tabulátoru obsahu v dokumentu aplikace Word" v Aspose.Words for .NET umožňuje upravit zarážky tabulátoru použité v obsahu dokumentu aplikace Word. Umožňuje vám přizpůsobit zarovnání a umístění čísel stránek a odpovídajících nadpisů v obsahu.

#### Otázka: Co je Aspose.Words for .NET?

A: Aspose.Words for .NET je výkonná knihovna navržená pro zpracování textu s dokumenty Word v aplikacích .NET. Poskytuje komplexní funkce pro vytváření, úpravu, manipulaci a převod dokumentů aplikace Word programově pomocí C# nebo jiných jazyků .NET.

#### Otázka: Jak načtu dokument aplikace Word obsahující obsah pomocí Aspose.Words for .NET?

 Odpověď: Chcete-li načíst dokument aplikace Word obsahující obsah pomocí Aspose.Words for .NET, můžete použít`Document` třída a její konstruktér. Zadáním cesty k souboru dokumentu jej můžete načíst do a`Document` objekt. Zde je příklad:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Tento fragment kódu načte dokument "Table of content.docx" umístěný v určeném adresáři.

#### Otázka: Jak mohu změnit karty použité v obsahu pomocí Aspose.Words for .NET?

 Odpověď: Jakmile je dokument načten, můžete iterovat každý odstavec dokumentu a zkontrolovat, zda je formátován pomocí stylů výsledků obsahu (TOC). Pokud je odstavec formátován jako styl obsahu, můžete upravit tabulátory používané k zarovnání čísel stránek. V Aspose.Words pro .NET máte přístup k`ParagraphFormat` vlastnost každého odstavce pro načtení a úpravu zarážek tabulátoru. Zde je příklad:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        TabStop tab = para.ParagraphFormat.TabStops[0];
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }
}
```

tomto kódu smyčka prochází každým odstavcem v dokumentu. Pokud má odstavec styl obsahu, přistoupí k první zarážce tabulátoru použité v tomto odstavci, odstraní ji a přidá novou zarážku tabulátoru s upravenou pozicí.

#### Otázka: Mohu změnit karty pro více úrovní v obsahu pomocí Aspose.Words for .NET?

Odpověď: Ano, pomocí Aspose.Words for .NET můžete změnit záložky pro více úrovní v obsahu. Procházením každého odstavce a kontrolou stylu obsahu můžete upravovat karty pro každou úroveň jednotlivě. Můžete získat přístup k požadované úrovni obsahu a podle toho upravit zarážky tabulátoru.

#### Otázka: Jak uložím upravený dokument po změně karet v obsahu pomocí Aspose.Words for .NET?

 Odpověď: Po provedení nezbytných změn na kartách v obsahu můžete upravený dokument uložit pomocí`Save` metoda`Document` třída. Zadejte požadovanou cestu k souboru a název výstupního dokumentu jako parametr`Save` metoda. Zde je příklad:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Tento kód uloží upravený dokument jako "WorkingWithTableOfContent.ChangeTocTabStops.docx".

#### Otázka: Mohu upravit další aspekty obsahu pomocí Aspose.Words for .NET?

Odpověď: Ano, pomocí Aspose.Words pro .NET můžete přizpůsobit různé aspekty obsahu. Kromě změny karet můžete upravit styly písma, velikost, zarovnání a další vlastnosti formátování položek obsahu a čísel stránek. Navíc můžete upravit odsazení, mezery a formátování odpovídajících nadpisů.

#### Otázka: Mohu změnit zarovnání tabulátoru a vodicí znaky pro obsah pomocí Aspose.Words for .NET?

Odpověď: Ano, pomocí Aspose.Words for .NET můžete změnit zarovnání tabulátoru a vodicí znaky pro obsah. Přístupem k zarážkám tabulátoru a úpravou jejich vlastností zarovnání a odkazu můžete ovládat zarovnání a vizuální vzhled čísel stránek a odpovídajících nadpisů v obsahu.

#### Otázka: Podporuje Aspose.Words for .NET změnu jiných stylů a formátování v dokumentech aplikace Word?

Odpověď: Ano, Aspose.Words for .NET poskytuje rozsáhlou podporu pro změnu různých stylů a formátování v dokumentech aplikace Word. Umožňuje vám upravovat styly pro různé prvky, jako jsou odstavce, nadpisy, tabulky, seznamy a další. Můžete změnit písma, barvy, zarovnání, odsazení, mezery a další aspekty formátování podle vašich požadavků.

#### Otázka: Mohu upravit karty v obsahu v existujícím dokumentu aplikace Word pomocí Aspose.Words for .NET?

Odpověď: Ano, můžete upravit záložky v obsahu v existujícím dokumentu aplikace Word pomocí Aspose.Words for .NET. Načtením dokumentu, procházením odstavců a provedením nezbytných změn zarážek tabulátoru můžete aktualizovat tabulátory v obsahu. Nakonec dokument uložte, abyste použili úpravy.