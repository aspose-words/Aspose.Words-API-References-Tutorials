---
title: Vložit plovoucí obrázek do dokumentu aplikace Word
linktitle: Vložit plovoucí obrázek do dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vkládat plovoucí obrázky do dokumentů aplikace Word pomocí Aspose.Words for .NET. Průvodce krok za krokem.
type: docs
weight: 10
url: /cs/net/add-content-using-documentbuilder/insert-floating-image/
---
tomto komplexním příkladu se naučíte, jak vložit plovoucí obrázek do dokumentu aplikace Word pomocí Aspose.Words for .NET. Provedeme vás celým procesem a poskytneme vám potřebné úryvky kódu C#. Na konci této příručky budete moci ke svým dokumentům přidávat obrázky s přizpůsobitelnými možnostmi umístění a obtékání.

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Knihovna Aspose.Words for .NET nainstalovaná ve vašem systému.

## Krok 1: Vytvořte nový dokument a DocumentBuilder
Chcete-li začít, vytvořte nový dokument pomocí třídy Document a inicializujte objekt DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Vložte plovoucí obrázek
Dále použijte metodu InsertImage třídy DocumentBuilder k vložení plovoucího obrázku. Jako parametry zadejte cestu k souboru obrázku, relativní horizontální a vertikální polohu, šířku, výšku a možnosti obtékání:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## Krok 3: Uložte dokument
Po vložení plovoucího obrázku uložte dokument do souboru pomocí metody Save třídy Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## Příklad zdrojového kódu pro vložení plovoucího obrázku pomocí Aspose.Words pro .NET
Zde je kompletní zdrojový kód pro vložení plovoucího obrázku pomocí Aspose.Words pro .NET:
Plovoucí obrázky jsou užitečné pro různé scénáře, jako je přidávání log, ilustrací nebo dekorativních prvků, které lze umístit nezávisle na textu dokumentu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

Nezapomeňte upravit kód podle vašich konkrétních požadavků, včetně cesty k souboru obrázku a požadovaných možností umístění a zalamování.

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak vložit plovoucí obrázek do dokumentu aplikace Word pomocí Aspose.Words for .NET. Dodržováním tohoto podrobného průvodce a využitím poskytnutého zdrojového kódu nyní můžete vylepšit své dokumenty vizuálně přitažlivými a přizpůsobitelnými plovoucími obrázky.

### Časté dotazy pro vložení plovoucího obrázku do dokumentu aplikace Word

#### Otázka: Mohu vložit více plovoucích obrázků do jednoho dokumentu?

A: Určitě! Pomocí Aspose.Words for .NET můžete do dokumentu aplikace Word vložit libovolný počet plovoucích obrázků. Jednoduše opakujte proces vkládání a přidejte více vizuálně přitažlivých obrázků.

#### Otázka: Jaké možnosti obtékání jsou k dispozici pro plovoucí obrázek?

Odpověď: Aspose.Words for .NET poskytuje různé možnosti zalamování pro plovoucí obrázky, včetně čtvercového, těsného, průchozího, horního dna a žádného. Tyto možnosti určují, jak text interaguje s plovoucím obrázkem.

#### Otázka: Mohu upravit velikost plovoucího obrázku?

A: Rozhodně! Pomocí příslušných parametrů v metodě InsertImage můžete určit šířku a výšku plovoucího obrázku. To vám umožní ovládat rozměry obrazu podle vašich preferencí designu.

#### Otázka: Mohu umístit plovoucí obrázek vzhledem ke konkrétnímu prvku v dokumentu?

Odpověď: Ano, Aspose.Words for .NET vám umožňuje umístit plovoucí obrázek vzhledem ke konkrétním prvkům, jako je okraj, stránka, odstavec nebo tabulka. Pro dosažení požadovaného umístění můžete zvolit vhodné parametry relativní horizontální a vertikální polohy.

#### Otázka: Je Aspose.Words for .NET vhodný pro desktopové i webové aplikace?

Odpověď: Ano, Aspose.Words for .NET je všestranná knihovna vhodná pro desktopové i webové aplikace. Ať už vytváříte aplikaci pro Windows nebo webový systém, knihovnu můžete integrovat bez námahy.
