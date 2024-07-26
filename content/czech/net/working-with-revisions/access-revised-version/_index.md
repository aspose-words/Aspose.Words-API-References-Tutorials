---
title: Přístup k revidované verzi
linktitle: Přístup k revidované verzi
second_title: Aspose.Words API pro zpracování dokumentů
description: Získejte přístup k revidované verzi dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-revisions/access-revised-version/
---

V tomto podrobném průvodci vám ukážeme, jak získat přístup k revidované verzi dokumentu aplikace Word pomocí Aspose.Words for .NET. Poskytneme vám kompletní zdrojový kód a ukážeme vám, jak formátovat výstup markdown.

## Krok 1: Načtení dokumentu

Prvním krokem je nahrání dokumentu obsahujícího revize.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Krok 2: Přístup k revidované verzi

Nyní přejdeme k revidované verzi dokumentu.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Krok 3: Procházení revizí

Dále projdeme revize v dokumentu a zobrazíme konkrétní informace pro odstavce, které jsou položkami seznamu.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Příklad zdrojového kódu pro Access Revised Version pomocí Aspose.Words for .NET

Zde je úplný zdrojový kód pro přístup k revidované verzi dokumentu pomocí Aspose.Words pro .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Přepněte na revidovanou verzi dokumentu.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## Závěr

tomto tutoriálu jsme se naučili, jak získat přístup k revidované verzi dokumentu aplikace Word pomocí Aspose.Words for .NET. Načtením dokumentu, přechodem na revidovanou verzi a procházením revizí jsme byli schopni získat konkrétní informace pro odstavce, které jsou položkami seznamu. Aspose.Words for .NET nabízí výkonné funkce pro manipulaci s dokumenty aplikace Word, včetně přístupu k recenzím. Nyní můžete tyto znalosti využít k přístupu k revidované verzi svých vlastních dokumentů Word pomocí Aspose.Words for .NET.

### FAQ

#### Otázka: Jak načtu dokument s revizemi do Aspose.Words pro .NET?

 A: Použijte`Document` třídy Aspose.Words for .NET k načtení dokumentu ze souboru obsahujícího revize. Můžete zadat úplnou cestu dokumentu.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Otázka: Jak získám přístup k revidované verzi dokumentu v Aspose.Words for .NET?

 A: Použijte`RevisionsView` majetek z`Document` zamítnout přístup k revidované verzi dokumentu. Můžete nastavit hodnotu`RevisionsView`majetek do`RevisionsView.Final` zobrazit konečnou verzi bez revizí.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### Otázka: Jak mohu procházet revize dokumentů v Aspose.Words pro .NET?

A: Použijte a`foreach` smyčka pro iteraci revizí přítomných v dokumentu. Můžete použít`Revisions` majetek z`Document` objekt k získání kolekce všech revizí dokumentu.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Zde zpracujte každou revizi
}
```

#### Otázka: Jak zkontrolovat, zda je odstavec položkou seznamu v Aspose.Words pro .NET?

 A: Použijte`IsListItem` majetek z`Paragraph` objekt pro kontrolu, zda je odstavec položkou seznamu. The`IsListItem` majetkové výnosy`true` pokud je odstavec položkou seznamu, jinak se vrátí`false`.

```csharp
if (paragraph.IsListItem)
{
     // Odstavec je položka seznamu
}
else
{
     // Odstavec není položka seznamu
}
```