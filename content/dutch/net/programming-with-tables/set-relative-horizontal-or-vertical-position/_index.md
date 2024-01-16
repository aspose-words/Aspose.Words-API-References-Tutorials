---
title: Stel de relatieve horizontale of verticale positie in
linktitle: Stel de relatieve horizontale of verticale positie in
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de relatieve horizontale of verticale positie van een tabel in een Word-document instelt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

In deze zelfstudie leren we hoe u de relatieve horizontale of verticale positie van een tabel in een Word-document kunt instellen met behulp van Aspose.Words voor .NET. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u de relatieve horizontale of verticale positie van uw tabel in uw Word-documenten instellen.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document laden
Volg deze stappen om de tekstverwerking met het document te starten:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap en geef de juiste bestandsnaam op.

## Stap 3: De relatieve positie van de tafel instellen
Vervolgens stellen we de relatieve horizontale of verticale positie van de tabel in. Gebruik de volgende code:

```csharp
// Haal de tabel op
Table table = doc.FirstSection.Body.Tables[0];

//Definitie van de relatieve horizontale positie van de tafel
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Definieer de relatieve verticale positie van de tabel
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Hier gebruiken we het document om de eerste tabel uit de hoofdtekst van de eerste sectie op te halen. Vervolgens stellen we de relatieve horizontale positie van de tafel in met de`HorizontalAnchor` eigendom met behulp van de`RelativeHorizontalPosition.Column` waarde. Op dezelfde manier stellen we de relatieve verticale positie van de tafel in met de`VerticalAnchor` eigendom met behulp van de`RelativeVerticalPosition.Page` waarde.

## Stap 4: Het gewijzigde document opslaan
Ten slotte moeten we het gewijzigde document opslaan met de relatieve positie van de tabel gedefinieerd. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.

### Voorbeeldbroncode voor het instellen van relatieve horizontale of verticale positie met Aspose.Words voor .NET 

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u de relatieve horizontale of verticale positie van een tabel in een Word-document kunt instellen met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u deze relatieve positie toepassen op uw tabellen in uw Word-documenten.