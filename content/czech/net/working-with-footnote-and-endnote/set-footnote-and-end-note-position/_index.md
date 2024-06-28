---
title: Nastavit pozici poznámky pod čarou a konec poznámky
linktitle: Nastavit pozici poznámky pod čarou a konec poznámky
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak nastavit polohu poznámek pod čarou a vysvětlivky v dokumentech aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

V tomto podrobném tutoriálu vás provedeme tím, jak používat Aspose.Words pro .NET k nastavení pozice poznámek pod čarou a vysvětlivky v dokumentu aplikace Word. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat do vašich vlastních projektů.

 Chcete-li začít, ujistěte se, že máte Aspose.Words for .NET nainstalovaný a nastavený ve svém vývojovém prostředí. Pokud jste tak neučinili, stáhněte si a nainstalujte knihovnu z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Inicializace objektu dokumentu

 Nejprve inicializujte`Document` objekt poskytnutím cesty ke zdrojovému dokumentu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Krok 2: Nastavení pozice poznámky pod čarou a koncové poznámky

 Dále přejděte na`FootnoteOptions` a`EndnoteOptions`vlastnosti dokumentu pro nastavení polohy poznámek pod čarou a vysvětlivky. V tomto příkladu nastavíme pozici poznámek pod čarou tak, aby byly pod textem, a pozici vysvětlivek na konci oddílu:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Krok 3: Uložení dokumentu

Nakonec upravený dokument uložte:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

A je to! Úspěšně jste nastavili pozici poznámek pod čarou a vysvětlivky v dokumentu aplikace Word pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro nastavení pozice poznámky pod čarou a koncové poznámky pomocí Aspose.Words pro .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Neváhejte použít tento kód ve svých vlastních projektech a upravit jej podle svých konkrétních požadavků.

### FAQ

#### Otázka: Jak mohu umístit poznámky pod čarou a vysvětlivky v Aspose.Words?

 A: Chcete-li umístit poznámky pod čarou a vysvětlivky v Aspose.Words, musíte použít`FootnoteOptions` třída a`Position` vlastnictví. Tuto vlastnost můžete nastavit na libovolnou hodnotu, jako je např`BottomOfPage` (ve spodní části stránky) popř`EndOfSection` (na konci sekce).

#### Otázka: Je možné upravit umístění poznámek pod čarou a vysvětlivky pro každou stránku nebo část dokumentu?

Odpověď: Ano, je možné upravit umístění poznámek pod čarou a vysvětlivky pro každou stránku nebo sekci dokumentu. K definování konkrétních pozic pro poznámky pod čarou a vysvětlivky můžete použít metody manipulace části Aspose.Words a stránky.

#### Otázka: Jak odstraním poznámky pod čarou nebo vysvětlivky z dokumentu?

 A: Chcete-li odstranit poznámky pod čarou nebo vysvětlivky z dokumentu v Aspose.Words, můžete použít vhodné metody, jako např.`RemoveAllFootnotes` odstranit všechny poznámky pod čarou popř`RemoveAllEndnotes` odstranit všechny vysvětlivky. Po provedení těchto operací nezapomeňte dokument uložit.

#### Otázka: Mohou být poznámky pod čarou a vysvětlivky umístěny mimo okraje stránky?

Ne, ve výchozím nastavení nelze poznámky pod čarou a vysvětlivky umístit mimo okraje stránky v Aspose.Words. Můžete však upravit okraje dokumentu, aby bylo v případě potřeby více místa pro poznámky pod čarou a vysvětlivky.

#### Otázka: Lze poznámky pod čarou a vysvětlivky přizpůsobit konkrétním písmem nebo styly formátování?

Odpověď: Ano, poznámky pod čarou a vysvětlivky si můžete přizpůsobit konkrétním písmem nebo styly formátování v Aspose.Words. Pomocí dostupných metod a vlastností můžete použít styly písma, barvy, velikosti písma atd. poznámky pod čarou a vysvětlivky.