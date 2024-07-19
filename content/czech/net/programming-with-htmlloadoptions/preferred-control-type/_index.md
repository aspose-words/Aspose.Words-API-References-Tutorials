---
title: Preferovaný typ ovládacího prvku v dokumentu aplikace Word
linktitle: Preferovaný typ ovládacího prvku v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce určením preferovaného typu ovládacího prvku v dokumentu aplikace Word při načítání dokumentu HTML pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-htmlloadoptions/preferred-control-type/
---
Tento článek poskytuje podrobného průvodce, jak používat preferovaný typ ovládacího prvku s Aspose.Words pro .NET. Každou část kódu si podrobně vysvětlíme. Na konci tohoto tutoriálu budete schopni porozumět tomu, jak určit preferovaný typ ovládacího prvku při načítání dokumentu HTML.

Než začnete, ujistěte se, že jste ve svém projektu nainstalovali a nakonfigurovali knihovnu Aspose.Words for .NET. Knihovnu a pokyny k instalaci najdete na webu Aspose.

## Krok 1: Definujte HTML kód

 Chcete-li začít, musíte definovat kód HTML, který chcete načíst jako dokument. V tomto příkladu jsme definovali an`html` proměnná obsahující HTML kód selektoru s volbami.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## Krok 2: Nastavte možnosti načítání HTML

 Dále vytvoříme`HtmlLoadOptions` objekt a nastavte`PreferredControlType`majetek do`HtmlControlType.StructuredDocumentTag`. To říká Aspose.Words, aby použil StructuredDocumentTags k reprezentaci HTML při načítání.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Krok 3: Načtěte a uložte dokument

 Používáme`Document` třídy k načtení kódu HTML z paměťového toku s dříve definovanými možnostmi načítání. Poté dokument uložíme do určeného adresáře s`.docx`formát souboru.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Příklad zdrojového kódu pro preferovaný typ ovládání s Aspose.Words pro .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

To je vše ! Úspěšně jste zadali preferovaný typ ovládacího prvku při načítání dokumentu HTML pomocí Aspose.Words for .NET.

## Závěr

 Podle tohoto podrobného průvodce jste se naučili používat funkci "Preferovaný typ ovládacího prvku" v Aspose.Words pro .NET k určení požadovaného typu ovládacího prvku při načítání dokumentu HTML. Nastavení`PreferredControlType`majetek do`HtmlControlType.StructuredDocumentTag` umožňuje Aspose.Words používat StructuredDocumentTags (SDT) pro lepší reprezentaci a zpracování obsahu HTML. Můžete také prozkoumat další typy ovládání, aby vyhovovaly vašim specifickým požadavkům. Použití této funkce pomáhá zajistit přesné a efektivní zpracování dokumentů HTML ve vaší aplikaci C# pomocí Aspose.Words.

### Časté dotazy pro preferovaný typ ovládacího prvku v dokumentu aplikace Word

#### Otázka: Co je funkce "Preferovaný typ ovládání" v Aspose.Words pro .NET?

Odpověď: Funkce "Preferovaný typ ovládacího prvku" vám umožňuje určit preferovaný typ ovládacího prvku pro reprezentaci prvků HTML při načítání dokumentu HTML. Pomáhá při výběru vhodného typu ovládacího prvku pro lepší reprezentaci a zpracování obsahu HTML.

#### Otázka: Jak nastavím preferovaný typ ovládacího prvku při načítání dokumentu HTML?

 A: Chcete-li nastavit preferovaný typ ovládání, musíte vytvořit`HtmlLoadOptions` objekt a nastavte jej`PreferredControlType` vlastnost k požadovanému`HtmlControlType` . V uvedeném příkladu`HtmlControlType.StructuredDocumentTag` se používá.

#### Otázka: Jaký význam má použití strukturovaných značek dokumentů (SDT) jako preferovaného typu ovládacího prvku?

Odpověď: StructuredDocumentTags (SDT) jsou prvky založené na XML, které lze použít k reprezentaci komplexního obsahu a ovládacích prvků v dokumentu aplikace Word. Použití SDT jako preferovaného typu ovládacího prvku může zajistit lepší kompatibilitu a reprezentaci obsahu HTML.

#### Otázka: Jak mohu zajistit, aby Aspose.Words používal preferovaný typ ovládacího prvku při načítání dokumentu HTML?

 A: Nastavením`PreferredControlType`majetek do`HtmlControlType.StructuredDocumentTag`jak je znázorněno v příkladu zdrojového kódu, Aspose.Words použije SDT k reprezentaci prvků HTML při načítání dokumentu.

#### Otázka: Mohu jako preferovanou možnost použít jiné typy ovládacích prvků?

 A: Ano, kromě`HtmlControlType.StructuredDocumentTag` , Aspose.Words for .NET podporuje další typy ovládání, jako např`HtmlControlType.ContentControl`a`HtmlControlType.CustomXmlMarkup`.