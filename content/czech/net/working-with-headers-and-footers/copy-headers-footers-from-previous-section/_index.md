---
title: Zkopírujte záhlaví zápatí z předchozí sekce
linktitle: Zkopírujte záhlaví zápatí z předchozí sekce
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se kopírovat záhlaví a zápatí z předchozí části v dokumentech aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

V tomto podrobném tutoriálu vás provedeme kopírováním záhlaví a zápatí z předchozí části do dokumentu aplikace Word pomocí Aspose.Words for .NET. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat do vašich vlastních projektů.

 Chcete-li začít, ujistěte se, že máte Aspose.Words for .NET nainstalovaný a nastavený ve svém vývojovém prostředí. Pokud jste tak neučinili, stáhněte si a nainstalujte knihovnu z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Přístup k předchozí části

 Nejprve načtěte předchozí sekci přístupem k`PreviousSibling` vlastnost aktuální sekce:

```csharp
Section previousSection = (Section)section.PreviousSibling;
```

## Krok 2: Kontrola předchozí sekce

Dále zkontrolujte, zda existuje předchozí sekce. Pokud neexistuje žádná předchozí sekce, jednoduše se vrátíme:

```csharp
if (previousSection == null)
    return;
```

## Krok 3: Vymazání a kopírování záhlaví a zápatí

Chcete-li zkopírovat záhlaví a zápatí z předchozí sekce do aktuální sekce, vymažeme stávající záhlaví a zápatí v aktuální sekci a poté iterujeme záhlaví a zápatí předchozí sekce, abychom do aktuální sekce přidali klonované kopie:

```csharp
section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));
```

## Krok 4: Uložení dokumentu

Nakonec upravený dokument uložte:

```csharp
doc.Save("OutputDocument.docx");
```

A je to! Úspěšně jste zkopírovali záhlaví a zápatí z předchozího oddílu do aktuálního oddílu v dokumentu aplikace Word pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro Kopírovat záhlaví zápatí z předchozí části pomocí Aspose.Words pro .NET

```csharp
Section previousSection = (Section)section.PreviousSibling;

if (previousSection == null)
    return;

section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));

doc.Save("OutputDocument.docx");
```

Neváhejte použít tento kód ve svých vlastních projektech a upravit jej podle svých konkrétních požadavků.

### FAQ

#### Otázka: Jak mohu zkopírovat záhlaví a zápatí z předchozí sekce do Aspose.Words?

 A: Chcete-li zkopírovat záhlaví a zápatí z předchozí sekce do Aspose.Words, můžete použít`CopyHeadersFootersFromPreviousSection()` metoda na proudu`Section`objekt. Tím se zkopírují záhlaví a zápatí z předchozí sekce do aktuální sekce.

#### Otázka: Je možné zkopírovat pouze záhlaví nebo zápatí z předchozí sekce v Aspose.Words?

 Odpověď: Ano, je možné zkopírovat pouze záhlaví nebo zápatí z předchozí sekce v Aspose.Words. K tomu můžete použít`CopyHeaderFromPreviousSection()` a`CopyFooterFromPreviousSection()` metody na proud`Section` objekt, který konkrétně zkopíruje záhlaví nebo zápatí z předchozí sekce do aktuální sekce.

#### Otázka: Nahrazuje kopírování záhlaví a zápatí z předchozí sekce stávající záhlaví a zápatí v aktuální sekci?

Odpověď: Ano, zkopírováním záhlaví a zápatí z předchozí sekce se nahradí stávající záhlaví a zápatí v aktuální sekci. Pokud chcete zachovat stávající záhlaví a zápatí a přidat je ke zkopírovaným záhlavím a zápatím, budete muset provést další operaci ke sloučení obsahu.

#### Otázka: Jak mohu zkontrolovat, zda má sekce záhlaví nebo zápatí z předchozí sekce v Aspose.Words?

A: Chcete-li zkontrolovat, zda má sekce záhlaví nebo zápatí z předchozí sekce v Aspose.Words, můžete použít`HasHeader` a`HasFooter` vlastnosti na`Section` objekt k určení, zda je přítomno záhlaví nebo zápatí záhlaví. Li`HasHeader` nebo`HasFooter` se vrací`false`, znamená to, že v této sekci není žádné záhlaví ani zápatí z předchozí sekce.