---
title: Rastrování transformovaných prvků
linktitle: Rastrování transformovaných prvků
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak zakázat rasterizaci transformovaných prvků při převodu do formátu PCL pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words for .NET je výkonná knihovna pro vytváření, manipulaci a konverzi dokumentů aplikace Word v aplikaci C#. Mezi funkce, které Aspose.Words nabízí, patří schopnost rastrovat transformované prvky při převodu dokumentů do různých formátů. V této příručce vám ukážeme, jak pomocí zdrojového kódu C# Aspose.Words for .NET zakázat rasterizaci transformovaných prvků při převodu dokumentu do formátu PCL.

## Porozumění knihovně Aspose.Words

Než se ponoříte do kódu, je důležité porozumět knihovně Aspose.Words pro .NET. Aspose.Words je oblíbená knihovna, která usnadňuje a zefektivňuje zpracování textu s dokumenty aplikace Word. Nabízí širokou škálu funkcí pro vytváření, úpravy a převod dokumentů aplikace Word, včetně podpory rastrování transformovaných prvků během převodu.

## Načítání dokumentu aplikace Word

Prvním krokem je načtení dokumentu aplikace Word, který chcete převést do formátu PCL. Pomocí třídy Document načtěte dokument ze zdrojového souboru. Zde je příklad:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

V tomto příkladu načítáme dokument „Rendering.docx“ umístěný v adresáři dokumentů.

## Konfigurace možností zálohování

Dalším krokem je konfigurace možností uložení pro převod do formátu PCL. Použijte třídu PclSaveOptions a nastavte vlastnost RasterizeTransformedElements na hodnotu false. Jak na to:

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

Vytvoříme nový objekt PclSaveOptions a nastavíme vlastnost SaveFormat na SaveFormat.Pcl, abychom určili, že chceme dokument uložit ve formátu PCL. Dále nastavíme vlastnost RasterizeTransformedElements na false, abychom zakázali rastrování transformovaných prvků.

## Převod dokumentu do formátu PCL

Nyní, když jsme nakonfigurovali možnosti uložení, můžeme přistoupit k převodu dokumentu do formátu PCL. Pomocí metody Save třídy Document uložte převedený dokument ve formátu PCL zadáním voleb uložení. Zde je příklad:

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

V tomto příkladu uložíme převedený dokument jako "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl" pomocí zadaných možností uložení.

### Příklad zdrojového kódu pro funkci "Rasterize Transformed Elements" s Aspose.Words pro .NET

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Načtěte dokument aplikace Word


Document doc = new Document(dataDir + "Rendering.docx");

// Nakonfigurujte možnosti zálohování pro převod do formátu PCL
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// Převeďte dokument do formátu PCL
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## Závěr

této příručce jsme se zabývali tím, jak pomocí Aspose.Words for .NET zakázat rasterizaci transformovaných prvků při převodu dokumentu do formátu PCL pomocí dodaného zdrojového kódu C#. Podle uvedených kroků můžete snadno ovládat chování rastrování transformovaných prvků při převodu dokumentů aplikace Word do různých formátů. Aspose.Words nabízí obrovskou flexibilitu a výkon pro práci s transformovanými prvky, což vám umožňuje vytvářet převedené dokumenty přesně podle vašich specifických potřeb.