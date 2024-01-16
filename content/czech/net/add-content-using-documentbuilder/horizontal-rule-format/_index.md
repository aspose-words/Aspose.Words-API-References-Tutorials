---
title: Horizontální Pravidlo Formát V dokumentu Word
linktitle: Horizontální Pravidlo Formát V dokumentu Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se formátovat horizontální pravidla v dokumentech aplikace Word pomocí Aspose.Words for .NET. Průvodce krok za krokem.
type: docs
weight: 10
url: /cs/net/add-content-using-documentbuilder/horizontal-rule-format/
---
tomto komplexním příkladu se naučíte, jak formátovat vodorovné pravítko v dokumentu aplikace Word pomocí Aspose.Words for .NET. Provedeme vás celým procesem a poskytneme vám potřebné úryvky kódu C#. Na konci této příručky budete moci přizpůsobit zarovnání, šířku, výšku, barvu a další vlastnosti vodorovného pravítka.

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Knihovna Aspose.Words for .NET nainstalovaná ve vašem systému.

## Krok 1: Vytvořte DocumentBuilder a vložte vodorovné pravidlo
Chcete-li začít, vytvořte objekt DocumentBuilder a pomocí metody InsertHorizontalRule vložte vodorovné pravidlo:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## Krok 2: Otevřete formát horizontálního pravidla
Dále otevřete vlastnost HorizontalRuleFormat objektu Shape a načtěte možnosti formátování:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## Krok 3: Upravte možnosti formátování
Nyní můžete přizpůsobit různé možnosti formátování pro vodorovné pravítko. Můžete například upravit zarovnání, šířku, výšku, barvu a stínování:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Krok 4: Uložte dokument
Po naformátování vodorovného pravítka uložte dokument do souboru pomocí metody Uložit objektu dokumentu:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Příklad zdrojového kódu pro formát horizontálních pravidel pomocí Aspose.Words pro .NET
Zde je úplný zdrojový kód pro formátování vodorovného pravidla pomocí Aspose.Words pro .NET:

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

Nezapomeňte upravit kód podle svých specifických požadavků a podle potřeby jej vylepšit o další funkce.

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak formátovat vodorovné pravítko v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu si nyní můžete přizpůsobit vzhled vodorovných pravidel a zlepšit tak vizuální rozvržení dokumentu.

Experimentujte s různými možnostmi formátování, abyste dosáhli požadovaného stylu a efektu pro vaše horizontální pravidla.

### Časté dotazy pro formát horizontálních pravidel v dokumentu aplikace Word

#### Otázka: Mohu na vodorovné pravítko použít různé barvy?

A: Rozhodně! Pomocí Aspose.Words for .NET můžete snadno přizpůsobit barvu vodorovného pravítka nastavením vlastnosti Barva na požadovanou hodnotu barvy. To vám umožní sladit vodorovné pravítko s celkovým návrhem dokumentu.

#### Otázka: Je možné upravit šířku a výšku vodorovného pravítka?

Odpověď: Ano, máte plnou kontrolu nad šířkou a výškou vodorovného pravítka. Úpravou vlastností WidthPercent a Height můžete dosáhnout požadovaných rozměrů pro vodorovné pravítko.

#### Otázka: Mohu změnit zarovnání vodorovného pravítka v dokumentu?

A: Určitě! Aspose.Words for .NET umožňuje určit zarovnání vodorovného pravidla pomocí vlastnosti Alignment. Můžete si vybrat z různých možností, jako je Center, Left, Right a Justified.

#### Otázka: Mohu na vodorovné pravítko použít stínování nebo barvu pozadí?

Odpověď: Ano, k vodorovnému pravidlu můžete přidat stínování nebo barvu pozadí. Ve výchozím nastavení je vlastnost NoShade nastavena na hodnotu true, ale můžete ji nastavit na hodnotu false a definovat stínování pomocí příslušných metod.

#### Otázka: Mohu vložit více horizontálních pravidel do jednoho dokumentu?

A: Rozhodně! Pomocí Aspose.Words for .NET můžete do dokumentu aplikace Word vložit více horizontálních pravidel. Jednoduše opakujte kroky ve výukovém programu podle potřeby a přidejte tolik horizontálních pravidel, kolik potřebujete.