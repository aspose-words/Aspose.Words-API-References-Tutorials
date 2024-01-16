---
title: Získejte revizní typy slov
linktitle: Získejte revizní typy slov
second_title: Aspose.Words API pro zpracování dokumentů
description: Získejte typy revizí slov v dokumentu aplikace Word pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/working-with-revisions/get-revision-types/
---

V tomto průvodci krok za krokem vám řekneme, jak získat typy revizí slov v dokumentu aplikace Word pomocí Aspose.Words for .NET. Poskytneme vám kompletní zdrojový kód a ukážeme vám, jak formátovat výstup markdown.

## Krok 1: Načtení dokumentu

Prvním krokem je nahrání dokumentu obsahujícího revize.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Krok 2: Projděte si odstavce

Dále projdeme odstavce dokumentu a zkontrolujeme typy revizí slov spojených s každým odstavcem.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Příklad zdrojového kódu pro získání typů revizí pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód pro získání typů revizí v dokumentu pomocí Aspose.Words pro .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## Závěr

tomto tutoriálu jsme se naučili, jak získat typy revizí slov v dokumentu aplikace Word pomocí Aspose.Words for .NET. Postupovali jsme podle kroků k načtení dokumentu, procházení odstavců a kontrole typů slovních recenzí spojených s každým odstavcem. Nyní můžete tyto znalosti použít k analýze slovních recenzí ve vašich vlastních dokumentech aplikace Word pomocí Aspose.Words for .NET.

### Časté dotazy pro získání revizních typů slov

#### Otázka: Jak nahrát dokument do Aspose.Words pro .NET?

 A: Použijte`Document` třídy Aspose.Words pro .NET k načtení dokumentu ze souboru. Můžete zadat úplnou cestu dokumentu.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Otázka: Jak mohu procházet odstavce v dokumentu v Aspose.Words pro .NET?

 A: Použijte`Paragraphs` vlastnost sekce dokumentu pro získání kolekce odstavců. Pomocí smyčky pak můžete procházet každý odstavec.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Zde zpracujte každý odstavec
}
```

#### Otázka: Jak zkontrolovat, zda byl odstavec přesunut (smazán) v Aspose.Words pro .NET?

 A: Použijte odstavce`IsMoveFromRevision` vlastnost zkontrolovat, zda byla přesunuta (smazána).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // Odstavec byl přesunut (smazán)
}
```

#### Otázka: Jak zkontrolovat, zda byl odstavec přesunut (vložen) v Aspose.Words pro .NET?

 A: Použijte odstavce`IsMoveToRevision`vlastnost zkontrolovat, zda byla přesunuta (vložena).

```csharp
if (paragraph.IsMoveToRevision)
{
     // Odstavec byl přesunut (vložen)
}
```