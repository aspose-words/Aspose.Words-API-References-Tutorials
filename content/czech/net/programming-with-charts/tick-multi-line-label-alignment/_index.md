---
title: Zaškrtněte víceřádkové zarovnání štítků v grafu
linktitle: Zaškrtněte víceřádkové zarovnání štítků v grafu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak zarovnat víceřádkové popisky v ose grafu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-charts/tick-multi-line-label-alignment/
---

Tento tutoriál vysvětluje, jak používat Aspose.Words pro .NET k nastavení zarovnání víceřádkových štítků v ose grafu. Poskytnutý zdrojový kód ukazuje, jak vytvořit graf, získat přístup k ose a upravit zarovnání štítků.

## Krok 1: Nastavte projekt

Ujistěte se, že máte následující předpoklady:

- Nainstalovaná knihovna Aspose.Words for .NET. Můžete si jej stáhnout pomocí správce balíčků NuGet k instalaci.
- Cesta k adresáři dokumentu, kam bude výstupní dokument uložen.

## Krok 2: Vytvořte nový dokument a vložte graf.

 Vytvoř nový`Document` objekt a a`DocumentBuilder` k vytvoření dokumentu.

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Dále použijte`InsertChart` metoda`DocumentBuilder` pro vložení bodového grafu do dokumentu.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Krok 3: Nastavte zarovnání štítků

 Chcete-li nastavit zarovnání víceřádkových štítků, přejděte na`AxisX` vlastnost grafu a nastavte`TickLabelAlignment` vlastnost k požadovanému zarovnání. V tomto příkladu nastavíme zarovnání na`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Krok 4: Uložte dokument

 Nakonec uložte dokument do určeného adresáře pomocí`Save` metoda`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Tím je implementace nastavení víceřádkového zarovnání štítků pomocí Aspose.Words pro .NET dokončena.

### Příklad zdrojového kódu pro Tick Multi Line Label Alignment pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Tato vlastnost má vliv pouze na víceřádkové štítky.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

## Závěr

V tomto tutoriálu jste se naučili, jak nastavit zarovnání víceřádkových štítků v ose grafu pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete vytvořit nový dokument, vložit bodový graf, získat přístup k ose grafu a upravit zarovnání štítků.

Aspose.Words for .NET poskytuje výkonné funkce pro manipulaci s grafy v dokumentech aplikace Word. Víceřádkové štítky jsou užitečné, když štítky os obsahují dlouhý text, který vyžaduje zalomení nebo rozdělení na více řádků. Nastavením zarovnání štítků můžete ovládat vodorovné zarovnání víceřádkových štítků v ose grafu a zajistit tak optimální prezentaci a čitelnost.

Přizpůsobení víceřádkového zarovnání štítků vám umožní doladit vzhled vašeho grafu, zejména při práci s dlouhými nebo složitými štítky. Zarovnáním štítků doprava, doleva, na střed nebo do bloku můžete dosáhnout vyváženého a vizuálně přitažlivého uspořádání štítků podél osy.

S Aspose.Words for .NET můžete snadno přistupovat k vlastnosti zarovnání štítků na ose grafu a upravovat je, což vám poskytuje plnou kontrolu nad vzhledem a rozložením štítků v grafech dokumentu aplikace Word.

### Nejčastější dotazy

#### Q1. Co jsou víceřádkové štítky na ose grafu?
Zaškrtávací víceřádkové štítky na ose grafu odkazují na štítky os, které se rozprostírají přes více řádků, když je text štítku dlouhý nebo vyžaduje zalomení, aby se vešel do dostupného prostoru. Namísto zkrácení textu štítku nebo vizuálního nepořádku osa grafu automaticky rozděluje štítky na více řádků, aby byla zajištěna čitelnost. Zaškrtávací víceřádkové štítky jsou užitečné zejména při práci s dlouhými štítky kategorií nebo hodnot v grafech.

#### Q2. Mohu přizpůsobit zarovnání štítků na ose grafu?
 Ano, můžete upravit zarovnání štítků v ose grafu pomocí Aspose.Words for .NET. Přístupem k`TickLabelAlignment` vlastnictvím`ChartAxis` objektu, můžete nastavit požadované zarovnání pro popisky. Možnosti zarovnání zahrnují zarovnání doleva, doprava, na střed nebo do bloku. Úprava zarovnání vám umožňuje ovládat horizontální umístění štítků podél osy grafu, což zajišťuje správnou čitelnost a vizuální prezentaci.

#### Q3. Kdy bych měl zvážit změnu zarovnání štítku na ose grafu?
Změna zarovnání štítků v ose grafu je výhodná, pokud máte dlouhé štítky nebo štítky s více řádky, které vyžadují optimální prezentaci a čitelnost. Úpravou zarovnání můžete zajistit, aby byly štítky správně zarovnány a rozmístěny, aby nedocházelo k překrývání nebo ořezávání. Zvažte změnu zarovnání štítků při práci s grafy, které mají dlouhé názvy kategorií, popisky s podrobnými hodnotami nebo jiné scénáře, kde výchozí zarovnání neposkytuje požadovaný vizuální vzhled.

#### Q4. Ovlivňuje zarovnání štítků jednořádkové štítky na ose grafu?
Ne, vlastnost zarovnání štítků neovlivňuje jednořádkové štítky na ose grafu. Je speciálně navržen pro víceřádkové etikety, které vyžadují balení nebo dělení. Jednořádkové popisky jsou zarovnány na základě výchozího nastavení zarovnání osy grafu. Vlastnost zarovnání štítků se vztahuje pouze na štítky, které se rozprostírají přes více řádků, což vám umožňuje řídit zarovnání každého řádku v rámci víceřádkového štítku.

#### Q5. Mohu odlišně zarovnat štítky pro osu X a osu Y v grafu?
 Ano, pomocí Aspose.Words for .NET můžete v grafu zarovnat popisky zatržení odlišně pro osu X a osu Y. Vlastnost zarovnání štítků je specifická pro každou osu grafu. Přístupem k odpovídajícímu`ChartAxis` objekt pro osu X nebo osu Y, můžete nezávisle nastavit zarovnání štítku na různé hodnoty. To vám poskytuje flexibilitu pro různé zarovnání štítků na základě vašich specifických požadavků pro každou osu v grafu.