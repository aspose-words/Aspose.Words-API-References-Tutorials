---
title: Onbeperkte bewerkbare regio's in Word-document
linktitle: Onbeperkte bewerkbare regio's in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u onbeperkte bewerkbare gebieden in een Word-document kunt maken met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/document-protection/unrestricted-editable-regions/
---
In deze zelfstudie begeleiden we u bij de stappen om de functie voor onbeperkte bewerkbare gebieden van Aspose.Words voor .NET te gebruiken. Met deze functie kunt u gebieden in een Word-document definiëren waar de inhoud zonder beperkingen kan worden bewerkt, zelfs als de rest van het document alleen-lezen is. Volg onderstaande stappen:

## Stap 1: Het document laden en de beveiliging instellen

Begin met het laden van het bestaande document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Beveilig het document door het alleen-lezen beveiligingstype en wachtwoord in te stellen

## Stap 2: Een bewerkbaar gebied maken

Begin met het maken van een bewerkbaar gebied met behulp van de objecten EditableRangeStart en EditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Er wordt een EditableRange-object gemaakt voor de EditableRangeStart die we zojuist hebben gemaakt.
EditableRange editableRange = edRangeStart.EditableRange;

// Plaats iets binnen het bewerkbare bereik.
builder.Writeln("Paragraph inside first editable range");

// Een bewerkbaar bereik is goed gevormd als het een begin en een einde heeft.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## Stap 3: Voeg inhoud toe buiten de bewerkbare gebieden

U kunt inhoud toevoegen buiten de bewerkbare gebieden, die alleen-lezen blijft:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## Stap 4: Sla het document op

Sla ten slotte het gewijzigde document op:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam opgeeft om het document met bewerkbare gebieden op te slaan.

### Voorbeeldbroncode voor onbeperkte bewerkbare regio's met Aspose.Words voor .NET

Hier is de volledige broncode voor onbeperkt bewerkbare gebieden met Aspose.Words voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Upload een document en maak het alleen-lezen.
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

// Start een bewerkbaar bereik.
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Er wordt een EditableRange-object gemaakt voor de EditableRangeStart die we zojuist hebben gemaakt.
EditableRange editableRange = edRangeStart.EditableRange;

// Plaats iets binnen het bewerkbare bereik.
builder.Writeln("Paragraph inside first editable range");

// Een bewerkbaar bereik is goed gevormd als het een begin en een einde heeft.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
Door deze stappen te volgen, kunt u eenvoudig onbeperkte bewerkbare gebieden in uw Word-document maken met Aspose.Words voor .NET.

## Conclusie
In deze zelfstudie hebben we geleerd hoe u onbeperkt bewerkbare gebieden in een Word-document kunt maken met Aspose.Words voor .NET. Door de aangegeven stappen te volgen, kunt u specifieke gebieden binnen het document definiëren waar gebruikers de inhoud vrijelijk kunnen bewerken terwijl de rest van het document alleen-lezen blijft. Aspose.Words voor .NET biedt krachtige functies voor documentbeveiliging en aanpassing, waardoor u controle krijgt over de bewerkingsmogelijkheden van uw Word-documenten.

### Veelgestelde vragen over onbeperkt bewerkbare gebieden in een Word-document

#### Vraag: Wat zijn onbeperkte bewerkbare regio's in Aspose.Words voor .NET?

A: Onbeperkt bewerkbare gebieden in Aspose.Words voor .NET zijn gebieden binnen een Word-document waar de inhoud zonder enige beperking kan worden bewerkt, zelfs als de rest van het document is ingesteld als alleen-lezen. Deze gebieden bieden een manier om specifieke delen van het document te definiëren die gebruikers kunnen wijzigen, terwijl de algehele documentbeveiliging behouden blijft.

#### Vraag: Hoe kan ik onbeperkt bewerkbare regio's maken met Aspose.Words voor .NET?

A: Om onbeperkt bewerkbare gebieden in een Word-document te maken met Aspose.Words voor .NET, kunt u deze stappen volgen:
1.  Laad het bestaande document met behulp van de`Document` klas.
2.  Stel de documentbeveiliging in op alleen-lezen met behulp van de`Protect` werkwijze van de`Document` voorwerp.
3.  Gebruik de`DocumentBuilder` class om een bewerkbaar bereik te maken door een`EditableRangeStart` voorwerp en een`EditableRangeEnd` voorwerp.
4.  Voeg inhoud toe binnen het bewerkbare bereik met behulp van de`DocumentBuilder`.
5.  Sla het gewijzigde document op met behulp van de`Save` werkwijze van de`Document` voorwerp.

#### Vraag: Kan ik meerdere onbeperkte bewerkbare gebieden in een Word-document hebben?

A: Ja, u kunt meerdere onbeperkte bewerkbare gebieden in een Word-document hebben. Om dit te bereiken, kunt u meerdere sets maken`EditableRangeStart` En`EditableRangeEnd` objecten met behulp van de`DocumentBuilder` klas. Elke set objecten definieert een afzonderlijk bewerkbaar gebied waar gebruikers de inhoud zonder enige beperking kunnen wijzigen.

#### Vraag: Kan ik bewerkbare regio's in elkaar nesten?

 A: Nee, u kunt bewerkbare regio's niet in elkaar nesten met Aspose.Words voor .NET. Elk bewerkbaar gebied gedefinieerd door een`EditableRangeStart` En`EditableRangeEnd` Het paar moet onafhankelijk zijn en niet overlappen of genest zijn in een ander bewerkbaar gebied. Geneste bewerkbare regio's worden niet ondersteund.

#### Vraag: Kan ik de alleen-lezen-beveiliging van het document binnen een bewerkbaar gebied verwijderen?

A: Nee, u kunt de alleen-lezen-beveiliging niet verwijderen van het document binnen een bewerkbaar gebied. De alleen-lezen-beveiliging wordt toegepast op het gehele document en kan niet selectief worden verwijderd binnen specifieke bewerkbare gebieden. Het doel van de bewerkbare gebieden is om inhoudswijzigingen mogelijk te maken terwijl het gehele document alleen-lezen blijft.