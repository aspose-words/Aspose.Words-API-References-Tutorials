---
title: Použít ohraničení a stínování na odstavec v dokumentu aplikace Word
linktitle: Použít ohraničení a stínování na odstavec v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak použít ohraničení a stínování na odstavec v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
tomto tutoriálu vám ukážeme, jak použít ohraničení a stínování na odstavec v dokumentu aplikace Word pomocí funkce Aspose.Words pro .NET. Chcete-li porozumět zdrojovému kódu a použít změny formátování, postupujte podle následujících kroků.

## Krok 1: Vytvoření a konfigurace dokumentu

Chcete-li začít, vytvořte nový dokument a přidružený objekt DocumentBuilder. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Konfigurace ohraničení

Nyní nakonfigurujeme ohraničení odstavce zadáním stylu ohraničení pro každou stranu. Zde je postup:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## Krok 3: Nastavení infill

Nyní nakonfigurujeme výplň odstavce zadáním textury a barev výplně. Zde je postup:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## Krok 4: Přidejte obsah

Do odstavce přidáme nějaký formátovaný obsah. Zde je postup:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## Krok 3: Uložení dokumentu

 Po vložení pole formuláře pro zadání textu uložte dokument na požadované místo pomocí`Save` metoda. Ujistěte se, že jste zadali správnou cestu k souboru:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Příklad zdrojového kódu pro použití ohraničení a stínování na odstavec pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód pro funkci Použít ohraničení a stínování na odstavec s Aspose.Words pro .NET:

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## Závěr

 V tomto tutoriálu jsme se naučili, jak použít ohraničení a stínování na odstavec v dokumentu aplikace Word pomocí Aspose.Words for .NET. Konfigurací odstavce`Borders` a`Shading` vlastnostmi jsme mohli nastavit styl ohraničení, barvu čáry a barvu výplně odstavce. Aspose.Words for .NET poskytuje výkonné možnosti formátování pro přizpůsobení vzhledu odstavců a vylepšení vizuální reprezentace vašich dokumentů.

### FAQ

#### Otázka: Jak mohu použít ohraničení a stínování na odstavec v dokumentu aplikace Word pomocí Aspose.Words for .NET?

Odpověď: Chcete-li použít ohraničení a stínování na odstavec v dokumentu aplikace Word pomocí Aspose.Words for .NET, postupujte takto:
1.  Vytvořte nový dokument a a`DocumentBuilder` objekt.
2.  Ohraničení odstavců nakonfigurujte přístupem k`Borders` vlastnictvím`ParagraphFormat` a nastavení stylu ohraničení pro každou stranu.
3. Nakonfigurujte výplň odstavce přístupem k`Shading` vlastnictvím`ParagraphFormat` a určení barvy textury a výplně.
4.  Přidejte obsah do odstavce pomocí`Write` metoda`DocumentBuilder`.
5.  Uložte dokument pomocí`Save` metoda.

#### Otázka: Jak nastavím styl ohraničení pro každou stranu odstavce?

 A: Chcete-li nastavit styl ohraničení pro každou stranu odstavce, můžete otevřít`Borders` vlastnictvím`ParagraphFormat` a nastavte`LineStyle` majetek pro každého`BorderType` (např.,`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). Můžete zadat různé styly čar jako např`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`, atd.

#### Otázka: Jak určím texturu a barvy výplně pro stínování odstavce?

 A: Chcete-li určit texturu a barvy výplně pro stínování odstavce, můžete otevřít`Shading` vlastnictvím`ParagraphFormat` a nastavte`Texture` vlastnost na požadovaný index textury (např.`TextureIndex.TextureDiagonalCross` ). Můžete také nastavit`BackgroundPatternColor` a`ForegroundPatternColor` vlastnosti na požadované barvy pomocí`System.Drawing.Color` třída.