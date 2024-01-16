---
title: Commentaar opgelost en antwoorden
linktitle: Commentaar opgelost en antwoorden
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u opmerkingen en hun antwoorden in Word-documenten kunt oplossen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-comments/comment-resolved-and-replies/
---

In deze uitgebreide zelfstudie leert u hoe u opmerkingen en hun antwoorden in een Word-document kunt oplossen met behulp van Aspose.Words voor .NET. Wij begeleiden u door het proces en voorzien u van de benodigde C#-codefragmenten. Aan het einde van deze handleiding kunt u de reactieresolutie beheren en de status van reacties en hun antwoorden bijwerken.

## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Aspose.Words voor .NET-bibliotheek geïnstalleerd op uw systeem.

## Stap 1: Laad het document en open opmerkingen
Laad om te beginnen het document dat de opmerkingen bevat met behulp van de klasse Document en open de verzameling opmerkingen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## Stap 2: Los opmerkingen en hun antwoorden op
Blader vervolgens door de opmerkingen en hun antwoorden om ze als opgelost te markeren:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

In de bovenstaande code hebben we toegang tot de bovenliggende opmerking en doorlopen we de antwoorden ervan. We kunnen de bovenliggende reactie-ID en de resolutiestatus ervan ophalen. Vervolgens werken we de markering 'Gereed' van elk reactieantwoord bij om de oplossing aan te geven.

## Stap 3: Sla het document op
Nadat u de opmerkingen hebt opgelost en hun status hebt bijgewerkt, slaat u het gewijzigde document op in een bestand met behulp van de Save-methode van de Document-klasse:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Voorbeeldbroncode voor het oplossen van opmerkingen en hun antwoorden met Aspose.Words voor .NET
Hier is de volledige broncode voor het oplossen van opmerkingen en hun antwoorden met Aspose.Words voor .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
Vergeet niet om de code aan te passen aan uw specifieke vereisten, inclusief het documentbestandspad en aanvullende aanpassingen

## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u opmerkingen en hun antwoorden in een Word-document kunt oplossen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u nu de reactieresolutie beheren en de status van reacties en hun antwoorden bijwerken volgens uw vereisten.

Het oplossen van opmerkingen helpt bij het volgen en beheren van feedback binnen een document. Experimenteer met verschillende commentaarstatussen en pas ze aan om de samenwerking en beoordelingsprocessen in uw documenten te verbeteren.

### Veelgestelde vragen

#### Vraag: Hoe los ik een opmerking op in Aspose.Words voor .NET?

 A: Om een opmerking in Aspose.Words voor .NET op te lossen, kunt u de`Comment.Resolve` methode die specificeert`Comment` object dat u wilt oplossen. Hierdoor wordt de opmerking als opgelost gemarkeerd en in het definitieve document verborgen.

#### Vraag: Hoe voeg ik een antwoord toe aan een opgeloste opmerking in Aspose.Words voor .NET?

 A: Hoewel opgeloste opmerkingen standaard verborgen zijn in het definitieve document, kunt u nog steeds een antwoord toevoegen aan een opgeloste opmerking met behulp van de`Comment.AddReply` methode die de antwoordtekst specificeert en waar u deze wilt toevoegen.

#### Vraag: Hoe bekijk ik opgeloste opmerkingen in Aspose.Words voor .NET?

 A: Standaard worden opgeloste opmerkingen verborgen in het definitieve document. U kunt ze echter wel weergeven met behulp van de`CommentOptions.ShowResolvedComments` eigendom van de`Document` object en stel het in`true`.

#### Vraag: Hoe kan ik alle opmerkingen, inclusief antwoorden, verbergen in Aspose.Words voor .NET?

 A: Om alle opmerkingen, inclusief antwoorden, in Aspose.Words voor .NET te verbergen, kunt u de`CommentOptions.CommentDisplayMode` eigendom van de`Document` object en stel het in`CommentDisplayMode.None`.

#### Vraag: Kan ik de tekst van een opgeloste opmerking in Aspose.Words voor .NET bewerken?

 A: Ja, u kunt de tekst van een opgeloste opmerking in Aspose.Words voor .NET bewerken door naar de`Comment.Text` eigendom van de corresponderende`Comment` object en wijzig de tekst indien nodig.