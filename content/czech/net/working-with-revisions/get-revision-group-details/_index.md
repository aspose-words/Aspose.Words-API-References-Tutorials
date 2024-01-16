---
title: Získejte podrobnosti o skupině revizí
linktitle: Získejte podrobnosti o skupině revizí
second_title: Aspose.Words API pro zpracování dokumentů
description: Získejte podrobnosti o skupině revizí v dokumentu aplikace Word pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/working-with-revisions/get-revision-group-details/
---

V tomto podrobném průvodci vám ukážeme, jak získat podrobnosti o skupině revizí v dokumentu aplikace Word pomocí Aspose.Words for .NET. Poskytneme vám kompletní zdrojový kód a ukážeme vám, jak formátovat výstup markdown.

## Krok 1: Načtení dokumentu

Prvním krokem je nahrání dokumentu obsahujícího revize.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Krok 2: Procházení revizí

Dále projdeme revize přítomné v dokumentu a zobrazíme jejich podrobnosti, jako je typ, autor, datum a revidovaný text.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Příklad zdrojového kódu pro Get Revision Group Details pomocí Aspose.Words for .NET

Zde je úplný zdrojový kód pro získání podrobností o skupině revizí v dokumentu pomocí Aspose.Words for .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## Závěr

tomto tutoriálu jsme se naučili, jak získat podrobnosti o skupině revizí v dokumentu aplikace Word pomocí Aspose.Words for .NET. Pomocí smyčky a příslušných vlastností jsme byli schopni zobrazit podrobnosti, jako je typ revize, autor, datum a revidovaný text. Aspose.Words for .NET nabízí mnoho výkonných funkcí pro manipulaci s dokumenty Word, včetně správy revizí. Nyní můžete tyto znalosti použít k získání podrobností o skupině revizí do vašich vlastních dokumentů aplikace Word pomocí Aspose.Words for .NET.

### FAQ

#### Otázka: Jak načtu dokument s revizemi do Aspose.Words pro .NET?

 A: Použijte`Document`třídy Aspose.Words for .NET k načtení dokumentu ze souboru obsahujícího revize. Můžete zadat úplnou cestu dokumentu.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Otázka: Jak získám podrobnosti o skupině revizí v Aspose.Words for .NET?

 Odpověď: Projděte revize dokumentu pomocí smyčky a otevřete vlastnosti každé revize, abyste získali požadované podrobnosti. Můžete použít`RevisionType`, `Author`, `DateTime` a`ParentNode` vlastnosti, abyste získali typ revize, autora, datum a revidovaný text.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### Otázka: Jak zkontrolovat, zda revize patří do skupiny v Aspose.Words pro .NET?

 A: Použijte`Group` vlastnictvím`Revision` objekt pro kontrolu, zda revize patří do skupiny. Pokud`Group` majetek je`null`to znamená, že revize nepatří do žádné skupiny.

```csharp
if (revision.Group != null)
{
      // Revize patří do skupiny
}
else
{
      // Revize nepatří do žádné skupiny
}
```