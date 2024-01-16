---
title: Zadejte národní prostředí na úrovni pole
linktitle: Zadejte národní prostředí na úrovni pole
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak určit lokalizaci na úrovni pole v dokumentech aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fields/specify-locale-at-field-level/
---

Zde je podrobný průvodce, který vysvětluje následující zdrojový kód C#, který umožňuje specifikovat lokalizaci na úrovni pole pomocí funkce Aspose.Words for .NET. Před použitím tohoto kódu se ujistěte, že jste do projektu zahrnuli knihovnu Aspose.Words.

## Krok 1: Nastavte cestu k adresáři dokumentu

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Ujistěte se, že jste zadali správnou cestu k adresáři dokumentů, kam se upravený dokument uloží.

## Krok 2: Vytvořte generátor dokumentů

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Zde vytváříme instanci`DocumentBuilder` třída, která nám umožní přidávat pole do dokumentu.

## Krok 3: Vložte datové pole s konkrétním umístěním

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 Pro vložení pole typu používáme generátor dokumentů`FieldType.FieldDate` do dokumentu. Nastavením`LocaleId`majetek do`1049`, specifikujeme pro toto pole ruskou lokalizaci.

## Krok 4: Uložte upravený dokument

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Nakonec upravený dokument uložíme se zadaným umístěním do určeného souboru.

### Ukázkový zdrojový kód pro určení lokalizace na úrovni pole pomocí Aspose.Words pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Toto byl příklad zdrojového kódu pro specifikaci lokalizace na úrovni pole v dokumentu pomocí Aspose.Words for .NET. Tento kód můžete použít k vložení datových polí s konkrétními umístěními do dokumentů aplikace Word.

### FAQ

#### Otázka: Jak mohu určit národní prostředí na úrovni pole v Aspose.Words pro .NET?

 Odpověď: Chcete-li zadat národní prostředí na úrovni pole v Aspose.Words pro .NET, můžete použít`FieldOptions` třída a její`FieldLocale` vlastnost pro nastavení požadovaného národního prostředí. Můžete například použít`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` k určení francouzského (francouzského) národního prostředí.

#### Otázka: Je možné pro každé pole v Aspose.Words pro .NET zadat jiné národní prostředí?

 Odpověď: Ano, pro každé pole v Aspose.Words for .NET je možné zadat jiné národní prostředí. Můžete použít`FieldOptions.FieldLocale` vlastnost před vytvořením nebo aktualizací konkrétního pole, abyste mu přiřadili jiné národní prostředí.

#### Otázka: Jak mohu získat aktuálně používané národní prostředí pro pole v Aspose.Words pro .NET?

 A: Chcete-li získat aktuálně používané národní prostředí pro pole v Aspose.Words pro .NET, můžete použít`Field.LocaleId` vlastnictví. To vám umožní získat identifikátor národního prostředí spojený s polem.