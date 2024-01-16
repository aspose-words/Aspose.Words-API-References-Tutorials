---
title: Změnit národní prostředí
linktitle: Změnit národní prostředí
second_title: Aspose.Words API pro zpracování dokumentů
description: Přečtěte si, jak změnit národní prostředí pro formátování data a čísel v dokumentech aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fields/change-locale/
---

tomto tutoriálu vás provedeme procesem změny národního prostředí v dokumentech aplikace Word pomocí Aspose.Words for .NET. Úpravou národního prostředí můžete řídit formátování dat a čísel během operací hromadné korespondence. Poskytneme vám potřebný zdrojový kód C# a pokyny krok za krokem, jak toho dosáhnout.

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

## Krok 2: Vložte pole
Dále vložte slučovací pole do dokumentu pomocí metody InsertField:

```csharp
builder.InsertField("MERGEFIELD Date");
```

Ve výše uvedeném kódu vložíme do dokumentu slučovací pole s názvem "Datum".

## Krok 3: Změňte místní nastavení
Chcete-li změnit národní prostředí pro formátování data a čísla, můžete upravit aktuální jazykovou verzi vlákna. V tomto příkladu nastavíme národní prostředí na němčinu ("de-DE"):

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

Ve výše uvedeném kódu uložíme aktuální jazykovou verzi a poté nastavíme kulturu aktuálního vlákna na němčinu.

## Krok 4: Proveďte hromadnou korespondenci
Proveďte operaci hromadné korespondence a zadejte hodnotu data do pole "Datum":

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

tomto fragmentu kódu provedeme operaci hromadné korespondence a jako hodnotu pole „Datum“ poskytneme aktuální datum.

## Krok 5: Obnovte původní národní prostředí
Po dokončení hromadné korespondence obnovte původní kulturu vlákna:

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

Ve výše uvedeném kódu obnovíme původní kulturu vlákna.

## Krok 6: Uložte dokument
Uložte upravený dokument do souboru pomocí metody Save třídy Document:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### Příklad zdrojového kódu pro změnu národního prostředí pomocí Aspose.Words for .NET
Zde je úplný zdrojový kód pro změnu národního prostředí v dokumentech aplikace Word pomocí Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD Date");

CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");

doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });

Thread.CurrentThread.CurrentCulture = currentCulture;

doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak změnit národní prostředí v dokumentech aplikace Word pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu nyní můžete řídit formátování dat a čísel během operací hromadné korespondence. Upravte národní prostředí podle svých požadavků, abyste zajistili přesné a konzistentní formátování dokumentů.

### FAQ

#### Otázka: Je Aspose.Words kompatibilní s různými verzemi aplikace Microsoft Word?

Odpověď: Ano, Aspose.Words je kompatibilní s různými verzemi aplikace Microsoft Word včetně Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 a Word 2019.

#### Otázka: Podporuje Aspose.Words složité struktury polí?

A: Absolutně! Aspose.Words nabízí rozsáhlou podporu pro složité struktury polí, včetně vnořených polí, výpočtů a podmíněných výrazů. Toto výkonné rozhraní API můžete použít k práci s libovolným typem struktury pole.

#### Otázka: Podporuje Aspose.Words operace aktualizace pole?

Odpověď: Ano, Aspose.Words vám umožňuje aktualizovat pole podle plánu. Pomocí API můžete snadno aktualizovat hodnoty polí, aktualizovat výpočty a provádět další operace související s poli.

#### Otázka: Je možné pomocí Aspose.Words převést pole na prostý text?

A: Určitě! Aspose.Words poskytuje metody pro převod polí na prostý text. To může být užitečné, když potřebujete extrahovat obsah bez jakéhokoli formátování nebo funkcí souvisejících s poli.

#### Otázka: Je možné generovat dokumenty aplikace Word s dynamickými poli pomocí Aspose.Words?

A: Absolutně! Aspose.Words nabízí robustní funkce pro generování dokumentů aplikace Word s dynamickými poli. Můžete vytvářet šablony s předdefinovanými poli a dynamicky je plnit daty, což poskytuje flexibilní a efektivní řešení pro generování dokumentů.