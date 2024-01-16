---
title: Kopírovat text se záložkou v dokumentu aplikace Word
linktitle: Kopírovat text se záložkou v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se kopírovat text záložky v dokumentu aplikace Word do jiného dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-bookmarks/copy-bookmarked-text/
---

tomto článku prozkoumáme zdrojový kód C# výše, abychom pochopili, jak používat funkci Kopírovat text označený záložkou v knihovně Aspose.Words for .NET. Tato funkce umožňuje zkopírovat obsah konkrétní záložky ze zdrojového dokumentu do jiného dokumentu.

## Předpoklady

- Základní znalost jazyka C#.
- Vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

## Krok 1: Načtení zdrojového dokumentu

 Před zkopírováním textu záložky musíme načíst zdrojový dokument do a`Document` objekt pomocí cesty k souboru:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Krok 2: Získání záložky zdroje

 Používáme`Bookmarks` vlastnost rozsahu zdrojového dokumentu pro získání konkrétní záložky, kterou chceme zkopírovat:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Krok 3: Vytvoření cílového dokumentu

Vytvoříme nový dokument, který bude sloužit jako cílový dokument pro zkopírování obsahu záložky:

```csharp
Document dstDoc = new Document();
```

## Krok 4: Určení umístění kopie

Určíme umístění, kam chceme přidat zkopírovaný text. V našem příkladu přidáme text na konec těla poslední části cílového dokumentu:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Krok 5: Importujte a zkopírujte text záložky

 Používáme a`NodeImporter`objekt pro import a kopírování textu záložky ze zdrojového dokumentu do cílového dokumentu:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Příklad zdrojového kódu pro kopírování textu označeného záložkou pomocí Aspose.Words for .NET

Zde je úplný ukázkový zdrojový kód, který demonstruje kopírování textu ze záložky pomocí Aspose.Words for .NET:

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Toto je záložka, jejíž obsah chceme zkopírovat.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Tento dokument budeme doplňovat.
	Document dstDoc = new Document();

	// Řekněme, že budeme připojeni na konec těla poslední sekce.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Pokud importujete vícekrát bez jediného kontextu, vytvoří se mnoho stylů.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### AppendBookmarkedText Zdrojový kód

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
            // Toto je odstavec, který obsahuje začátek záložky.
            Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

            // Toto je odstavec, který obsahuje konec záložky.
            Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

            if (startPara == null || endPara == null)
                throw new InvalidOperationException(
                    "Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

            // Omezte se na přiměřeně jednoduchý scénář.
            if (startPara.ParentNode != endPara.ParentNode)
                throw new InvalidOperationException(
                    "Start and end paragraphs have different parents, cannot handle this scenario yet.");

            // Chceme zkopírovat všechny odstavce od počátečního odstavce až po (včetně) koncového odstavce,
            // proto uzel, u kterého zastavíme, je jeden za koncovým odstavcem.
            Node endNode = endPara.NextSibling;

            for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
            {
                //Tím se vytvoří kopie aktuálního uzlu a importuje se (učiní se platným) v kontextu
                // cílového dokumentu. Import znamená správnou úpravu stylů a identifikátorů seznamu.
                Node newNode = importer.ImportNode(curNode, true);

                dstNode.AppendChild(newNode);
            }
        }

```
## Závěr

V tomto článku jsme prozkoumali zdrojový kód C#, abychom pochopili, jak používat funkci Kopírovat text označený záložkou z Aspose.Words pro .NET. Při kopírování obsahu záložky ze zdrojového dokumentu do jiného dokumentu jsme postupovali podle podrobného průvodce.

### Časté dotazy pro kopírování textu označeného záložkou v dokumentu aplikace Word

#### Otázka: Jaké jsou požadavky na použití funkce "Kopírovat text se záložkami" v Aspose.Words for .NET?

A: Chcete-li použít funkci "Kopírovat text se záložkami" v Aspose.Words pro .NET, musíte mít základní znalosti jazyka C#. Potřebujete také vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

#### Otázka: Jak načtu zdrojový dokument do Aspose.Words for .NET?

 A: Chcete-li načíst zdrojový dokument v Aspose.Words pro .NET, můžete použít`Document` třídy zadáním cesty k souboru dokumentu. Zde je ukázkový kód:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### Otázka: Jak získat obsah konkrétní záložky ve zdrojovém dokumentu pomocí Aspose.Words for .NET?

 Odpověď: Chcete-li získat obsah konkrétní záložky ve zdrojovém dokumentu pomocí Aspose.Words for .NET, můžete přistupovat k`Bookmarks` vlastnost rozsahu zdrojového dokumentu a použijte název záložky k načtení konkrétní záložky. Zde je ukázkový kód:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### Otázka: Jak určit umístění kopie textu záložky v cílovém dokumentu pomocí Aspose.Words for .NET?

 Odpověď: Chcete-li určit, kam chcete přidat zkopírovaný text záložky v cílovém dokumentu pomocí Aspose.Words for .NET, můžete přejít do těla poslední části cílového dokumentu. Můžete použít`LastSection` vlastnost pro přístup k poslední sekci a`Body` vlastnost pro přístup k tělu této sekce. Zde je ukázkový kód:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### Otázka: Jak importovat a kopírovat text záložky ze zdrojového dokumentu do cílového dokumentu pomocí Aspose.Words for .NET?

 Odpověď: Chcete-li importovat a zkopírovat text záložky ze zdrojového dokumentu do cílového dokumentu pomocí Aspose.Words for .NET, můžete použít`NodeImporter` třída určující zdrojový dokument, cílový dokument a režim formátování, který se má zachovat. Poté můžete použít`AppendBookmarkedText` způsob přidání textu záložky do cílového dokumentu. Zde je ukázkový kód:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### Otázka: Jak uložit cílový dokument po zkopírování textu záložky pomocí Aspose.Words for .NET?

Odpověď: Chcete-li uložit cílový dokument po zkopírování textu ze záložky pomocí Aspose.Words for .NET, můžete použít`Save` metoda`Document` objekt určující cestu k cílovému souboru. Zde je ukázkový kód:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```