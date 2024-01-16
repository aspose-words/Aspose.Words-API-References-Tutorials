---
title: Nastavte značku zvýraznění písma
linktitle: Nastavte značku zvýraznění písma
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak nastavit styl zvýraznění písma v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fonts/set-font-emphasis-mark/
---

V tomto tutoriálu vám ukážeme, jak nastavit styl zvýraznění písma v dokumentu aplikace Word pomocí Aspose.Words for .NET. Zvýraznění písma se používá ke zvýraznění určitých slov nebo frází v textu.

## Předpoklady
Než začnete, ujistěte se, že máte následující položky:
- Pracovní znalost programovacího jazyka C#
- Knihovna Aspose.Words pro .NET nainstalovaná ve vašem projektu

## Krok 1: Definujte adresář dokumentů
 Začněte nastavením cesty k adresáři na umístění vašeho dokumentu aplikace Word. Nahradit`"YOUR DOCUMENT DIRECTORY"` v kódu s příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvořte a přizpůsobte dokument
 Vytvořte instanci souboru`Document` třída a přidružená`DocumentBuilder` k vytvoření obsahu dokumentu. Použijte`Font.EmphasisMark` vlastnost, na kterou chcete nastavit styl zvýraznění písma`EmphasisMark.UnderSolidCircle` . Poté použijte`Write` a`Writeln` metody`DocumentBuilder` pro přidání textu se zadaným zvýrazněním písma.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## Krok 3: Uložte dokument
 Uložte dokument pomocí`Save` metoda`Document` s příslušnou cestou a názvem souboru.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Ukázkový zdrojový kód pro Set Font Emphas Mark pomocí Aspose.Words for .NET 

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Závěr
tomto kurzu jste se naučili, jak nastavit styl zvýraznění písma v dokumentu aplikace Word pomocí Aspose.Words for .NET. Experimentujte s různými styly důrazu a použijte tuto funkci ke zvýraznění slov nebo frází v dokumentech.

### FAQ

#### Otázka: Jak mohu přidat akcenty do konkrétního písma v dokumentu aplikace Word pomocí Aspose.Words?

A: Chcete-li přidat akcenty do konkrétního písma v dokumentu aplikace Word pomocí Aspose.Words, můžete použít API k navigaci na požadované písmo a použití příslušných akcentů. Tím se do textu s vybraným písmem přidají akcenty.

#### Otázka: Je možné pomocí Aspose.Words změnit styl diakritických znamének v dokumentu aplikace Word?

Odpověď: Ano, pomocí Aspose.Words můžete změnit styl diakritických znamének v dokumentu aplikace Word. Rozhraní API umožňuje upravit vlastnosti stylu, jako je barva, velikost, typ čáry atd., a přizpůsobit tak vzhled akcentů.

#### Otázka: Jak mohu odstranit všechna diakritická znaménka z dokumentu aplikace Word pomocí Aspose.Words?

Odpověď: Chcete-li odstranit všechna diakritická znaménka z dokumentu aplikace Word pomocí Aspose.Words, můžete použít API k procházení dokumentu, zjištění existujících akcentů a jejich odstranění pomocí vhodných metod. Tím se z dokumentu odstraní všechny značky důrazu.

#### Otázka: Mohu přidat diakritická znaménka do určité části textu v dokumentu aplikace Word?

Odpověď: Ano, pomocí Aspose.Words můžete do určité části textu v dokumentu aplikace Word přidat diakritická znaménka. Pomocí rozhraní API můžete vybrat požadovaný rozsah textu a do této části textu přidat vhodné značky zvýraznění.

#### Otázka: Mohou být akcenty přizpůsobeny mým potřebám?

Odpověď: Ano, akcenty lze upravit podle vašich potřeb pomocí Aspose.Words. Vlastnosti stylu akcentních značek, jako je barva, velikost, typ čáry a další, můžete upravit tak, aby odpovídaly vašim předvolbám formátování.