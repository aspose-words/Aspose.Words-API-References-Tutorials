---
title: Accepteer revisies
linktitle: Accepteer revisies
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u revisies van een Word-document accepteert met Aspose.Words voor .NET
type: docs
weight: 10
url: /nl/net/working-with-revisions/accept-revisions/
---

In deze zelfstudie begeleiden we u bij het accepteren van revisies van een Word-document met behulp van de functie Revisies accepteren van Aspose.Words voor .NET. Volg de onderstaande stappen om de broncode te begrijpen en wijzigingen in het document te accepteren.

## Stap 1: Documentinhoud toevoegen en bewerken

In dit voorbeeld maken we een document en voegen we inhoud toe. We gebruiken verschillende paragrafen om wijzigingen en herzieningen te illustreren. Hier is hoe:

```csharp
//Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Voeg tekst toe aan de eerste alinea en voeg vervolgens nog twee alinea's toe.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Stap 2: Houd beoordelingen bij en voeg beoordelingen toe

We schakelen het bijhouden van revisies in en voegen een revisie toe aan het document. Hier is hoe:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Deze paragraaf is een revisie en de bijbehorende vlag "IsInsertRevision" is ingesteld.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Stap 3: Verwijder een paragraaf en beheer revisies

We verwijderen een paragraaf en controleren op opgeslagen revisies. Hier is hoe:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Terwijl we revisies bijhouden, bestaat de alinea nog steeds in het document en is de vlag 'IsDeleteRevision' ingesteld
// en wordt als recensie in Microsoft Word weergegeven, totdat we alle recensies accepteren of afwijzen.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Stap 4: Accepteer wijzigingen

Wij accepteren alle wijzigingen in het document. Hier is hoe:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Stap 5: Stop met het bijhouden van beoordelingen

We stoppen met het bijhouden van revisies, zodat wijzigingen in het document niet langer als revisies worden weergegeven. Hier is hoe:

```csharp
doc.StopTrackRevisions();
```
## Stap 6: Het document opslaan

 Nadat u het tekstinvoerformulierveld hebt ingevoegd, slaat u het document op de gewenste locatie op met behulp van de`Save`methode. Zorg ervoor dat u het juiste bestandspad opgeeft:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Voorbeeldbroncode voor het accepteren van revisies met Aspose.Words voor .NET

Hier is de volledige broncode voor het accepteren van wijzigingen in een document met Aspose.Words voor .NET:


```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Voeg tekst toe aan de eerste alinea en voeg vervolgens nog twee alinea's toe.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//We hebben drie paragrafen, waarvan geen enkele als enige vorm van herziening is geregistreerd
// Als we inhoud aan het document toevoegen of verwijderen terwijl we revisies bijhouden,
// ze worden als zodanig in het document weergegeven en kunnen worden geaccepteerd/afgewezen.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Deze paragraaf is een revisie en de bijbehorende vlag "IsInsertRevision" is ingesteld.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Haal de alineaverzameling van het document op en verwijder een alinea.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Omdat we revisies bijhouden, bestaat de alinea nog steeds in het document en is de waarde "IsDeleteRevision" ingesteld
// en wordt als revisie in Microsoft Word weergegeven, totdat we alle revisies accepteren of afwijzen.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// De paragraaf 'Revisie verwijderen' wordt verwijderd zodra we de wijzigingen accepteren.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// Als u het bijhouden van revisies stopt, verschijnt deze tekst als normale tekst.
// Revisies worden niet meegeteld wanneer het document wordt gewijzigd.
doc.StopTrackRevisions();

// Bewaar het document.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Conclusie

In deze zelfstudie hebben we geleerd hoe u revisies in een Word-document kunt accepteren met behulp van de functie Revisies accepteren van Aspose.Words voor .NET. We hebben de stappen gevolgd om documentinhoud toe te voegen en te bewerken, revisies bij te houden, een herziene paragraaf te verwijderen, alle wijzigingen te accepteren en te stoppen met het bijhouden van revisies. Nu kunt u deze kennis toepassen om revisies in uw eigen Word-documenten effectief te beheren met Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag: Hoe schakel ik het bijhouden van revisies in Aspose.Words voor .NET in?

#### Oplossing 1:

 A: Om het bijhouden van revisies in Aspose.Words voor .NET in te schakelen, gebruikt u de`StartTrackRevisions` werkwijze van de`Document` object en specificeer de naam van de auteur en de startdatum voor het bijhouden van revisies.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Oplossing 2:

 A: U kunt het bijhouden van revisies ook inschakelen met behulp van de`Document` constructeur die accepteert`trackRevisions`En`author` parameters.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### Vraag: Hoe accepteer ik alle wijzigingen in een document met Aspose.Words voor .NET?

 EEN: Gebruik de`AcceptAllRevisions` werkwijze van de`Document` bezwaar maken tegen het accepteren van alle wijzigingen die in het document zijn aangebracht.

```csharp
doc.AcceptAllRevisions();
```

#### Vraag: Hoe bewaar ik een gewijzigd document met geaccepteerde revisies?

 Gebruik de`Save` werkwijze van de`Document` object om het gewijzigde document met geaccepteerde revisies op te slaan. Zorg ervoor dat u het juiste bestandspad opgeeft.

```csharp
doc.Save("path/to/the/document.docx");
```

#### Vraag: Hoe stop ik met het bijhouden van revisies in Aspose.Words voor .NET?

 EEN: Gebruik de`StopTrackRevisions` werkwijze van de`Document` bezwaar maken om het bijhouden van revisies te stoppen.

```csharp
doc.StopTrackRevisions();
```

#### Vraag: Hoe verwijder ik een herziene alinea in een document met Aspose.Words voor .NET?

 A: Om een herziene alinea uit een document te verwijderen, kunt u de`Remove` methode van het verzamelen van alinea's.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```