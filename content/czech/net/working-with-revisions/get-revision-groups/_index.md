---
title: Získejte skupiny revizí
linktitle: Získejte skupiny revizí
second_title: Aspose.Words API pro zpracování dokumentů
description: Získejte skupiny revizí v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-revisions/get-revision-groups/
---

V tomto průvodci krok za krokem vám řekneme, jak získat skupiny revizí v dokumentu aplikace Word pomocí Aspose.Words for .NET. Poskytneme vám kompletní zdrojový kód a ukážeme vám, jak formátovat výstup markdown.

## Krok 1: Načtení dokumentu

Prvním krokem je nahrání dokumentu obsahujícího revize.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Krok 2: Procházení skupin revizí

Dále projdeme skupiny revizí v dokumentu a zobrazíme jejich podrobnosti, jako je autor, typ revize a revidovaný text.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Příklad zdrojového kódu pro Get Revision Groups pomocí Aspose.Words for .NET

Zde je úplný zdrojový kód pro získání skupin revizí v dokumentu pomocí Aspose.Words pro .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## Závěr

tomto tutoriálu jsme se naučili, jak získat skupiny revizí v dokumentu aplikace Word pomocí Aspose.Words for .NET. Postupovali jsme podle kroků k načtení dokumentu a procházení skupin recenzí, přičemž jsme zobrazili podrobnosti, jako je autor a typ recenze. Nyní můžete tyto znalosti použít k analýze revizí vašeho vlastního dokumentu Word pomocí Aspose.Words for .NET.

### FAQ

#### Otázka: Jak nahrát dokument do Aspose.Words pro .NET?

 A: Použijte`Document` třídy Aspose.Words pro .NET k načtení dokumentu ze souboru. Můžete zadat úplnou cestu dokumentu.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Otázka: Jak procházet skupiny revizí v dokumentu v Aspose.Words for .NET?

 A: Použijte`Groups` vlastnost dokumentu`Revisions` objekt k získání kolekce skupin revizí. Poté můžete použít smyčku k procházení každou skupinou recenzí.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Zde zpracujte každou kontrolní skupinu
}
```

#### Otázka: Jak získat autora recenzní skupiny v Aspose.Words pro .NET?

 A: Použijte`Author` vlastnictvím`RevisionGroup` objekt získat autora revizní skupiny.

```csharp
string author = group.Author;
```

#### Otázka: Jak získat typ revize skupiny revizí v Aspose.Words pro .NET?

 A: Použijte`RevisionType` vlastnictvím`RevisionGroup`objekt, abyste získali typ revize skupiny.

```csharp
string revisionType = group.RevisionType;
```