---
title: Escape URI v dokumentu PDF
linktitle: Escape URI v dokumentu PDF
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce Jak uniknout URI v dokumentu PDF pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/escape-uri/
---

Tento článek poskytuje krok za krokem návod, jak Escape URI v dokumentu PDF pomocí Aspose.Words pro .NET. Každou část kódu si podrobně vysvětlíme. Na konci tohoto tutoriálu budete schopni porozumět tomu, jak vložit hypertextové odkazy s kódovaným Uri do dokumentu.

Než začnete, ujistěte se, že jste ve svém projektu nainstalovali a nakonfigurovali knihovnu Aspose.Words for .NET. Knihovnu a pokyny k instalaci najdete na webu Aspose.

## Krok 1: Definujte adresář dokumentů

 Chcete-li začít, musíte definovat cestu k adresáři, kde jsou umístěny vaše dokumenty. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte dokument a DocumentBuilder

 Dále musíme vytvořit nový`Document` objekt a a`DocumentBuilder` objekt k vytvoření dokumentu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Vložte hypertextové odkazy s kódem Uri

 Použijte`InsertHyperlink` metoda`DocumentBuilder` objekt pro vložení hypertextových odkazů do dokumentu. Uri musí uniknout pomocí`Uri.EscapeUriString` funkce, aby se zabránilo chybám ve formátu.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), nepravda);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), nepravda);
```

## Krok 4: Uložte dokument jako PDF

 Nakonec můžeme dokument uložit jako PDF pomocí`Save` metoda`Document` objekt. Zadejte název výstupního souboru.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

To je vše ! Úspěšně jste do dokumentu pomocí Aspose.Words for .NET vložili hypertextové odkazy s kódem Uri.

### Ukázka zdrojového kódu pro únik Uri pomocí Aspose.Words pro .NET


```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", false);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", false);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## Závěr

V tomto tutoriálu jsme se zabývali tím, jak uniknout z URI v dokumentu PDF pomocí Aspose.Words pro .NET. Escapováním URI se můžete vyhnout chybám ve formátování a zajistit, aby byly hypertextové odkazy správně interpretovány a zobrazeny v dokumentu PDF. Chcete-li do dokumentu PDF vložit hypertextové odkazy s kódem URI, postupujte podle uvedených kroků. Určitě uteč.

### Často kladené otázky

#### Otázka: Co je escape URI v dokumentu PDF a proč je důležité?
Odpověď: Escape URI v dokumentu PDF odkazuje na metodu převodu speciálních znaků v URL na escape sekvence, aby se předešlo chybám ve formátu. To je důležité, protože speciální znaky v adrese URL mohou narušit strukturu adresy URL a vést k nesprávné interpretaci nebo nesprávnému vykreslení. Escapováním speciálních znaků zaručujeme, že adresa URL bude správně interpretována a zobrazena v dokumentu PDF.

#### Otázka: Jak mohu pomocí Aspose.Words for .NET uniknout identifikátorům URI v dokumentu PDF?
Odpověď: Chcete-li uniknout identifikátorům URI v dokumentu PDF pomocí Aspose.Words for .NET, postupujte takto:

 Nahrazením nastavte cestu k adresáři, kde jsou umístěny vaše dokumenty`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

 Vytvořte novou instanci souboru`Document` třída a a`DocumentBuilder` objekt k vytvoření dokumentu.

 Použijte`InsertHyperlink` metoda`DocumentBuilder` objekt pro vložení hypertextových odkazů do dokumentu. Nezapomeňte uniknout URI pomocí`Uri.EscapeUriString` funkce, aby se zabránilo chybám ve formátu.

 Použijte`Save` metoda`Document` objekt pro uložení dokumentu ve formátu PDF zadáním názvu výstupního souboru.

#### Otázka: Jaké jsou výhody escapování URI v dokumentu PDF?
Odpověď: Výhody escapování URI v dokumentu PDF jsou:

Prevence chyb formátu: Escapování URI pomáhá předcházet chybám formátu způsobeným speciálními znaky v adrese URL a zajišťuje, že adresa URL je správně interpretována a zobrazena v dokumentu PDF.

Kompatibilita se čtečkami PDF: Unifikované URI jsou čtečkami PDF obecně dobře podporovány, což zajišťuje lepší kompatibilitu a konzistentní uživatelskou zkušenost.

#### Otázka: Jaké speciální znaky by měly být v URI kódovány?
 A: Speciální znaky, které musí být v URI uvozeny, jsou: mezera, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.