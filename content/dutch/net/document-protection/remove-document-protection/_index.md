---
title: Documentbeveiliging verwijderen in Word-document
linktitle: Documentbeveiliging verwijderen in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de beveiliging in een Word-document kunt verwijderen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/document-protection/remove-document-protection/
---
In deze zelfstudie begeleiden we u bij de stappen voor het gebruik van de functie voor het opheffen van de beveiliging van documenten van Aspose.Words voor .NET. Met deze functie kunt u de beveiliging in een Word-document verwijderen, zodat het toegankelijk wordt voor verdere bewerking. Volg onderstaande stappen:

## Stap 1: Het document maken en inhoud toevoegen

Begin met het maken van een exemplaar van de klasse Document en een DocumentBuilder-object:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Voeg inhoud toe aan het document

Gebruik het DocumentBuilder-object om inhoud aan het document toe te voegen:

```csharp
builder.Writeln("Text added to a document.");
```

## Stap 3: Maak de beveiliging van het document ongedaan

Om de beveiliging van het document op te heffen, kunt u de methode Unprotect() van het Document-object gebruiken. U kunt ervoor kiezen om de beveiliging zonder wachtwoord of met het juiste wachtwoord te verwijderen. Wachtwoordloze beveiliging verwijderen:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

Zorg ervoor dat u "newPassword" vervangt door het juiste documentwachtwoord.

## Stap 4: Bewaar het document zonder bescherming

Sla het document ten slotte onbeveiligd op met behulp van de Save()-methode van het Document-object:

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam opgeeft om het document onbeschermd op te slaan.

### Voorbeeldbroncode voor Documentbeveiliging verwijderen met Aspose.Words voor .NET

Hier is de volledige broncode voor het opheffen van de beveiliging van het document met Aspose.Words voor .NET:

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Text added to a document.");

// De beveiliging van documenten kan worden verwijderd zonder wachtwoord, of met het juiste wachtwoord.
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");

doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

Door deze stappen te volgen, kunt u eenvoudig de beveiliging van een Word-document verwijderen met Aspose.Words voor .NET.

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u documentbeveiliging in een Word-document kunt verwijderen met Aspose.Words voor .NET. Door de aangegeven stappen te volgen, kunt u de beveiliging van een document eenvoudig opheffen en toegankelijk maken voor verdere bewerking. Aspose.Words voor .NET biedt een krachtige API waarmee u de instellingen voor documentbeveiliging kunt manipuleren en het beveiligingsniveau voor uw Word-documenten kunt aanpassen. Door de documentbeveiliging te verwijderen, beschikt u over de flexibiliteit om de inhoud en opmaak van het document indien nodig aan te passen.

### Veelgestelde vragen over het verwijderen van documentbeveiliging in een Word-document

#### Vraag: Wat is documentbeveiliging in Aspose.Words voor .NET?

A: Documentbeveiliging in Aspose.Words voor .NET verwijst naar de functie waarmee u beveiligingsmaatregelen op een Word-document kunt toepassen om bewerking, opmaak en inhoudswijzigingen te beperken. Het helpt de integriteit en vertrouwelijkheid van het document te garanderen.

#### Vraag: Hoe kan ik documentbeveiliging verwijderen met Aspose.Words voor .NET?

A: Om documentbeveiliging te verwijderen met Aspose.Words voor .NET, kunt u deze stappen volgen:
1.  Maak een exemplaar van de`Document` klasse en een`DocumentBuilder` voorwerp.
2.  Gebruik de`DocumentBuilder` om inhoud aan het document toe te voegen.
3.  Bel de`Unprotect` werkwijze van de`Document` bezwaar maken tegen het verwijderen van eventuele bestaande beveiliging van het document. Dit kan zonder wachtwoord of door het juiste wachtwoord op te geven.
4.  Sla het onbeveiligde document op met behulp van de`Save` werkwijze van de`Document` voorwerp.

#### Vraag: Kan ik de beveiliging van een Word-document verwijderen zonder wachtwoord?

 A: Ja, u kunt de beveiliging van een Word-document zonder wachtwoord verwijderen met Aspose.Words voor .NET. Door te bellen met de`Unprotect` werkwijze van de`Document`object zonder een wachtwoord op te geven, kunt u de beveiliging van het document verwijderen als het eerder zonder wachtwoord was beveiligd.

#### Vraag: Hoe kan ik de beveiliging van een Word-document verwijderen met een wachtwoord?

 A: Als u de beveiliging wilt opheffen van een Word-document dat is beveiligd met een wachtwoord, moet u het juiste wachtwoord opgeven wanneer u de`Unprotect` werkwijze van de`Document` voorwerp. Dit zorgt ervoor dat alleen gebruikers met het juiste wachtwoord de beveiliging kunnen opheffen en toegang kunnen krijgen tot het document om het te bewerken.

#### Vraag: Kan ik specifieke beveiligingstypen uit een Word-document verwijderen?

 A: Ja, met Aspose.Words voor .NET kunt u selectief specifieke beveiligingstypen uit een Word-document verwijderen. Door te bellen met de`Unprotect` werkwijze van de`Document` object, kunt u het gewenste beveiligingstype verwijderen, zoals alleen-lezen-beveiliging of formulierbeveiliging, terwijl andere beveiligingstypen intact blijven.