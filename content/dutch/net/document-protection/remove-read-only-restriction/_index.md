---
title: Verwijder de alleen-lezenbeperking
linktitle: Verwijder de alleen-lezenbeperking
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de alleen-lezenbeperking uit een Word-document verwijdert met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/document-protection/remove-read-only-restriction/
---
In deze zelfstudie leiden we u door de stappen om Aspose.Words te gebruiken voor het verwijderen van de functie voor het verwijderen van alleen-lezen beperkingen in .NET. Met deze functie kunt u de alleen-lezenbeperking van een Word-document verwijderen om het bewerkbaar te maken. Volg onderstaande stappen:

## Stap 1: Het document aanmaken en de beveiliging instellen

Begin met het maken van een exemplaar van de klasse Document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Stel een wachtwoord in voor het document met behulp van de eigenschap SetPassword() van het WriteProtection-object:

Zorg ervoor dat u "MyPassword" vervangt door het daadwerkelijke wachtwoord dat u hebt gebruikt om het document te beveiligen.

## Stap 2: Verwijder de alleen-lezenbeperking

Als u de alleen-lezenbeperking wilt verwijderen, stelt u de eigenschap ReadOnlyRecommended in op false:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## Stap 3: Pas onbeperkte bescherming toe

Pas ten slotte onbeperkte beveiliging toe met behulp van de Protect()-methode van het Document-object:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam opgeeft om het document zonder de alleen-lezen-beperking op te slaan.

### Voorbeeldbroncode voor het verwijderen van de alleen-lezenbeperking met Aspose.Words voor .NET

Hier is de volledige broncode voor het verwijderen van de alleen-lezen-beperking met Aspose.Words voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

// Voer een wachtwoord in dat maximaal 15 tekens lang is.
doc.WriteProtection.SetPassword("MyPassword");

//Verwijder de alleen-lezen-optie.
doc.WriteProtection.ReadOnlyRecommended = false;

// Pas schrijfbeveiliging toe zonder enige beveiliging.
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Door deze stappen te volgen, kunt u eenvoudig de alleen-lezenbeperking van een Word-document verwijderen met Aspose.Words voor .NET.


## Conclusie

In deze zelfstudie hebben we geleerd hoe u de alleen-lezenbeperking uit een Word-document kunt verwijderen met behulp van Aspose.Words voor .NET. Door de aangegeven stappen te volgen, kunt u de beperking eenvoudig verwijderen en het document weer bewerkbaar maken. Aspose.Words voor .NET biedt een uitgebreide reeks functies voor het beheren van documentbeveiliging en -beperkingen, waardoor u flexibiliteit en controle krijgt over de beveiliging en bewerkingsmogelijkheden van uw Word-documenten.

### Veelgestelde vragen

#### Vraag: Wat is de alleen-lezenbeperking in Aspose.Words voor .NET?

A: De alleen-lezenbeperking in Aspose.Words voor .NET verwijst naar een functie waarmee u een Word-document als alleen-lezen kunt instellen, zodat gebruikers geen wijzigingen kunnen aanbrengen in de inhoud of opmaak. Deze beperking helpt de integriteit van het document te beschermen en zorgt ervoor dat het niet per ongeluk of kwaadwillig wordt gewijzigd.

#### Vraag: Hoe kan ik de alleen-lezenbeperking verwijderen met Aspose.Words voor .NET?

A: Om de alleen-lezenbeperking uit een Word-document te verwijderen met behulp van Aspose.Words voor .NET, kunt u deze stappen volgen:
1.  Maak een exemplaar van de`Document` class en stel een wachtwoord in voor het document met behulp van de`SetPassword` werkwijze van de`WriteProtection` voorwerp.
2.  Stel de`ReadOnlyRecommended` eigendom van de`WriteProtection` bezwaar tegen`false` om de alleen-lezen aanbeveling te verwijderen.
3.  Pas onbeperkte bescherming toe op het document met behulp van de`Protect` werkwijze van de`Document` bezwaar maken met de`NoProtection` soort bescherming.
4.  Sla het document op zonder de alleen-lezen-beperking met behulp van de`Save` werkwijze van de`Document` voorwerp.

#### Vraag: Kan ik de alleen-lezenbeperking van een Word-document verwijderen zonder wachtwoord?

A: Nee, u kunt de alleen-lezenbeperking niet van een Word-document verwijderen zonder het juiste wachtwoord op te geven. De alleen-lezen-beperking is ingesteld om veiligheidsredenen, en het verwijderen ervan zonder het wachtwoord zou het doel van het beschermen van de integriteit van het document ondermijnen.

#### Vraag: Kan ik de alleen-lezenbeperking verwijderen van een Word-document met het verkeerde wachtwoord?

A: Nee, u kunt de alleen-lezen-beperking niet verwijderen van een Word-document met het verkeerde wachtwoord. Het juiste wachtwoord moet worden opgegeven om de alleen-lezenbeperking op te heffen en het document weer bewerkbaar te maken. Dit zorgt ervoor dat alleen geautoriseerde gebruikers met het juiste wachtwoord het document kunnen wijzigen.

#### Vraag: Is het mogelijk om andere typen documentbeveiliging te verwijderen met Aspose.Words voor .NET?

A: Ja, Aspose.Words voor .NET biedt verschillende methoden om andere soorten documentbeveiliging te verwijderen, zoals wachtwoordbeveiliging, formulierbeveiliging of beperkingen voor het bewerken van documenten. Afhankelijk van het type beveiliging dat op het document wordt toegepast, kunt u de overeenkomstige methoden en eigenschappen van Aspose.Words gebruiken om de specifieke beveiliging te verwijderen en het document bewerkbaar te maken.
