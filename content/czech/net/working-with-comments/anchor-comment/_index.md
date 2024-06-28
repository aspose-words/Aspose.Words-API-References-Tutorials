---
title: Komentář kotvy
linktitle: Komentář kotvy
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak ukotvit odpovědi na komentáře ke konkrétnímu textu v dokumentech aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-comments/anchor-comment/
---

tomto komplexním tutoriálu se naučíte, jak ukotvit odpovědi na komentáře ke konkrétnímu textu v dokumentu aplikace Word pomocí Aspose.Words for .NET. Provedeme vás celým procesem a poskytneme vám potřebné úryvky kódu C#. Na konci této příručky budete moci přiřadit komentáře ke konkrétnímu textu ve vašich dokumentech.

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Knihovna Aspose.Words for .NET nainstalovaná ve vašem systému.

## Krok 1: Vytvořte nový dokument a přidejte text
Chcete-li začít, vytvořte nový dokument pomocí třídy Document a přidejte požadovaný text:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## Krok 2: Vytvořte komentář a přidejte rozsah komentářů
Dále vytvořte komentář a přiřaďte jej ke konkrétnímu textu pomocí objektů CommentRangeStart a CommentRangeEnd:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## Krok 3: Uložte dokument
Po ukotvení komentáře ke konkrétnímu textu uložte dokument do souboru pomocí metody Save třídy Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Příklad zdrojového kódu pro odpověď na komentář kotvy pomocí Aspose.Words for .NET
Zde je úplný zdrojový kód pro ukotvení odpovědi na komentář pomocí Aspose.Words pro .NET:

```csharp
// Vytvořte instanci dokumentu.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Vytvořte tři objekty Run.
//První dva spouští nějaký text, zatímco třetí spouští komentář

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

// Každý z objektů Run má přidružený objekt CommentRangeStart a CommentRangeEnd.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### FAQ

#### Otázka: Co je kotva komentářů v Aspose.Words pro .NET?

Odpověď: V Aspose.Words for .NET je kotva komentáře značka, která spojuje komentář s konkrétním umístěním v dokumentu.

#### Otázka: Jak mohu přidat kotvu komentáře do dokumentu Aspose.Words for .NET?

A: Chcete-li přidat kotvu komentáře do dokumentu Aspose.Words for .NET, postupujte podle kroků uvedených v tutoriálu.

#### Otázka: Jak získám přístup k existující kotvě komentářů v Aspose.Words pro .NET?

 Odpověď: Ke stávající kotvě komentářů v Aspose.Words pro .NET můžete přistupovat pomocí`Comment.Anchor` vlastnictví.

#### Otázka: Mohu převýšit kotvu komentářů v Aspose.Words pro .NET?

 Odpověď: Ano, můžete odstranit kotvu komentáře v Aspose.Words pro .NET pomocí`Comment.Remove` metoda.

#### Otázka: Jak mohu upravit text komentáře propojeného s kotvou komentáře v Aspose.Words for .NET?

Odpověď: Chcete-li upravit text komentáře vázaného na kotvu komentáře v Aspose.Words pro .NET, můžete získat přístup k`Comment.Text` vlastnost odpovídající`Comment` objekt a upravte text podle potřeby.

