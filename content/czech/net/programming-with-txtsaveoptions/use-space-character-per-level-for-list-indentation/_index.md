---
title: Pro odsazení seznamu použijte mezeru na úroveň
linktitle: Pro odsazení seznamu použijte mezeru na úroveň
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce používáním mezery na úrovni pro odsazení seznamu v Aspose.Words pro .NET. Snadno vytvářejte dobře strukturované dokumenty aplikace Word.
type: docs
weight: 10
url: /cs/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words for .NET je výkonná knihovna pro vytváření, úpravy a manipulaci s dokumenty Wordu v aplikaci C#. Mezi funkce nabízené Aspose.Words patří možnost použití jednoho znaku mezery na úroveň pro odsazení seznamů. V této příručce vám ukážeme, jak použít zdrojový kód C# Aspose.Words for .NET k implementaci této funkce.

## Porozumění knihovně Aspose.Words

Než se ponoříte do kódu, je důležité porozumět knihovně Aspose.Words pro .NET. Aspose.Words je oblíbená knihovna, která usnadňuje a zefektivňuje zpracování textu s dokumenty aplikace Word. Nabízí širokou škálu funkcí pro vytváření, úpravu a manipulaci s dokumenty Word, včetně správy seznamů a odsazení.

## Vytvoření dokumentu a přidání obsahu

Prvním krokem je vytvoření nového dokumentu a přidání obsahu do něj. Pomocí třídy Document vytvořte novou instanci dokumentu. Poté pomocí třídy DocumentBuilder přidejte text a vytvořte seznam s více úrovněmi odsazení. Zde je příklad:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Vytvořte seznam se třemi úrovněmi odsazení
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

V tomto příkladu vytvoříme nový dokument a pomocí DocumentBuilder přidáme text a vytvoříme seznam se třemi úrovněmi odsazení. Do seznamu jsme přidali tři položky, přičemž každá položka označuje další úroveň.

## Použití jednoho znaku mezery na úroveň pro odsazení seznamu

Po přidání obsahu můžeme nyní nakonfigurovat odsazení seznamů pomocí jedné mezery na úroveň. K tomu použijeme třídu TxtSaveOptions a vlastnost ListIndentation.Count nastavíme na počet úrovní odsazení a vlastnost ListIndentation.Character na znak mezery, který se má použít. Zde je postup:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

tomto příkladu vytvoříme instanci TxtSaveOptions a nastavíme vlastnost ListIndentation.Count na 3, abychom indikovali, že v seznamu jsou tři úrovně odsazení. Vlastnost ListIndentation.Character jsme také nastavili na znak mezery (' '), který chceme použít pro odsazení.

### Příklad zdrojového kódu pro funkci "Použít jeden znak mezery na úroveň pro odsazení seznamu" s Aspose.Words for .NET

Zde je úplný ukázkový zdrojový kód pro funkci "Použít jeden znak mezery na úroveň pro odsazení seznamu" s Aspose.Words pro .NET:

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             // Cesta k vašemu adresáři dokumentů
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             // Vytvořte dokument a přidejte obsah
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             // Vytvořte seznam se třemi úrovněmi odsazení
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             // Pro odsazení seznamu použijte jednu mezeru na úroveň
             TxtSaveOptions saveOptions = new TxtSaveOptions();
             saveOptions.ListIndentation.Count = 3;
             saveOptions.ListIndentation.Character = ' ';

             // Uložte dokument se zadanými možnostmi
             doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
         }
     }
}

```

## Závěr

této příručce jsme vysvětlili, jak používat Aspose.Words pro .NET k použití funkce "Použít jeden znak mezery na úroveň pro odsazení seznamu". Podle uvedených kroků a pomocí poskytnutého zdrojového kódu C# můžete snadno nakonfigurovat odsazení seznamů v dokumentech aplikace Word pomocí jedné mezery na úroveň. Aspose.Words nabízí obrovskou flexibilitu a výkon pro textové zpracování s formátováním textu a správou seznamů, což vám umožňuje vytvářet dobře strukturované dokumenty ve vaší aplikaci C#.

### Často kladené otázky

#### Otázka: Co je Aspose.Words for .NET?
Aspose.Words for .NET je výkonná knihovna pro vytváření, úpravy a manipulaci s dokumenty Word v aplikaci C#. Nabízí mnoho funkcí pro zpracování textu s dokumenty Word, včetně možnosti použít jednu mezeru na úroveň pro odsazení seznamů.

#### Otázka: Jak mohu použít jednu mezeru na úroveň pro odsazení seznamu pomocí Aspose.Words pro .NET?
Pro odsazení seznamu můžete použít jednu mezeru na úroveň:

 Vytvořte nový dokument pomocí`Document` třída.

 Použijte`DocumentBuilder`třídy přidat obsah do dokumentu a vytvořit seznam s více úrovněmi odsazení.

 Jakmile přidáte obsah a nakonfigurujete odsazení seznamu, použijte`TxtSaveOptions` třídu a nastavte`ListIndentation.Count` vlastnost k počtu úrovní odsazení a`ListIndentation.Character` nemovitost na prostranství (`' '`) použít.

 Uložte dokument se zadanými možnostmi pomocí`Save` metoda`Document` třída.

#### Otázka: Podporuje Aspose.Words jiné znaky pro odsazení seznamu?
Ano, Aspose.Words podporuje jiné znaky pro odsazení seznamů. Můžete použít znaky bez mezer, jako jsou tabulátory (`'\t'` ) nebo jiné speciální znaky nastavením`ListIndentation.Character` vlastnost na požadovaný znak.

#### Otázka: Je možné upravit počet mezer na úrovni pro odsazení seznamu?
 Ano, můžete upravit počet mezer na úrovni pro odsazení seznamu změnou hodnoty`ListIndentation.Count` nemovitost v`TxtSaveOptions` třída. Můžete zadat požadovaný počet mezer pro každou úroveň odsazení.

#### Otázka: Jaké další funkce nabízí Aspose.Words pro správu seznamu?
Aspose.Words nabízí mnoho funkcí pro správu seznamů v dokumentech aplikace Word. Můžete vytvářet číslované seznamy nebo seznamy s odrážkami, nastavovat úrovně odsazení, přizpůsobovat styl seznamů, přidávat položky seznamu a další.