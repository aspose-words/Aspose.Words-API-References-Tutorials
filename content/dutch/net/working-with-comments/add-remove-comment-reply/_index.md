---
title: Voeg commentaar toe Antwoord verwijderen
linktitle: Voeg commentaar toe Antwoord verwijderen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u reactiereacties in Word-documenten kunt toevoegen en verwijderen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-comments/add-remove-comment-reply/
---

In deze uitgebreide zelfstudie leert u hoe u reactiereacties in een Word-document kunt toevoegen en verwijderen met behulp van Aspose.Words voor .NET. Wij begeleiden u door het proces en voorzien u van de benodigde C#-codefragmenten. Aan het einde van deze handleiding kunt u reacties op reacties beheren en aanpassen aan uw vereisten.

## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Aspose.Words voor .NET-bibliotheek geïnstalleerd op uw systeem.

## Stap 1: Laad het document
Laad om te beginnen het document dat de opmerkingen bevat met behulp van de klasse Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## Stap 2: Open de opmerking en beheer antwoorden
Open vervolgens de opmerking uit het document met behulp van de GetChild-methode met de parameter NodeType.Comment:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

Om een antwoord uit de opmerking te verwijderen, gebruikt u de RemoveReply-methode en geeft u de gewenste antwoordindex op:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

Om een nieuw antwoord aan de opmerking toe te voegen, gebruikt u de AddReply-methode en geeft u de naam van de auteur, de initialen van de auteur, de datum en tijd en de antwoordtekst op:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## Stap 3: Sla het document op
Nadat u commentaarantwoorden hebt toegevoegd of verwijderd, slaat u het document op in een bestand met behulp van de Save-methode van de Document-klasse:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Voorbeeldbroncode voor het toevoegen en verwijderen van reacties met Aspose.Words voor .NET
Hier is de volledige broncode voor het toevoegen en verwijderen van commentaarantwoorden met Aspose.Words voor .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u reactieantwoorden in een Word-document kunt toevoegen en verwijderen met behulp van Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u nu reacties op reacties beheren en aanpassen aan uw vereisten.

Reactieantwoorden maken gezamenlijke discussies en feedback binnen een document mogelijk. Experimenteer met verschillende antwoordauteurs, initialen, datums en teksten om de samenwerking en communicatie binnen uw documenten te verbeteren.

### Veelgestelde vragen

#### Vraag: Hoe kan ik een opmerking toevoegen in Aspose.Words voor .NET?

 A: Om commentaar toe te voegen in Aspose.Words voor .NET, kunt u de`Comment.AddComment` methode die de tekst van de opmerking specificeert en waar u deze in het document wilt toevoegen.

#### Vraag: Hoe kan ik een opmerking verwijderen in Aspose.Words voor .NET?

 A: Om een opmerking in Aspose.Words voor .NET te verwijderen, kunt u de`Comment.Remove` methode die specificeert`Comment` object dat u wilt verwijderen.

#### Vraag: Kan ik reageren op een opmerking in Aspose.Words voor .NET?

 A: Ja, u kunt reageren op een opmerking in Aspose.Words voor .NET met behulp van de`Comment.AddReply` methode die de antwoordtekst specificeert en waar u deze in het document wilt toevoegen.

#### Vraag: Hoe krijg ik toegang tot bestaande opmerkingen in Aspose.Words voor .NET?

 A: U kunt toegang krijgen tot bestaande opmerkingen in Aspose.Words voor .NET met behulp van de`CommentCollection` eigendom van de`Document`voorwerp. Hiermee kunt u door alle opmerkingen in het document bladeren.

#### Vraag: Kan ik commentaartekst bewerken in Aspose.Words voor .NET?

 A: Ja, u kunt de tekst van een opmerking in Aspose.Words voor .NET bewerken door naar de`Comment.Text` eigendom van de corresponderende`Comment` object en wijzig de tekst indien nodig.