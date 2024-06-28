---
title: Změnit pole Aktualizovat zdroj kultury
linktitle: Změnit pole Aktualizovat zdroj kultury
second_title: Aspose.Words API pro zpracování dokumentů
description: Change Field Update Culture Source, Podrobný průvodce úpravou zdroje kultury v Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fields/change-field-update-culture-source/
---

tomto tutoriálu vás provedeme procesem změny zdroje kultury aktualizace pole v dokumentech aplikace Word pomocí Aspose.Words for .NET. Úpravou zdroje jazykové verze můžete řídit formátování data během operací aktualizace polí a hromadné korespondence. Poskytneme vám potřebný zdrojový kód C# a pokyny krok za krokem, jak toho dosáhnout.

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Knihovna Aspose.Words for .NET nainstalovaná ve vašem systému.

## Krok 1: Vytvořte dokument a DocumentBuilder
Chcete-li začít, vytvořte instanci třídy Document a objekt DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Vložte obsah se specifickým národním prostředím
Dále nastavte národní prostředí na němčinu a vložte pole s formátováním data:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

Ve výše uvedeném kódu nastavíme národní prostředí písma na němčinu (ID národního prostředí 1031) a vložíme dvě pole se specifickým formátováním data.

## Krok 3: Změňte zdroj kultury aktualizace pole
Chcete-li změnit zdroj kultury aktualizace pole, použijte třídu FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

V tomto příkladu jsme nastavili kulturu použitou během aktualizace pole tak, aby byla vybrána z kultury používané polem.

## Krok 4: Proveďte hromadnou korespondenci
Proveďte operaci hromadné korespondence a zadejte hodnotu data pro pole "Datum2":

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

V tomto fragmentu kódu provedeme operaci hromadné korespondence a do pole „Datum2“ zadáme hodnotu DateTime.

## Krok 5: Uložte dokument
Uložte upravený dokument do souboru pomocí metody Save třídy Document:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Příklad zdrojového kódu pro změnu zdroje kultury aktualizace pole pomocí Aspose.Words for .NET
Zde je úplný zdrojový kód pro změnu zdroje kultury aktualizace pole v dokumentech aplikace Word pomocí Aspose.Words pro .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak změnit zdroj kultury aktualizace pole v dokumentech aplikace Word pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete nyní ovládat kulturu používanou pro formátování data během operací aktualizace polí a hromadné korespondence. Upravte zdroj kultury podle svých požadavků, abyste zajistili přesné a konzistentní datum.

### FAQ

#### Otázka: Jak mohu změnit zdroj kultury aktualizace pole v Aspose.Words pro .NET?

 A: Chcete-li změnit zdroj kultury aktualizace pole v Aspose.Words pro .NET, můžete použít`Document.FieldOptions.CultureSource` vlastnost a nastavte její hodnotu na`FieldCultureSource.FieldCode` nebo`FieldCultureSource.CurrentThread` . Můžete například použít`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` použít kulturu definovanou v kódu pole.

#### Otázka: Jak mohu určit konkrétní kulturu pro aktualizaci polí v Aspose.Words pro .NET?

 A: Chcete-li určit konkrétní kulturu pro aktualizaci polí v Aspose.Words pro .NET, můžete použít`Document.FieldOptions.FieldUpdateCultureInfo` vlastnost a nastavte`CultureInfo` objekt odpovídající požadované kultuře. Můžete například použít`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` specifikovat francouzskou (francouzskou) kulturu.

#### Otázka: Je možné zakázat automatickou aktualizaci polí v Aspose.Words pro .NET?

 Odpověď: Ano, v Aspose.Words pro .NET je možné zakázat automatickou aktualizaci polí. Můžete použít`Document.FieldOptions.UpdateFields` vlastnost a nastavte ji na`false` abyste zabránili automatické aktualizaci polí. To vám umožňuje ručně ovládat aktualizaci polí podle potřeby.

#### Otázka: Jak mohu ručně aktualizovat pole dokumentu v Aspose.Words pro .NET?

 A: Chcete-li ručně aktualizovat pole v dokumentu v Aspose.Words pro .NET, můžete použít`Field.Update` metoda pro každý obor zvlášť. Můžete například použít`field.Update()` pro aktualizaci konkrétního pole.