---
title: Versleutel document met wachtwoord
linktitle: Versleutel document met wachtwoord
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u documenten met een wachtwoord kunt coderen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
Documentbeveiliging is essentieel bij het verwerken van woorden met bestanden in een C#-toepassing. Met de Aspose.Words-bibliotheek voor .NET kunt u uw documenten eenvoudig beveiligen door ze met een wachtwoord te coderen. In deze stapsgewijze handleiding laten we u zien hoe u Aspose.Words voor .NET C#-broncode kunt gebruiken om een document te coderen met behulp van de DocSaveOptions-opslagopties.

## Inzicht in de Aspose.Words-bibliotheek

Voordat u in de code duikt, is het belangrijk dat u de Aspose.Words-bibliotheek voor .NET begrijpt. Aspose.Words is een krachtige bibliotheek voor het maken, bewerken, converteren en beschermen van Word-documenten op verschillende platforms, waaronder .NET. Het biedt veel functies voor het manipuleren van documenten, zoals het invoegen van tekst, het wijzigen van de opmaak, het toevoegen van secties en nog veel meer.

## Stap 1: De documentmap definiëren

De eerste stap is het instellen van de map waarin u het gecodeerde document wilt opslaan. U moet het volledige mappad opgeven. Bijvoorbeeld :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 2: Een document maken en bewerken

Vervolgens kunt u een document maken en er inhoud aan toevoegen. Gebruik de klasse DocumentBuilder van Aspose.Words om de inhoud van uw document op te bouwen. Bijvoorbeeld :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

In dit voorbeeld maken we een nieuw leeg document en gebruiken we DocumentBuilder om de tekst "Hallo wereld!" te schrijven.

## Stap 3: Configureer opnameopties

Laten we nu de opslagopties voor ons document configureren. Gebruik de klasse DocSaveOptions om opslaginstellingen op te geven. Bijvoorbeeld :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

In dit voorbeeld maken we een nieuw DocSaveOptions-object en stellen we de eigenschap Wachtwoord in op "wachtwoord" om het document met dit wachtwoord te coderen.

## Stap 4: De functie "Document coderen met wachtwoord" inschakelen

We hebben de opties al geconfigureerd voor

registratie met het opgegeven wachtwoord, waardoor automatisch de functie "Document coderen met wachtwoord" wordt geactiveerd. Dit zorgt ervoor dat het document wordt gecodeerd met het wachtwoord dat is opgegeven toen het werd opgeslagen.

## Stap 5: Het document opslaan

Ten slotte kunt u het document opslaan met de Save-methode van de Document-klasse. Geef het volledige pad naar het bestand en de gewenste bestandsnaam op. Bijvoorbeeld :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

Zorg ervoor dat u "dataDir" vervangt door het mappad naar uw documenten.

### Voorbeeldbroncode voor DocSaveOptions-opslagopties met de functionaliteit "Document coderen met wachtwoord" met behulp van Aspose.Words voor .NET

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Een document maken en bewerken
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

// Configureer de opslagopties met de functie "Document coderen met wachtwoord".
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

// Sla het document op met de opgegeven opties
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## Conclusie

In deze handleiding hebben we uitgelegd hoe u de Aspose.Words-bibliotheek voor .NET kunt gebruiken om een document met een wachtwoord te coderen met behulp van de DocSaveOptions-opslagopties. Door de meegeleverde stappen te volgen en de meegeleverde C#-broncode te gebruiken, kunt u deze functionaliteit eenvoudig toepassen in uw C#-applicatie. Het coderen van het document met een wachtwoord garandeert de vertrouwelijkheid en veiligheid ervan bij de verwerking ervan.