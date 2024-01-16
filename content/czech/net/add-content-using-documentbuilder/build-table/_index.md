---
title: Sestavte tabulku v dokumentu aplikace Word
linktitle: Sestavte tabulku v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/add-content-using-documentbuilder/build-table/
---
V tomto podrobném tutoriálu se naučíte, jak vytvořit tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET. Provedeme vás celým procesem a poskytneme vám potřebné úryvky kódu C#. Na konci této příručky budete schopni vytvořit tabulku s vlastním formátováním a obsahem pomocí třídy DocumentBuilder.

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Knihovna Aspose.Words for .NET nainstalovaná ve vašem systému.

## Krok 1: Vytvořte nový dokument
Chcete-li začít, vytvořte nový dokument pomocí třídy Document:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Spusťte tabulku
Dále pomocí metody StartTable třídy DocumentBuilder začněte sestavovat tabulku:

```csharp
Table table = builder.StartTable();
```

## Krok 3: Vložte buňky a přidejte obsah
Nyní můžete do tabulky vkládat buňky a přidávat do nich obsah pomocí metod InsertCell a Write třídy DocumentBuilder. Upravte formátování buněk podle potřeby:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Krok 4: Ukončete řádek
Po přidání obsahu do buněk prvního řádku použijte k ukončení řádku metodu EndRow třídy DocumentBuilder:

```csharp
builder.EndRow();
```

## Krok 5: Přizpůsobte formátování řádků
Formátování řádku můžete přizpůsobit nastavením vlastností objektů RowFormat a CellFormat:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Krok 6: Ukončete tabulku
K dokončení tabulky použijte metodu EndTable třídy DocumentBuilder:

```csharp
builder.EndTable();
```

### Příklad zdrojového kódu pro vytvoření tabulky pomocí Aspose.Words pro .NET
Zde je kompletní zdrojový kód pro vytvoření tabulky pomocí Aspose.Words pro .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak vytvořit tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete nyní vytvářet tabulky s vlastním formátováním.

### Nejčastější dotazy k sestavení tabulky v dokumentu aplikace Word

#### Otázka: Co je Aspose.Words for .NET?

Odpověď: Aspose.Words for .NET je výkonná knihovna pro zpracování dokumentů, která umožňuje vývojářům vytvářet, číst, upravovat a převádět dokumenty Microsoft Word programově v aplikacích .NET. Poskytuje širokou škálu funkcí pro práci s dokumenty aplikace Word, jako je manipulace s textem, vytváření tabulek, ochrana dokumentů, formátování a další.

#### Otázka: Jak mohu vytvořit tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET?

Odpověď: Chcete-li vytvořit tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET, můžete postupovat takto:
1.  Vytvořte novou instanci souboru`Document` třída a a`DocumentBuilder` objekt.
2.  Použijte`StartTable` metoda`DocumentBuilder`třídy začít sestavovat tabulku.
3.  Vložte buňky do tabulky a přidejte obsah pomocí`InsertCell` a`Write` metody`DocumentBuilder` třída.
4.  Ukončete řádek pomocí`EndRow` metoda`DocumentBuilder` třída.
5.  Přizpůsobte formátování řádků nastavením vlastností souboru`RowFormat` a`CellFormat` objektů.
6.  Ukončete tabulku pomocí`EndTable` metoda`DocumentBuilder` třída.
7. Uložte dokument.

#### Otázka: Jak mohu přizpůsobit formátování tabulky a jejích buněk?

 Odpověď: Formátování tabulky a jejích buněk můžete přizpůsobit nastavením různých vlastností tabulky`RowFormat` a`CellFormat` objektů. Můžete například upravit zarovnání buněk, vertikální a horizontální orientaci textu, výšku buňky, výšku řádku a další. Pomocí těchto vlastností můžete dosáhnout požadovaného vzhledu tabulky a jejího obsahu.

#### Otázka: Mohu vytvářet složité tabulky se sloučenými buňkami a dalšími pokročilými funkcemi?

 Odpověď: Ano, Aspose.Words for .NET poskytuje pokročilé funkce pro vytváření složitých tabulek, včetně podpory sloučených buněk, vnořených tabulek a rozložení složitých tabulek. Můžete použít`MergeCells` způsob sloučení buněk,`StartTable`metoda k vytvoření vnořených tabulek a další metody k dosažení požadované struktury tabulky.

#### Otázka: Je Aspose.Words for .NET kompatibilní s různými formáty dokumentů aplikace Word?

Odpověď: Ano, Aspose.Words for .NET je kompatibilní s různými formáty dokumentů Word, včetně DOC, DOCX, RTF a dalších. Podporuje starší formáty (DOC) i moderní formáty založené na XML (DOCX) a umožňuje bezproblémovou práci s dokumenty v různých formátech.

#### Otázka: Kde najdu další informace a dokumentaci k Aspose.Words for .NET?

 Odpověď: Komplexní dokumentaci a příklady kódu naleznete na[Reference API](https://reference.aspose.com/words/net/). Dokumentace poskytne podrobné informace o funkcích knihovny a o tom, jak je používat ve vašich aplikacích .NET.