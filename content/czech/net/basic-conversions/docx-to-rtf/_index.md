---
title: Převést Docx na Rtf
linktitle: Převést Docx na Rtf
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se převádět dokumenty aplikace Word z formátu Docx do formátu RTF pomocí Aspose.Words for .NET. Výukový program krok za krokem s ukázkovým zdrojovým kódem.
type: docs
weight: 10
url: /cs/net/basic-conversions/docx-to-rtf/
---

V tomto podrobném tutoriálu vás provedeme tím, jak používat Aspose.Words pro .NET k převodu dokumentu aplikace Word ve formátu Docx na RTF. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat do vašich vlastních projektů.

 Chcete-li začít, ujistěte se, že máte Aspose.Words for .NET nainstalovaný a nastavený ve svém vývojovém prostředí. Pokud jste tak neučinili, stáhněte si a nainstalujte knihovnu z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Čtení dokumentu ze streamu

Nejprve otevřete stream a přečtěte si dokument Docx:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Stream stream = File.OpenRead(MyDir + "Document.docx");
```

## Krok 2: Vložení dokumentu

Dále načtěte dokument ze streamu:

```csharp
Document doc = new Document(stream);
```

## Krok 3: Zavření streamu

Protože je dokument načten do paměti, můžete stream zavřít:

```csharp
stream.Close();
```

## Krok 4: Provádění operací na dokumentu

V tomto okamžiku můžete s dokumentem provádět libovolné požadované operace.

## Krok 5: Uložení dokumentu ve formátu RTF

Chcete-li dokument uložit ve formátu RTF, uložte jej do paměti:

```csharp
MemoryStream dstStream = new MemoryStream();
doc.Save(dstStream, SaveFormat.Rtf);
```

## Krok 6: Přetočení streamu zpět

Před zápisem datového proudu paměti do souboru převiňte jeho pozici zpět na nulu:

```csharp
dstStream.Position = 0;
```

## Krok 7: Zápis streamu do souboru

Nakonec zapište datový proud paměti do souboru RTF:

```csharp
File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
```

A je to! Úspěšně jste převedli dokument aplikace Word ve formátu Docx na RTF pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro Docx To Rtf pomocí Aspose.Words pro .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Aspose.Words k načtení dokumentu stačí přístup pouze pro čtení.
	Stream stream = File.OpenRead(MyDir + "Document.docx");

	Document doc = new Document(stream);
	// Stream můžete nyní zavřít, již není potřeba, protože dokument je v paměti.
	stream.Close();

	// ... udělejte něco s dokumentem.

	// Převeďte dokument do jiného formátu a uložte jej do streamu.
	MemoryStream dstStream = new MemoryStream();
	doc.Save(dstStream, SaveFormat.Rtf);

	// Přetočte pozici streamu zpět na nulu, aby byla připravena pro další čtečku.
	dstStream.Position = 0;

	File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
	
```

Neváhejte použít tento kód ve svých vlastních projektech a upravit jej podle svých konkrétních požadavků.

### Nejčastější dotazy

#### Jak mohu převést soubor DOCX do formátu RTF?

Chcete-li převést soubor DOCX do formátu RTF, můžete použít různé softwarové nástroje nebo knihovny, které tuto funkci poskytují. Jedním z takových spolehlivých nástrojů je Aspose.Words for .NET. Nabízí jednoduchý a efektivní způsob, jak programově převést soubory DOCX do formátu RTF. K načtení souboru DOCX a jeho uložení v požadovaném formátu RTF můžete použít rozhraní API knihovny.

#### Existují nějaká omezení procesu převodu?

Omezení procesu převodu závisí na konkrétním nástroji nebo knihovně, kterou používáte. Některé nástroje mohou mít omezení velikosti nebo složitosti vstupního dokumentu. Je důležité vybrat nástroj, který zvládne požadavky vašeho úkolu převodu.

#### Mohu zachovat formátování a rozvržení původního dokumentu?

Ano, pomocí Aspose.Words můžete během procesu převodu zachovat formátování a rozvržení původního dokumentu. Například Aspose.Words for .NET poskytuje komplexní podporu pro údržbu formátování, stylů a dalších prvků souboru DOCX v převedeném dokumentu RTF.

#### Je Aspose spolehlivým nástrojem pro konverzi DOCX do RTF?

Ano, Aspose.Words for .NET je vysoce spolehlivý nástroj pro konverzi DOCX do RTF. Je široce používán vývojáři a podniky po celém světě pro své robustní funkce a vynikající výkon. Knihovna nabízí rozsáhlou dokumentaci, pravidelné aktualizace a vyhrazenou technickou podporu, což z ní dělá důvěryhodnou volbu pro úlohy převodu dokumentů.