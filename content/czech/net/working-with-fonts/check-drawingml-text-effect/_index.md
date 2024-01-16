---
title: Zaškrtněte Textový efekt DrawingML
linktitle: Zaškrtněte Textový efekt DrawingML
second_title: Aspose.Words API pro zpracování dokumentů
description: V tomto kurzu se dozvíte, jak zkontrolovat textové efekty DrawingML v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fonts/check-drawingml-text-effect/
---

tomto tutoriálu vás provedeme tím, jak zkontrolovat textové efekty DrawingML v dokumentu aplikace Word pomocí knihovny Aspose.Words pro .NET. Zaškrtnutím textových efektů DrawingML můžete určit, zda je na část textu aplikován konkrétní efekt. Provedeme vás krok za krokem, abychom vám pomohli pochopit a implementovat kód ve vašem projektu .NET.

## Předpoklady
Než začnete, ujistěte se, že máte následující položky:
- Pracovní znalost programovacího jazyka C#
- Knihovna Aspose.Words pro .NET nainstalovaná ve vašem projektu
- Dokument aplikace Word obsahující textové efekty DrawingML

## Krok 1: Definujte adresář dokumentů
 Nejprve musíte nastavit cestu k adresáři na umístění vašeho dokumentu aplikace Word. Nahradit`"YOUR DOCUMENT DIRECTORY"` v kódu s příslušnou cestou.

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vložte dokument a zkontrolujte textové efekty
Dále načteme dokument Word a zpřístupníme kolekci běhů (sekvencí znaků) v prvním odstavci těla dokumentu. Dále zkontrolujeme, zda jsou na písmo prvního spuštění aplikovány nějaké specifické textové efekty DrawingML.

```csharp
// Vložte dokument
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Zkontrolujte textové efekty DrawingML
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### Ukázkový zdrojový kód pro Check DMLText Effect pomocí Aspose.Words pro .NET 

```csharp

// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Na jedno spuštění může být použito několik textových efektů Dml.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## Závěr
tomto tutoriálu jsme viděli, jak zkontrolovat textové efekty DrawingML v dokumentu aplikace Word pomocí Aspose.Words for .NET. Zaškrtnutí textových efektů DrawingML vám umožňuje identifikovat části textu, které mají aplikované specifické efekty. Neváhejte použít tuto funkci k manipulaci a analýze textových efektů v dokumentech aplikace Word.

### FAQ

#### Otázka: Jak mohu získat přístup k textovým efektům DrawingML v dokumentu aplikace Word pomocí Aspose.Words?

Odpověď: S Aspose.Words můžete přistupovat k textovým efektům DrawingML v dokumentu aplikace Word pomocí poskytnutého rozhraní API. Můžete procházet textové prvky a kontrolovat specifické vlastnosti textových efektů, jako je barva, velikost atd.

#### Otázka: Jaké typy textových efektů DrawingML se běžně používají v dokumentech aplikace Word?

Odpověď: Mezi běžně používané typy textových efektů DrawingML v dokumentech aplikace Word patří stíny, odrazy, záře, přechody atd. Tyto efekty lze použít ke zlepšení vzhledu a formátování textu.

#### Otázka: Jak mohu zkontrolovat barvu textového efektu DrawingML v dokumentu aplikace Word?

Odpověď: Chcete-li zkontrolovat barvu textového efektu DrawingML v dokumentu aplikace Word, můžete použít metody poskytované Aspose.Words pro přístup k barevným vlastnostem textového efektu. Tímto způsobem můžete získat barvu použitou pro konkrétní textový efekt.

#### Otázka: Je možné zkontrolovat textové efekty v dokumentech aplikace Word obsahujících více oddílů?

Odpověď: Ano, Aspose.Words umožňuje kontrolu textových efektů v dokumentech aplikace Word obsahujících více oddílů. Můžete procházet každou částí dokumentu a přistupovat k textovým efektům pro každou část zvlášť.

#### Otázka: Jak mohu zkontrolovat neprůhlednost textového efektu DrawingML v dokumentu aplikace Word?

Odpověď: Chcete-li zkontrolovat neprůhlednost textového efektu DrawingML v dokumentu aplikace Word, můžete použít metody poskytované Aspose.Words pro přístup k vlastnostem neprůhlednosti textového efektu. To vám umožní získat hodnotu krytí aplikovanou na konkrétní textový efekt.