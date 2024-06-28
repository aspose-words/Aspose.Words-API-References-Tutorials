---
title: Dělit slova jazyků
linktitle: Dělit slova jazyků
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se dělit slova v různých jazycích v dokumentech aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-hyphenation/hyphenate-words-of-languages/
---

V tomto podrobném tutoriálu vás provedeme dělením slov v různých jazycích v dokumentech aplikace Word pomocí Aspose.Words for .NET. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat do vašich vlastních projektů.

Chcete-li začít, ujistěte se, že máte Aspose.Words for .NET nainstalovaný a nakonfigurovaný ve svém vývojovém prostředí. Pokud jste tak ještě neučinili, stáhněte si a nainstalujte knihovnu z oficiálních stránek.

## Krok 1: Inicializace objektu dokumentu

 Nejprve inicializujte`Document` objekt zadáním cesty ke zdrojovému dokumentu obsahujícímu text v různých jazycích:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Krok 2: Uložení slovníků dělení slov

Dále uložte slovníky dělení slov pro různé jazyky, které chcete zpracovat. V tomto příkladu registrujeme slovníky pro americkou angličtinu a švýcarskou němčinu:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Ujistěte se, že máte v datovém adresáři příslušné soubory slovníku.

## Krok 3: Zpracování slov dělením slov

Nyní můžete používat funkce dělení slov ke zpracování slov v různých jazycích. Můžete použít různé metody`Document` nebo`DocumentBuilder` v závislosti na vašich konkrétních potřebách.

```csharp
// Příklad: Použití metody dělení slov v DocumentBuilderu
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Krok 4: Uložte dokument

Nakonec upravený dokument uložte:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Tak ! Úspěšně jste zpracovali slova jejich dělením v různých jazycích v dokumentu aplikace Word pomocí Aspose.Words for .NET.

### Ukázka zdrojového kódu pro dělení slov pomocí Aspose.Words pro .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Neváhejte použít tento kód ve svých vlastních projektech a upravit jej tak, aby vyhovoval vašim konkrétním potřebám.

### FAQ

#### Otázka: Jak mohu pomocí Aspose.Words slabikovat slovo v určitém jazyce?

 A: Chcete-li slabikovat slovo v určitém jazyce pomocí Aspose.Words, můžete použít`Hyphenation` třída a`Hyphenate()` metoda. Vytvořte instanci souboru`Hyphenation` třídu specifikující požadovaný jazyk a poté zavolejte`Hyphenate()` metoda předávání slova do slabikovat jako argument. Tím získáte slabiky slova v určeném jazyce.

#### Otázka: Jaké jazykové kódy bych měl použít k určení slabikového jazyka v Aspose.Words?

A: Chcete-li určit jazyk slabikáře v Aspose.Words, musíte použít příslušné kódy jazyků. Můžete například použít „en“ pro angličtinu, „fr“ pro francouzštinu, „es“ pro španělštinu, „de“ pro němčinu atd. Úplný seznam podporovaných jazykových kódů naleznete v dokumentaci Aspose.Words.

#### Otázka: Funguje slabikování pro všechny jazyky v Aspose.Words?

A: Slabikování v Aspose.Words závisí na pravidlech slabikování specifických pro jazyk. Přestože Aspose.Words podporuje širokou škálu jazyků, některé jazyky nemusí být podporovány nebo pro ně nemusí být k dispozici slabika. Podívejte se do dokumentace Aspose.Words a zjistěte, které jazyky jsou podporovány pro slabikování.