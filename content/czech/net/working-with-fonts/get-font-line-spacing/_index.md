---
title: Získejte řádkování písma
linktitle: Získejte řádkování písma
second_title: Aspose.Words API pro zpracování dokumentů
description: V tomto kurzu se dozvíte, jak získat řádkování písma v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fonts/get-font-line-spacing/
---
tomto tutoriálu vám řekneme, jak získat řádkování písma v dokumentu aplikace Word pomocí knihovny Aspose.Words pro .NET. Řádkování písma definuje vertikální mezeru mezi řádky textu. Provedeme vás krok za krokem, abychom vám pomohli pochopit a implementovat kód ve vašem projektu .NET.

## Předpoklady
Než začnete, ujistěte se, že máte následující položky:
- Pracovní znalost programovacího jazyka C#
- Knihovna Aspose.Words pro .NET nainstalovaná ve vašem projektu

## Krok 1: Vytvořte nový dokument a generátor dokumentů
 Nejprve vytvoříme nový dokument vytvořením instance`Document` třídy a tvůrce dokumentů vytvořením instance`DocumentBuilder` třída.

```csharp
// Vytvořte nový dokument
Document doc = new Document();

//Vytvořte generátor dokumentů
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Nakonfigurujte písmo
 Dále nakonfigurujeme písmo nastavením`Name` vlastnost generátoru dokumentů.

```csharp
// Nakonfigurujte písmo
builder.Font.Name = "Calibri";
```

## Krok 3: Přidejte do dokumentu text
Nyní použijeme generátor dokumentů k přidání formátovaného textu do dokumentu.

```csharp
// Přidejte text do dokumentu
builder. Writen("qText");
```

## Krok 4: Získejte řádkování písma
 Nyní přistoupíme k`Font` objekt prvního odstavce dokumentu a získat hodnotu`LineSpacing` vlastnictví.

```csharp
// Získejte řádkování písma
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Ukázka zdrojového kódu pro Get Font Line Spacing pomocí Aspose.Words for .NET 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Závěr
tomto tutoriálu jsme viděli, jak získat řádkování písma v dokumentu aplikace Word pomocí Aspose.Words pro .NET. Řádkování písma je důležité pro ovládání vertikálních mezer mezi řádky textu. Neváhejte použít tuto funkci k přizpůsobení vzhledu textu v dokumentech.

### FAQ

#### Otázka: Jak mohu změnit řádkování konkrétního textu v dokumentu aplikace Word?

Odpověď: Pomocí Aspose.Words můžete snadno změnit řádkování konkrétního textu v dokumentu aplikace Word. Pomocí rozhraní API vyberte požadovaný text a upravte mezery mezi řádky zadáním příslušné hodnoty.

#### Otázka: Je možné použít přesné mezery mezi řádky v dokumentu aplikace Word?

Odpověď: Ano, Aspose.Words vám umožňuje použít přesné mezery mezi řádky v dokumentu aplikace Word. Pomocí rozhraní API můžete zadat přesnou hodnotu pro řádkování.

#### Otázka: Jak mohu upravit řádkování pro celý dokument aplikace Word?

Odpověď: Pomocí Aspose.Words můžete snadno upravit řádkování pro celý dokument aplikace Word. Pomocí metod poskytovaných rozhraním API zadejte požadované řádkování pro celý dokument.

#### Otázka: Podporuje Aspose.Words více řádků?

Odpověď: Ano, Aspose.Words podporuje více řádkování v dokumentech aplikace Word. Pro řádky textu můžete nastavit vícenásobné mezery, například 1,5násobek nebo 2násobek normálního řádkování.

#### Otázka: Jak se mohu vyhnout problémům s překrýváním řádků při úpravě řádkování?

A: Abyste se vyhnuli problémům s překrýváním řádků při nastavování mezer mezi řádky, nezapomeňte zvolit vhodné hodnoty mezer. Otestujte také konečné vykreslení dokumentu, abyste zajistili, že text zůstane čitelný a dobře naformátovaný.