---
title: Seznam restartů v každé sekci
linktitle: Seznam restartů v každé sekci
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak obnovit číslovaný seznam pro každou sekci v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-list/restart-list-at-each-section/
---

tomto tutoriálu krok za krokem vám ukážeme, jak pomocí Aspose.Words for .NET resetovat číslovaný seznam pro každou sekci v dokumentu aplikace Word. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat do vašich vlastních projektů.

 Chcete-li začít, ujistěte se, že máte Aspose.Words for .NET nainstalovaný a nakonfigurovaný ve svém vývojovém prostředí. Pokud jste tak ještě neučinili, stáhněte si a nainstalujte knihovnu z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Vytvoření dokumentu a seznamu

Nejprve vytvořte nový dokument a přidejte výchozí číslovaný seznam:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## Krok 2: Přidání položek do seznamu

 Poté použijte a`DocumentBuilder` pro přidání položek do seznamu. K přidání více položek do seznamu můžete použít smyčku:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

V tomto příkladu vkládáme konec oddílu za 15. položku seznamu pro ilustraci přečíslování.

## Krok 3: Uložte upravený dokument

Nakonec upravený dokument uložte:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

Tak ! Úspěšně jste resetovali číslovaný seznam pro každou sekci v dokumentu aplikace Word pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro resetování seznamu v každé sekci

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

Neváhejte použít tento kód ve svých vlastních projektech a upravit jej tak, aby vyhovoval vašim konkrétním potřebám.

### FAQ

#### Otázka: Jak mohu restartovat seznam v každé sekci v Aspose.Words?

 A: Chcete-li restartovat seznam v každé sekci v Aspose.Words, musíte vytvořit instanci souboru`List`třídy a přiřadit k ní číslovaný seznam. Poté můžete použít`List.IsRestartAtEachSection` vlastnost, která určuje, že číslování by mělo být restartováno v každé sekci. Tento seznam můžete přidružit k jednomu nebo více oddílům dokumentu, aby se číslování u každého oddílu správně restartovalo.

#### Otázka: Mohu upravit formát číslování seznamů v Aspose.Words?

 Odpověď: Ano, můžete upravit formát číslování seznamů v Aspose.Words. The`List` třída k tomu nabízí několik vlastností, jako např`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`, atd. Pomocí těchto vlastností můžete nastavit typ seznamu (číslovaný, s odrážkami atd.), formát číslování (arabské číslice, římské číslice, písmena atd.) a další možnosti formátování číslování.

#### Otázka: Je možné přidat další úrovně do číslovaného seznamu v Aspose.Words?

 Odpověď: Ano, je možné přidat další úrovně do číslovaného seznamu v Aspose.Words. The`ListLevel`class umožňuje nastavit vlastnosti formátování pro každou úroveň seznamu. Můžete nastavit možnosti, jako je předpona, přípona, zarovnání, odsazení atd. To vám umožní vytvářet seznamy s více úrovněmi hierarchie.