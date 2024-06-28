---
title: Zobrazit skrýt obsah označený záložkou v dokumentu aplikace Word
linktitle: Zobrazit skrýt obsah označený záložkou v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak dynamicky zobrazit nebo skrýt obsah označený záložkou v dokumentech aplikace Word pomocí Aspose.Words for .NET s tímto komplexním průvodcem krok za krokem.
type: docs
weight: 10
url: /cs/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## Úvod

Nazdárek! Chtěli jste někdy ovládat viditelnost konkrétního obsahu v dokumentu aplikace Word na základě určitých podmínek? S Aspose.Words for .NET můžete dynamicky zobrazit nebo skrýt obsah se záložkami pomocí několika řádků kódu. V tomto tutoriálu vás provedu procesem krok za krokem a zajistím, že porozumíte každé části kódu. Nakonec z vás bude profesionál v manipulaci se záložkami v dokumentech aplikace Word. Začněme!

## Předpoklady

Než se vrhneme na tutoriál, ujistěte se, že máte vše, co potřebujete:

1. Základní znalost C#: Měli byste být spokojeni se syntaxí a koncepty C#.
2.  Aspose.Words pro .NET: Stáhněte si ji[tady](https://releases.aspose.com/words/net/) . Pokud nejste připraveni na nákup, můžete začít s a[zkušební verze zdarma](https://releases.aspose.com/).
3. Visual Studio: Bude fungovat jakákoli nejnovější verze, ale doporučuje se používat nejnovější verzi.
4. .NET Framework: Ujistěte se, že je na vašem počítači nainstalováno.

Jste připraveni začít? Skvělý! Začněme importem potřebných jmenných prostorů.

## Importovat jmenné prostory

Chcete-li používat Aspose.Words pro .NET, musíme importovat požadované jmenné prostory. Tento krok zajišťuje, že máme přístup ke všem třídám a metodám, které budeme používat.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Tyto jmenné prostory jsou klíčové pro práci s dokumenty aplikace Word a manipulaci s jejich obsahem.

## Krok 1: Nastavení dokumentu

Nejprve vytvořte nový dokument aplikace Word a tvůrce dokumentů. Tvůrce dokumentů nám pomáhá snadno přidávat a manipulovat s obsahem v dokumentu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

V tomto kroku inicializujeme nový dokument a tvůrce dokumentů. Tím se naše prostředí nastaví pro další operace.

## Krok 2: Přidání obsahu označeného záložkou

Dále do dokumentu přidáme nějaký obsah a vytvoříme kolem něj záložku. Tato záložka nám pomůže identifikovat a manipulovat s obsahem.

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

 Zde přidáme nějaký text před a za obsah označený záložkou. The`StartBookmark` a`EndBookmark` metody definují hranice záložky.

## Krok 3: Vložení podmíněného pole

ovládání viditelnosti obsahu označeného záložkou použijeme podmíněné pole. Toto pole zkontroluje podmínku a podle toho zobrazí nebo skryje obsah.

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

V tomto kroku vložíme pole IF, které kontroluje hodnotu záložky. Pokud je hodnota "true", zobrazí se "Visible"; jinak se zobrazí "Skrytý".

## Krok 4: Přeuspořádání uzlů

Dále musíme změnit uspořádání uzlů, abychom zajistili, že se podmíněná logika správně aplikuje na obsah v záložkách.

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
    currentNode = nextNode;
}

Node endNode = bm.BookmarkEnd;
flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.FieldEnd)
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
    endNode = currentNode;
    currentNode = nextNode;
}
```

Zde přesouváme uzly, abychom se ujistili, že podmínka správně zahrnuje obsah v záložkách.

## Krok 5: Provedení hromadné korespondence

Nakonec provedeme hromadnou korespondenci, abychom nastavili hodnotu záložky a určili, zda se má obsah zobrazit nebo skrýt.

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

Tento krok nastaví hodnotu záložky na "true", což zviditelní obsah na základě našeho stavu.

## Krok 6: Uložení dokumentu

Po všech manipulacích je posledním krokem uložení upraveného dokumentu.

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

Zde dokument uložíme s popisným názvem souboru pro označení změn.

## Závěr

 A to je vše! Úspěšně jste se naučili, jak zobrazit nebo skrýt obsah označený záložkou v dokumentu aplikace Word pomocí Aspose.Words for .NET. Tento kurz se zabýval vytvářením dokumentu, přidáváním záložek, vkládáním podmíněných polí, přeskupováním uzlů a prováděním hromadné korespondence. Aspose.Words nabízí nepřeberné množství funkcí, takže neváhejte a prozkoumejte[API dokumentace](https://reference.aspose.com/words/net/) pro pokročilejší možnosti.

## Nejčastější dotazy

### 1. Co je Aspose.Words pro .NET?

Aspose.Words for .NET je výkonná knihovna, která umožňuje vývojářům vytvářet, upravovat a převádět dokumenty aplikace Word programově. Je široce používán pro úlohy automatizace dokumentů.

### 2. Mohu používat Aspose.Words pro .NET zdarma?

 Můžete zkusit Aspose.Words for .NET pomocí a[zkušební verze zdarma](https://releases.aspose.com/). Pro dlouhodobé používání si budete muset zakoupit licenci.

### 3. Jak mohu upravit další vlastnosti záložky?

 Aspose.Words vám umožňuje manipulovat s různými vlastnostmi záložky, jako je její text a umístění. Odkazovat na[API dokumentace](https://reference.aspose.com/words/net/) pro podrobné pokyny.

### 4. Jak získám podporu pro Aspose.Words for .NET?

Podporu můžete získat návštěvou stránky[Aspose fórum podpory](https://forum.aspose.com/c/words/8).

### 5. Mohu pomocí Aspose.Words for .NET manipulovat s jinými typy obsahu?

Ano, Aspose.Words for .NET podporuje různé typy manipulace s obsahem, včetně textu, obrázků, tabulek a dalších.