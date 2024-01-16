---
title: Přidejte Bidi značky do dokumentu Word
linktitle: Přidejte Bidi značky do dokumentu Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se přidávat Bidi značky do dokumentu aplikace Word pomocí Aspose.Words for .NET a vytvářejte profesionální vícejazyčné dokumenty.
type: docs
weight: 10
url: /cs/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words for .NET je výkonná knihovna pro vytváření, úpravy a manipulaci s dokumenty Wordu v aplikaci C#. Mezi funkcemi, které Aspose.Words nabízí, je možnost přidat do dokumentu Bidi (obousměrné) značky. V této příručce vás provedeme tím, jak použít zdrojový kód C# Aspose.Words for .NET k přidání značek Bidi do dokumentu.

## Porozumění knihovně Aspose.Words

Než se ponoříte do kódu, je důležité porozumět knihovně Aspose.Words pro .NET. Aspose.Words je oblíbená knihovna, která usnadňuje a zefektivňuje zpracování textu s dokumenty aplikace Word. Nabízí širokou škálu funkcí pro vytváření, úpravu a manipulaci s dokumenty Word, včetně přidávání značek Bidi.

## Vytvoření dokumentu a přidání obsahu

Prvním krokem je vytvoření nového dokumentu a přidání obsahu do něj. Pomocí třídy Document vytvořte novou instanci dokumentu. Poté použijte třídu DocumentBuilder k přidání textu do dokumentu. Zde je příklad:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

tomto příkladu vytvoříme nový dokument a použijeme DocumentBuilder k přidání textu. Přidali jsme tři řádky textu: jeden v angličtině, jeden v hebrejštině a jeden v arabštině, abychom ukázali přidávání obsahu v různých jazycích.

## Přidány značky Bidi

Po přidání obsahu můžeme nyní do dokumentu přidat značky Bidi. K tomu použijeme třídu TxtSaveOptions a vlastnost AddBidiMarks nastavíme na true. Zde je postup:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

V tomto příkladu vytvoříme instanci TxtSaveOptions a nastavíme vlastnost AddBidiMarks na true. Dále použijeme metodu Save třídy Document k uložení dokumentu s Bidi značkami.

### Příklad zdrojového kódu pro funkci "Přidat Bidi Marks" s Aspose.Words pro .NET

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte dokument a přidejte obsah
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Přidejte značky Bidi
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Závěr

této příručce jsme vysvětlili, jak použít Aspose.Words pro .NET k přidání značek Bidi do dokumentu aplikace Word pomocí poskytnutého zdrojového kódu C#. Podle uvedených kroků můžete snadno přidat značky Bidi do dokumentů aplikace Word v aplikaci C#. Aspose.Words nabízí obrovskou flexibilitu a výkon pro zpracování textu s formátováním textu a správou jazyků, což vám umožňuje profesionálně vytvářet vícejazyčné dokumenty.

### Často kladené otázky

#### Otázka: Co je Aspose.Words for .NET?
Aspose.Words for .NET je výkonná knihovna pro vytváření, úpravy a manipulaci s dokumenty Word v aplikaci C#. Nabízí mnoho funkcí pro zpracování textu s dokumenty Word, včetně přidávání Bidi (obousměrných) značek.

#### Otázka: Jaké funkce nabízí Aspose.Words for .NET?
Aspose.Words for .NET nabízí širokou škálu funkcí pro vytváření, úpravy a manipulaci s dokumenty aplikace Word. Některé z těchto funkcí zahrnují vytváření dokumentů, přidávání obsahu, formátování textu, správu tabulek, slučování a rozdělování dokumentů, převod dokumentů a další.

#### Otázka: Jak mohu přidat značky Bidi do dokumentu aplikace Word pomocí Aspose.Words for .NET?
Značky Bidi můžete do dokumentu aplikace Word přidat takto:

 Vytvořte nový dokument pomocí`Document` třída.

 Použijte`DocumentBuilder` třídy přidat obsah do dokumentu.

 Jakmile přidáte obsah, použijte`TxtSaveOptions` třídu a nastavte`AddBidiMarks`majetek do`true`.

 Uložte dokument s Bidi značkami pomocí`Save` metoda`Document` třída.

#### Otázka: Podporuje Aspose.Words více jazyků pro přidávání značek Bidi?
Ano, Aspose.Words podporuje více jazyků pro přidávání značek Bidi. Bidi značky můžete přidat do textu v různých jazycích, jako je angličtina, hebrejština a arabština, pomocí Aspose.Words for .NET.

#### Otázka: Existují nějaké další možnosti pro uložení dokumentu se značkami Bidi?
 Ano, můžete zadat další možnosti při ukládání dokumentu s Bidi značkami pomocí`TxtSaveOptions` třída. Můžete například nastavit formát uložení dokumentu, možnosti kódování atd.