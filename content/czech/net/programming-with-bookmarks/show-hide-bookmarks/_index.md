---
title: Zobrazit skrýt záložky v dokumentu aplikace Word
linktitle: Zobrazit skrýt záložky v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak zobrazit nebo skrýt konkrétní záložku v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-bookmarks/show-hide-bookmarks/
---

V tomto článku prozkoumáme zdrojový kód C# výše, abychom pochopili, jak používat funkci Zobrazit skrýt záložky v knihovně Aspose.Words for .NET. Tato funkce umožňuje zobrazit nebo skrýt určitou záložku v dokumentu aplikace Word.

## Předpoklady

- Základní znalost jazyka C#.
- Vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

## Krok 1: Načtení dokumentu

 Používáme`Document` třídy k načtení existujícího dokumentu ze souboru:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Krok 2: Zobrazte nebo skryjte konkrétní záložku

 Používáme`ShowHideBookmarkedContent` funkce pro zobrazení nebo skrytí konkrétní záložky v dokumentu. Tato funkce bere jako parametry dokument, název záložky a boolean označující, zda se má záložka zobrazit nebo skrýt:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Krok 3: Uložení upraveného dokumentu

 Používáme`Save` způsob uložení upraveného dokumentu do souboru:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Příklad zdrojového kódu pro Zobrazit skrýt záložky pomocí Aspose.Words pro .NET

Zde je úplný ukázkový zdrojový kód, který demonstruje zobrazení nebo skrytí konkrétní záložky pomocí Aspose.Words pro .NET:

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### ShowHideBookmarkedContent zdrojový kód

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
            Bookmark bm = doc.Range.Bookmarks[bookmarkName];

            DocumentBuilder builder = new DocumentBuilder(doc);
            builder.MoveToDocumentEnd();

            // {IF "{MERGEFIELD bookmark}" = "true" "" ""}
            Field field = builder.InsertField("IF \"", null);
            builder.MoveTo(field.Start.NextSibling);
            builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
            builder.Write("\" = \"true\" ");
            builder.Write("\"");
            builder.Write("\"");
            builder.Write(" \"\"");

            Node currentNode = field.Start;
            bool flag = true;
            while (currentNode != null && flag)
            {
                if (currentNode.NodeType == NodeType.Run)
                    if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
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

            doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });
        }
		
```
## Závěr

V tomto článku jsme prozkoumali zdrojový kód C#, abychom pochopili, jak používat funkci Zobrazit skrýt záložky v Aspose.Words pro .NET. Postupovali jsme podle podrobného průvodce, jak zobrazit nebo skrýt konkrétní záložku v dokumentu.

### Nejčastější dotazy k zobrazení skrýt záložky v dokumentu aplikace Word

#### Otázka: Mohu zobrazit nebo skrýt více záložek v jednom dokumentu?

Odpověď: Ano, můžete zobrazit nebo skrýt více záložek v jednom dokumentu opakováním kroků 2 a 3 pro každou záložku, kterou chcete zpracovat.

#### Otázka: Funguje poskytnutý kód s jinými formáty dokumentů aplikace Word, jako jsou .doc nebo .docm?

Odpověď: Ano, poskytnutý kód funguje s různými formáty dokumentů Word podporovanými Aspose.Words, jako jsou .doc a .docm. Při načítání a ukládání dokumentu se ujistěte, že používáte správný název souboru a cestu.

#### Otázka: Jak mohu znovu zobrazit skrytou záložku?

 Odpověď: Chcete-li znovu zobrazit skrytou záložku, musíte použít stejnou`ShowHideBookmarkedContent` funkce předávající hodnotu`true` pro booleovský parametr, který označuje, zda se má záložka zobrazit nebo skrýt.

#### Otázka: Mohu použít podmínky k zobrazení nebo skrytí záložek na základě hodnot slučovacích polí v dokumentu?

 Odpověď: Ano, můžete použít podmínky a sloučit hodnoty polí k určení, zda má být záložka zobrazena nebo skryta. Kód si můžete přizpůsobit`ShowHideBookmarkedContent` funkce zohlednit vhodné podmínky a hodnoty.

#### Otázka: Jak mohu odstranit záložku v dokumentu aplikace Word pomocí Aspose.Words for .NET?

 Odpověď: Chcete-li odstranit záložku v dokumentu aplikace Word pomocí Aspose.Words for .NET, můžete použít`RemoveBookmarks` metoda`Document` třída. Zde je ukázkový kód:

```csharp
doc.RemoveBookmarks("BookmarkName");
```