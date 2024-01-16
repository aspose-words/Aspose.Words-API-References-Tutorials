---
title: Auteurveld invoegen
linktitle: Auteurveld invoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een AUTEUR-veld in uw Word-documenten invoegt met Aspose.Words voor .NET. Geef de naam van de auteur op om uw documenten te personaliseren.
type: docs
weight: 10
url: /nl/net/working-with-fields/insert-author-field/
---


Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, die gebruikmaakt van de functie "Insert an AUTHOR field" van Aspose.Words voor .NET. Zorg ervoor dat u elke stap zorgvuldig volgt om de gewenste resultaten te krijgen.

## Stap 1: Documentmap instellen

In de verstrekte code moet u de directory van uw documenten opgeven. Vervang de waarde "UW DOCUMENTENMAP" door het juiste pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Het document en de alinea maken

We beginnen met het maken van een nieuw document en het ophalen van de eerste alinea.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Stap 3: Voeg het AUTEUR-veld in

 Wij gebruiken de`AppendField()` methode om een AUTHOR-veld in de alinea in te voegen.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Vervolgens configureren we de velden`AuthorName` eigenschap om de naam van de auteur op te geven.

```csharp
field. AuthorName = "Test1";
```

 Tenslotte noemen wij de`Update()` methode om het veld bij te werken.

```csharp
field. Update();
```

### Voorbeeld van de broncode voor het invoegen van een AUTHOR-veld met Aspose.Words voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Documentcreatie.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Voeg het veld AUTEUR in.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

In dit voorbeeld hebben we een nieuw document gemaakt, een AUTEUR-veld ingevoegd, de auteursnaam geconfigureerd en het document opgeslagen met een opgegeven bestandsnaam.

Dit concludeert onze handleiding over het gebruik van de functie "AUTHOR Field invoegen" met Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag: Wat is een auteurveld in Aspose.Words?

A: Een auteursveld in Aspose.Words is een speciaal veld dat automatisch de naam van de auteur in een Word-document invoegt en bijwerkt. Het wordt vaak gebruikt om aan te geven wie het document heeft gemaakt of gewijzigd.

#### Vraag: Hoe kan ik het auteurveld in een Word-document bijwerken met Aspose.Words?

A: Het auteurveld in een Word-document kan worden bijgewerkt om de naam van de huidige auteur weer te geven. Hiervoor kunt u de UpdateFields-methode gebruiken die beschikbaar is in de Document-klasse. Met deze methode worden alle velden in het document bijgewerkt, inclusief het auteurveld.

#### Vraag: Is het mogelijk om de indeling van het auteurveld in een Word-document aan te passen?

A: Ja, het is mogelijk om de opmaak van het auteurveld in een Word-document aan te passen. Standaard wordt in het auteurveld eenvoudigweg de naam van de auteur weergegeven. U kunt echter aanvullende informatie toevoegen, zoals de datum en tijd van wijziging, met behulp van de opmaakopties die beschikbaar zijn in Aspose.Words.

#### Vraag: Is het auteurveld gevoelig voor latere wijzigingen in de naam van de auteur?

A: Ja, het auteurveld is gevoelig voor latere wijzigingen in de auteursnaam. Als u de auteursnaam in de documenteigenschappen wijzigt, wordt het auteurveld automatisch bijgewerkt met de nieuwe naam bij het bijwerken van documentvelden.