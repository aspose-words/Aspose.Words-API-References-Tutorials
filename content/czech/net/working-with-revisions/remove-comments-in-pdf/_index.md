---
title: Odebrat komentáře v souboru PDF
linktitle: Odebrat komentáře v souboru PDF
second_title: Aspose.Words API pro zpracování dokumentů
description: Odstraňte komentáře ze souboru PDF pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-revisions/remove-comments-in-pdf/
---

V tomto podrobném průvodci vám řekneme, jak odstranit komentáře v souboru PDF pomocí Aspose.Words for .NET. Poskytneme vám kompletní zdrojový kód a ukážeme vám, jak formátovat výstup markdown.

## Krok 1: Načtení dokumentu

Prvním krokem je načtení dokumentu obsahujícího komentáře.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Krok 2: Skrytí komentářů v PDF

Nakonfigurujeme možnost rozvržení tak, aby byly komentáře při generování PDF skryty.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## Krok 3: Uložte dokument jako PDF

Nakonec dokument uložíme ve formátu PDF smazáním komentářů.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Výstupní formáty Markdown

Výstup lze formátovat v markdown pro zlepšení čitelnosti. Například :

```markdown
- Comments are hidden in the generated PDF.
```

### Příklad zdrojového kódu pro Remove Comments In Pdf pomocí Aspose.Words for .NET

Zde je úplný zdrojový kód pro odstranění komentářů v souboru PDF pomocí Aspose.Words pro .NET:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Skrýt komentáře v PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Závěr

tomto tutoriálu jsme se naučili, jak odstranit komentáře ze souboru PDF pomocí Aspose.Words for .NET. Pomocí vhodných možností rozvržení jsme byli schopni skrýt komentáře při generování PDF. Aspose.Words for .NET nabízí velkou flexibilitu pro manipulaci se soubory aplikace Word a jejich převod do různých formátů, včetně PDF. Nyní můžete tyto znalosti použít k odstranění komentářů ve vašich vlastních souborech PDF pomocí Aspose.Words for .NET.

### Časté dotazy pro odstranění komentářů v souboru pdf

#### Otázka: Jak nahrát dokument do Aspose.Words pro .NET?

 A: Použijte`Document` třídy Aspose.Words pro .NET k načtení dokumentu ze souboru. Můžete zadat úplnou cestu dokumentu.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Otázka: Jak skrýt komentáře v PDF generovaném pomocí Aspose.Words pro .NET?

 A: Použijte`CommentDisplayMode` vlastnictvím`LayoutOptions` objekt pro konfiguraci způsobu zobrazení poznámek při generování PDF. Chcete-li skrýt komentáře, nastavte tuto vlastnost na`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### Otázka: Jak uložit dokument jako PDF pomocí Aspose.Words pro .NET?

 A: Použijte`Save` metoda`Document` objekt pro uložení dokumentu ve formátu PDF. Zadejte úplnou cestu k souboru PDF.

```csharp
doc.Save("path/to/the/file.pdf");
```