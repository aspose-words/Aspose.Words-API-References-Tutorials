---
title: Formát čísla Pro Osu V Grafu
linktitle: Formát čísla Pro Osu V Grafu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak nastavit formát čísla pro osu v grafu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-charts/number-format-for-axis/
---

Tento tutoriál vysvětluje, jak používat Aspose.Words pro .NET k nastavení formátu čísla pro osu v grafu. Poskytnutý zdrojový kód ukazuje, jak vytvořit graf, přidat data řad a formátovat popisky os.

## Krok 1: Nastavte projekt

Ujistěte se, že máte následující předpoklady:

- Nainstalovaná knihovna Aspose.Words for .NET. Můžete si jej stáhnout pomocí správce balíčků NuGet k instalaci.
- Cesta k adresáři dokumentu, kam bude výstupní dokument uložen.

## Krok 2: Vytvořte nový dokument a vložte graf

 Vytvoř nový`Document` objekt a a`DocumentBuilder` k vytvoření dokumentu.

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Dále použijte`InsertChart` metoda`DocumentBuilder` pro vložení sloupcového grafu do dokumentu.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Přidejte do grafu data řady

Přidejte do grafu data řady. V tomto příkladu přidáme pět položek s jejich odpovídajícími hodnotami.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Krok 4: Naformátujte popisky os

 Chcete-li nastavit formát čísel pro štítky osy Y, přejděte na`AxisY` vlastnost grafu a nastavte`NumberFormat.FormatCode` vlastnost do požadovaného formátu. V tomto příkladu jsme nastavili formát na "#,##0" pro zobrazení čísel s oddělovači tisíců.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Krok 5: Uložte dokument

 Nakonec uložte dokument do určeného adresáře pomocí`Save` metoda`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Tím je implementace nastavení formátu čísel pro osu pomocí Aspose.Words for .NET dokončena.

### Příklad zdrojového kódu pro Number Format For Axis pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Závěr

V tomto tutoriálu jste se naučili, jak nastavit formát čísla pro osu v grafu pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete vytvořit nový dokument, vložit sloupcový graf, přidat data řad a formátovat popisky os tak, aby zobrazovaly čísla v určitém formátu.

Aspose.Words for .NET poskytuje výkonné funkce pro přizpůsobení vzhledu grafů v dokumentech aplikace Word. Nastavením formátu čísel pro popisky os můžete ovládat způsob zobrazení čísel, včetně možností, jako jsou desetinná místa, oddělovače tisíců, symboly měn a další. To vám umožní prezentovat číselná data jasným a smysluplným způsobem.

Aspose.Words for .NET máte flexibilitu při formátování různých aspektů grafu, včetně označení os. Nastavením formátu čísel pro osu můžete zajistit konzistenci a zlepšit čitelnost grafu, což uživatelům usnadní interpretaci reprezentovaných hodnot.

### Nejčastější dotazy

#### Q1. Jaký je formát čísla pro osu v grafu?
Formát čísel pro osu v grafu odkazuje na formátování aplikované na číselné hodnoty zobrazené na ose. Umožňuje vám ovládat způsob zobrazení čísel, včetně možností, jako jsou desetinná místa, oddělovače tisíců, symboly měn, znaky procent a další. Nastavením formátu čísel můžete přizpůsobit vzhled číselných údajů v grafu tak, aby vyhovoval vašim konkrétním požadavkům.

#### Q2. Jak mohu nastavit formát čísel pro popisky os?
 Chcete-li nastavit formát čísel pro popisky os v grafu pomocí Aspose.Words for .NET, můžete získat přístup k`AxisY` vlastnost grafu a nastavte`NumberFormat.FormatCode`vlastnost na požadovaný formátový kód. Kód formátu se řídí syntaxí standardních číselných vzorů formátování a určuje, jak se čísla zobrazují. Například můžete použít "#,##0.00" k zobrazení čísel se dvěma desetinnými místy a oddělovači tisíců.

#### Q3. Mohu nastavit různé formáty čísel pro štítky osy X a Y?
Ano, pomocí Aspose.Words for .NET můžete nastavit různé formáty čísel pro popisky osy X a Y. Přístup k příslušné ose (`AxisX` pro osu X popř`AxisY` pro osu Y) grafu a upravte`NumberFormat.FormatCode` vlastnost jednotlivě pro každou osu. To vám umožní použít různé formáty čísel na štítky na každé ose na základě vašich specifických požadavků.

#### Q4. Jaké jsou některé běžné kódy formátu čísel, které mohu použít?
Aspose.Words for .NET podporuje širokou škálu kódů formátu čísel, které můžete použít k formátování popisků os v grafu. Některé běžné formátové kódy zahrnují:

- `0` nebo`#` - Zobrazí číslo bez desetinných míst.
- `0.00` nebo`#.00` - Zobrazí číslo se dvěma desetinnými místy.
- `#,##0` Zobrazí číslo s oddělovači tisíců.
- `"€"0.00` - Zobrazí číslo se symbolem měny Euro a dvěma desetinnými místy.
- `"%"0` - Zobrazuje číslo v procentech.

 Více informací o čísle naleznete[formátové kódy](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) v API Reference Aspose.Words pro .NET.

#### Q5. Mohu přizpůsobit další vlastnosti štítků os?
Ano, Aspose.Words for .NET poskytuje širokou škálu vlastností pro přizpůsobení vzhledu a chování popisků os. Kromě formátu čísel můžete upravit vlastnosti, jako je písmo, velikost, barva, orientace, zarovnání a další. To vám umožní plně přizpůsobit štítky os tak, aby odpovídaly požadovanému stylu a požadavkům na prezentaci.