---
title: Přidat komentáře
linktitle: Přidat komentáře
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se přidávat komentáře do dokumentů aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-comments/add-comments/
---

tomto komplexním tutoriálu se naučíte přidávat komentáře k dokumentu aplikace Word pomocí Aspose.Words for .NET. Provedeme vás celým procesem a poskytneme vám potřebné úryvky kódu C#. Na konci této příručky budete moci vkládat komentáře a upravovat jejich obsah ve svých dokumentech.

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Knihovna Aspose.Words for .NET nainstalovaná ve vašem systému.

## Krok 1: Vytvořte nový dokument a DocumentBuilder
Chcete-li začít, vytvořte nový dokument pomocí třídy Document a inicializujte objekt DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Přidejte obsah do dokumentu
Dále přidejte požadovaný obsah do dokumentu pomocí objektu DocumentBuilder. V tomto příkladu přidáme nějaký text:

```csharp
builder.Write("Some text is added.");
```

## Krok 3: Vytvořte komentář a přidejte obsah
Chcete-li přidat komentář, vytvořte instanci třídy Comment, předejte objekt Document, jméno autora, iniciály autora a aktuální datum:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

Dále přidejte komentář k aktuálnímu odstavci:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Přidejte do komentáře obsah, například odstavec a text:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Krok 4: Uložte dokument
Po přidání komentáře a jeho obsahu uložte dokument do souboru pomocí metody Save třídy Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Příklad zdrojového kódu pro přidávání komentářů pomocí Aspose.Words pro .NET
Zde je kompletní zdrojový kód pro přidávání komentářů pomocí Aspose.Words pro .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Závěr
Gratulujeme! Úspěšně jste se naučili přidávat komentáře do dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete nyní vkládat komentáře a přizpůsobovat jejich obsah do svých dokumentů.

Komentáře jsou užitečné pro spolupráci, poskytování dalších informací nebo vytváření poznámek v dokumentu. Experimentujte s různými jmény autorů, iniciálami a obsahem komentářů, abyste splnili své specifické požadavky.

### FAQ

#### Otázka: Jak mohu přidat komentář do dokumentu Aspose.Words for .NET?

A: Chcete-li přidat komentář do dokumentu Aspose.Words for .NET, musíte postupovat podle kroků uvedených v tutoriálu.

#### Otázka: Mohu formátovat text komentáře v Aspose.Words pro .NET?

Odpověď: Ano, můžete formátovat text komentáře v Aspose.Words pro .NET pomocí dostupných vlastností formátování.

#### Otázka: Jak mohu načíst všechny komentáře přítomné v dokumentu?

Odpověď: Všechny komentáře přítomné v dokumentu můžete načíst pomocí`Document.Comments` vlastnictví.

#### Otázka: Mohu smazat konkrétní komentář v Aspose.Words pro .NET?

 Odpověď: Ano, můžete odstranit konkrétní komentář v Aspose.Words pro .NET pomocí`Comment.Remove` metoda.

#### Otázka: Jak mohu upravit text existujícího komentáře v Aspose.Words pro .NET?

 A: Chcete-li upravit text existujícího komentáře v Aspose.Words pro .NET, můžete přistupovat k`Comment.Text` vlastnost odpovídající`Comment` objekt a upravte text podle potřeby.