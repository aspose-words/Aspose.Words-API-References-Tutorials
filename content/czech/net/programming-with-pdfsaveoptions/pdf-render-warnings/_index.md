---
title: Upozornění k vykreslení PDF
linktitle: Upozornění k vykreslení PDF
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce řešením varování při vykreslování PDF pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/pdf-render-warnings/
---

Tento článek poskytuje krok za krokem průvodce, jak používat funkci upozornění při vykreslování PDF s Aspose.Words for .NET. Každou část kódu si podrobně vysvětlíme. Na konci tohoto tutoriálu budete schopni porozumět tomu, jak se vypořádat s varováními při vykreslování při převodu do PDF.

Než začnete, ujistěte se, že jste ve svém projektu nainstalovali a nakonfigurovali knihovnu Aspose.Words for .NET. Knihovnu a pokyny k instalaci najdete na webu Aspose.

## Krok 1: Definujte adresář dokumentů

 Chcete-li začít, musíte definovat cestu k adresáři, kde jsou umístěny vaše dokumenty. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Nahrajte dokument

Dále musíme načíst dokument, který chceme zpracovat. V tomto příkladu předpokládáme, že dokument se nazývá "WMF s image.docx" a je umístěn v určeném adresáři dokumentů.

```csharp
Document doc = new Document(dataDir + "WMF with image.docx");
```

## Krok 3: Nakonfigurujte možnosti uložení jako PDF s upozorněními na vykreslování

 Abychom zvládli varování při vykreslování při převodu do PDF, musíme nakonfigurovat`MetafileRenderingOptions` objekt k určení způsobu vykreslování metasouborů. Používáme také`HandleDocumentWarnings` možnost zpracování varování generovaných při ukládání dokumentu.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     EmulateRasterOperations = false,
     RenderingMode = MetafileRenderingMode.VectorWithFallback
};

PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
```

## Krok 4: Uložte dokument jako PDF s upozorněním na vykreslování

Nakonec můžeme dokument uložit ve formátu PDF pomocí dříve nakonfigurovaných možností uložení.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);
```

## Krok 5: Zvládněte varování při vykreslování

Varování vykreslování generovaná při ukládání dokumentu lze získat pomocí obslužné rutiny vlastního varování. V tomto příkladu jednoduše vytiskneme popis každého varování.

```csharp
foreach(WarningInfo warningInfo in callback.mWarnings)
{
     Console.WriteLine(warningInfo.Description);
}
```

To je vše ! Úspěšně jste zpracovali varování vykreslování při převodu dokumentu

  do PDF pomocí Aspose.Words for .NET.

### Ukázkový zdrojový kód pro varování při vykreslování PDF pomocí Aspose.Words pro .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with image.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		EmulateRasterOperations = false, RenderingMode = MetafileRenderingMode.VectorWithFallback
	};

	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	//Pokud Aspose.Words nemůže správně vykreslit některé záznamy metasouboru
	// na vektorovou grafiku pak Aspose.Words vykreslí tento metasoubor do bitmapy.
	HandleDocumentWarnings callback = new HandleDocumentWarnings();
	doc.WarningCallback = callback;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);

	// Zatímco se soubor úspěšně ukládá, jsou zde shromažďována varování vykreslování, ke kterým došlo během ukládání.
	foreach (WarningInfo warningInfo in callback.mWarnings)
	{
		Console.WriteLine(warningInfo.Description);
	}
        
```

### Často kladené otázky

#### Otázka: Jaká je funkce varování při vykreslování PDF pomocí Aspose.Words pro .NET?
Funkce upozornění na vykreslování PDF s Aspose.Words for .NET pomáhá spravovat upozornění generovaná při převodu dokumentu do PDF. Poskytuje způsob, jak detekovat a řešit varování při vykreslování, aby byla zajištěna kvalita a integrita převedeného dokumentu.

#### Otázka: Jak mohu použít tuto funkci s Aspose.Words pro .NET?
Chcete-li použít tuto funkci s Aspose.Words pro .NET, postupujte takto:

Nastavte adresář dokumentů zadáním cesty k adresáři, kde jsou umístěny vaše dokumenty.

 Vložte dokument, který chcete zpracovat, pomocí`Document` a zadáním cesty k souboru.

 Nakonfigurujte možnosti uložení do PDF vytvořením instance souboru`PdfSaveOptions` třída. Použijte`MetafileRenderingOptions` třída k určení způsobu vykreslování metasouborů a nastavení`MetafileRenderingOptions.RenderingMode` na`MetafileRenderingMode.VectorWithFallback`.

 Použijte`HandleDocumentWarnings` třídy pro zpracování varování při vykreslování. Soubor`doc.WarningCallback` do instance této třídy.

 Použijte`Save` způsob uložení dokumentu ve formátu PDF s uvedením možností uložení.

Poté můžete zpracovat varování vykreslení pomocí`HandleDocumentWarnings` třída. Můžete například zobrazit popis každého varování pomocí smyčky.

#### Otázka: Jak zjistím, zda se při převodu dokumentu do PDF vyskytla nějaká varování při vykreslování?
 Můžete použít`HandleDocumentWarnings` třídy k načtení varování vykreslení generovaných při ukládání dokumentu. Tato třída obsahuje a`mWarnings` seznam, který ukládá informace o varováních. Můžete procházet tento seznam a přistupovat k vlastnostem každého varování, jako je popis, abyste mohli provést příslušnou akci.

#### Otázka: Jaký druh varování při vykreslování lze generovat při převodu do PDF?
Varování vykreslování při převodu do PDF mohou zahrnovat varování týkající se rozvržení, chybějících písem, nepodporovaných obrázků, problémů s kompatibilitou atd. Konkrétní varování budou záviset na obsahu zdrojového dokumentu a použitých možnostech převodu.

#### Otázka: Je možné zpracovat varování při vykreslování vlastním způsobem?
 Ano, zpracování varování při vykreslování můžete přizpůsobit přizpůsobením souboru`HandleDocumentWarnings`třída. Můžete přidat další funkce pro správu upozornění specifických pro vaši aplikaci, jako je protokolování upozornění, generování sestav, odesílání upozornění a další.