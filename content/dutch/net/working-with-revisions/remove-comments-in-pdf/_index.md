---
title: Verwijder opmerkingen in pdf-bestand
linktitle: Verwijder opmerkingen in pdf-bestand
second_title: Aspose.Words-API voor documentverwerking
description: Verwijder opmerkingen in een PDF-bestand met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-revisions/remove-comments-in-pdf/
---

In deze stapsgewijze handleiding vertellen we u hoe u opmerkingen in een PDF-bestand kunt verwijderen met Aspose.Words voor .NET. We voorzien u van de volledige broncode en laten u zien hoe u de markdown-uitvoer kunt formatteren.

## Stap 1: Het document laden

De eerste stap is het laden van het document met de opmerkingen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Stap 2: Verberg opmerkingen in PDF

We zullen de lay-outoptie configureren om opmerkingen te verbergen bij het genereren van de PDF.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## Stap 3: Sla het document op als PDF

Ten slotte slaan we het document op in PDF-formaat door de opmerkingen te verwijderen.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Markdown-uitvoerformaten

De uitvoer kan in markdown worden opgemaakt om de leesbaarheid te verbeteren. Bijvoorbeeld :

```markdown
- Comments are hidden in the generated PDF.
```

### Voorbeeldbroncode voor het verwijderen van opmerkingen in pdf met Aspose.Words voor .NET

Hier is de volledige broncode om opmerkingen in een PDF-bestand te verwijderen met Aspose.Words voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Verberg opmerkingen in de PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u opmerkingen uit een PDF-bestand kunt verwijderen met Aspose.Words voor .NET. Door de juiste lay-outopties te gebruiken, konden we de opmerkingen verbergen bij het genereren van de PDF. Aspose.Words voor .NET biedt grote flexibiliteit om Word-bestanden te manipuleren en naar verschillende formaten te converteren, waaronder PDF. U kunt deze kennis nu toepassen om opmerkingen in uw eigen PDF-bestanden te verwijderen met Aspose.Words voor .NET.

### Veelgestelde vragen over het verwijderen van opmerkingen in pdf-bestanden

#### Vraag: Hoe upload ik een document in Aspose.Words voor .NET?

 EEN: Gebruik de`Document` klasse van Aspose.Words voor .NET om een document uit een bestand te laden. U kunt het volledige documentpad opgeven.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Vraag: Hoe kan ik opmerkingen verbergen in een PDF die is gegenereerd met Aspose.Words voor .NET?

 EEN: Gebruik de`CommentDisplayMode` eigendom van de`LayoutOptions` object om te configureren hoe opmerkingen worden weergegeven bij het genereren van de PDF. Als u opmerkingen wilt verbergen, stelt u deze eigenschap in op`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### Vraag: Hoe kan ik een document opslaan als PDF met Aspose.Words voor .NET?

 EEN: Gebruik de`Save` werkwijze van de`Document` object om het document in PDF-formaat op te slaan. Geef het volledige pad van het PDF-bestand op.

```csharp
doc.Save("path/to/the/file.pdf");
```