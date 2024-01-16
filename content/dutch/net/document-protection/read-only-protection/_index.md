---
title: Alleen-lezen-beveiliging in Word-document
linktitle: Alleen-lezen-beveiliging in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u uw alleen-lezen documenten in Word kunt beveiligen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/document-protection/read-only-protection/
---
In deze zelfstudie begeleiden we u bij de stappen voor het gebruik van de alleen-lezen-beveiligingsfunctie van Aspose.Words voor .NET. Met deze functie kunt u een Word-document alleen-lezen maken om ongeoorloofde wijzigingen te voorkomen. Volg onderstaande stappen:

## Stap 1: Het document maken en beveiliging toepassen

Begin met het maken van een exemplaar van de klasse Document en een DocumentBuilder-object:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Schrijf inhoud naar het document
Gebruik het DocumentBuilder-object om inhoud naar het document te schrijven:

```csharp
builder.Write("Open document as read-only");
```

## Stap 3: Stel het wachtwoord in en maak het document alleen-lezen

Stel een wachtwoord in voor het document met behulp van de eigenschap SetPassword() van het WriteProtection-object:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Zorg ervoor dat u "MyPassword" vervangt door het daadwerkelijke wachtwoord dat u wilt gebruiken.

## Stap 4: Alleen-lezen document toepassen

Maak het document alleen-lezen door de eigenschap ReadOnlyRecommended in te stellen op true:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Stap 5: Pas alleen-lezen-beveiliging toe en sla het document op

Pas ten slotte alleen-lezen-beveiliging toe met behulp van de Protect()-methode van het Document-object:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam opgeeft om het beveiligde document op te slaan.

### Voorbeeldbroncode voor alleen-lezen-beveiliging met Aspose.Words voor .NET

Hier is de volledige broncode voor alleen-lezen-beveiliging met Aspose.Words voor .NET:

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// Voer een wachtwoord in dat maximaal 15 tekens lang is.
doc.WriteProtection.SetPassword("MyPassword");

// Maak het document als alleen-lezen.
doc.WriteProtection.ReadOnlyRecommended = true;

// Pas schrijfbeveiliging toe als alleen-lezen.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Door deze stappen te volgen, kunt u uw documenten eenvoudig beschermen

## Conclusie

In deze zelfstudie hebben we de alleen-lezen-beveiligingsfunctie van Aspose.Words voor .NET onderzocht, waarmee u Word-documenten alleen-lezen kunt maken om ongeoorloofde wijzigingen te voorkomen. Door de aangegeven stappen te volgen, kunt u eenvoudig alleen-lezen-beveiliging op uw documenten toepassen en de beveiliging ervan verbeteren. Alleen-lezen-beveiliging helpt de integriteit en nauwkeurigheid van de inhoud van uw document te garanderen door de bewerkingsmogelijkheden te beperken. Aspose.Words voor .NET biedt een krachtige en flexibele API voor documentbeveiliging en ondersteunt diverse andere functies om uw Word-documenten aan te passen en te beveiligen.

### Veelgestelde vragen over alleen-lezen-beveiliging in Word-documenten

#### Vraag: Wat is alleen-lezen-beveiliging in Aspose.Words voor .NET?

A: Alleen-lezen-beveiliging in Aspose.Words voor .NET is een functie waarmee u een Word-document alleen-lezen kunt maken, waardoor ongeoorloofde wijzigingen worden voorkomen. Wanneer een document is ingesteld op alleen-lezen, kunnen gebruikers het document openen en bekijken, maar kunnen ze geen wijzigingen aanbrengen in de inhoud ervan.

#### Vraag: Hoe kan ik alleen-lezen-beveiliging toepassen op een Word-document met Aspose.Words voor .NET?

A: Om alleen-lezen-beveiliging toe te passen op een Word-document met Aspose.Words voor .NET, kunt u deze stappen volgen:
1.  Maak een exemplaar van de`Document` klasse en een`DocumentBuilder` voorwerp.
2.  Gebruik de`DocumentBuilder` om inhoud naar het document te schrijven.
3.  Stel een wachtwoord in voor het document met behulp van de`SetPassword` werkwijze van de`WriteProtection` voorwerp.
4.  Stel de`ReadOnlyRecommended` eigendom van de`WriteProtection` bezwaar tegen`true` om aan te bevelen het document als alleen-lezen te openen.
5.  Pas alleen-lezen-beveiliging toe met behulp van de`Protect` werkwijze van de`Document` object, met vermelding van de`ProtectionType` als`ReadOnly`.
6.  Sla het beveiligde document op met behulp van de`Save` werkwijze van de`Document` voorwerp.

#### Vraag: Kan ik de alleen-lezen-beveiliging van een Word-document verwijderen met Aspose.Words voor .NET?

A: Ja, u kunt de alleen-lezen-beveiliging van een Word-document verwijderen met Aspose.Words voor .NET. Om dit te doen, kunt u gebruik maken van de`Unprotect` werkwijze van de`Document` class, die alle bestaande bescherming van het document verwijdert.

#### Vraag: Kan ik een ander wachtwoord instellen voor alleen-lezen-beveiliging in een Word-document?

 A: Nee, dankzij de alleen-lezen-beveiliging in Aspose.Words voor .NET kunt u niet specifiek een apart wachtwoord instellen voor alleen-lezen-beveiliging. Het wachtwoord dat is ingesteld met behulp van de`SetPassword` werkwijze van de`WriteProtection` object is van toepassing op de algehele documentbeveiliging, inclusief zowel alleen-lezen- als lees-schrijfbeveiliging.

#### Vraag: Kunnen gebruikers de alleen-lezen-beveiliging in een Word-document omzeilen?

A: Alleen-lezen-beveiliging in een Word-document is bedoeld om onbedoelde of ongeoorloofde wijzigingen te ontmoedigen en te voorkomen. Hoewel het een beschermingsniveau biedt, kan het worden omzeild door gebruikers met voldoende technische kennis of bewerkingsrechten. Alleen-lezen-beveiliging dient echter als afschrikmiddel en helpt de integriteit van het document te behouden.