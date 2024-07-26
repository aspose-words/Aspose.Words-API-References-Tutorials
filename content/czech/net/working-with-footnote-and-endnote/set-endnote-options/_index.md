---
title: Nastavte možnosti Endnote
linktitle: Nastavte možnosti Endnote
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak nastavit možnosti koncových poznámek v dokumentech aplikace Word pomocí Aspose.Words for .NET. Výukový program krok za krokem s ukázkovým zdrojovým kódem.
type: docs
weight: 10
url: /cs/net/working-with-footnote-and-endnote/set-endnote-options/
---

tomto podrobném tutoriálu vás provedeme tím, jak používat Aspose.Words pro .NET k nastavení možností koncových poznámek v dokumentu aplikace Word. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat do vašich vlastních projektů.

 Chcete-li začít, ujistěte se, že máte Aspose.Words for .NET nainstalovaný a nastavený ve svém vývojovém prostředí. Pokud jste tak neučinili, stáhněte si a nainstalujte knihovnu z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Inicializace objektu dokumentu

 Nejprve inicializujte`Document` objekt poskytnutím cesty ke zdrojovému dokumentu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Krok 2: Inicializace objektu DocumentBuilder

 Dále inicializujte`DocumentBuilder` objekt pro provádění operací s dokumentem:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Přidání textu a závěrečné poznámky

 Použijte`Write` metoda`DocumentBuilder` objekt pro přidání textu do dokumentu a`InsertFootnote` metoda pro vložení koncové poznámky:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Krok 4: Nastavení možností Endnote

 Přístup k`EndnoteOptions`vlastnost dokumentu upravit možnosti vysvětlivky. V tomto příkladu jsme nastavili pravidlo restartu tak, aby se restartovalo na každé stránce a na pozici na konec sekce:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Krok 5: Uložení dokumentu

Nakonec upravený dokument uložte:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

A je to! Úspěšně jste nastavili možnosti koncových poznámek v dokumentu aplikace Word pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro Set Endnote Options pomocí Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Neváhejte použít tento kód ve svých vlastních projektech a upravit jej podle svých konkrétních požadavků.

### FAQ

#### Otázka: Jak mohu stylovat vysvětlivky v Aspose.Words?

 A: Chcete-li stylovat vysvětlivky v Aspose.Words, můžete použít`EndnoteOptions` třída a`SeparatorNoteTextStyle` vlastnictví. Pomocí této vlastnosti můžete určit styl písma, velikost, barvu atd. pro vysvětlivky.

#### Otázka: Je možné přizpůsobit číslování vysvětlivek v dokumentu?

 Odpověď: Ano, je možné upravit číslování vysvětlivek v dokumentu. Můžete použít`RestartRule`a`NumberStyle` vlastnosti`EndnoteOptions` třídy k definování specifických pravidel restartu a stylů číslování.

#### Otázka: Jak mohu umístit vysvětlivky v dokumentu?

Odpověď: Chcete-li umístit vysvětlivky do dokumentu, můžete použít`Position` majetek z`EndnoteOptions` třída. Můžete určit, zda mají být vysvětlivky umístěny na konec každé stránky, na konec každé sekce nebo na konec dokumentu.

#### Otázka: Mohu přizpůsobit formát číslování vysvětlivky?

 Odpověď: Ano, formát číslování koncových poznámek si můžete přizpůsobit v Aspose.Words. Použijte`NumberFormat` majetek z`EndnoteOptions` třídy pro nastavení požadovaného formátu, jako jsou arabské číslice, římské číslice, písmena atd.

#### Otázka: Je možné pokračovat v číslování vysvětlivek mezi sekcemi dokumentu?

 Odpověď: Ano, je možné pokračovat v číslování vysvětlivek mezi sekcemi dokumentu. Použijte`RestartRule` majetek z`EndnoteOptions` třídu a nastavte ji na`RestartContinuous` aby číslování pokračovalo mezi sekcemi.