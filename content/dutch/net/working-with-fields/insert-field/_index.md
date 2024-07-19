---
title: Veld invoegen
linktitle: Veld invoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een veld in uw Word-documenten kunt invoegen met Aspose.Words voor .NET. Personaliseer uw documenten met dynamische velden.
type: docs
weight: 10
url: /nl/net/working-with-fields/insert-field/
---

Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, die gebruikmaakt van de functie 'Een veld invoegen' van Aspose.Words voor .NET. Zorg ervoor dat u elke stap zorgvuldig volgt om de gewenste resultaten te krijgen.

## Stap 1: Documentmap instellen

In de verstrekte code moet u de directory van uw documenten opgeven. Vervang de waarde "UW DOCUMENTENMAP" door het juiste pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Het document en DocumentBuilder maken

We beginnen met het maken van een nieuw document en het initialiseren van een DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Het veld invoegen

 Wij gebruiken de`InsertField()` methode van de DocumentBuilder om een veld in het document in te voegen. In dit voorbeeld voegen we een samenvoegveld (MERGEFIELD) in met de veldnaam "MyFieldName" en het samenvoegformaat.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Voorbeeld van de broncode voor het invoegen van een veld met Aspose.Words voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Maak het document en de DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Voer het veld in.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

In dit voorbeeld hebben we een nieuw document gemaakt, een DocumentBuilder geïnitialiseerd en vervolgens een samenvoegveld ingevoegd met de veldnaam "MyFieldName" en de samenvoegindeling. Het document wordt vervolgens opgeslagen met een opgegeven bestandsnaam.

Dit concludeert onze gids over het gebruik van de functie "Een veld invoegen" met Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag: Wat is een veld in Word?

A: Een veld in Word is een element waarmee u dynamische gegevens in een document kunt invoegen en manipuleren. Het kan worden gebruikt om variabele informatie weer te geven, zoals datums, paginanummers, tabellen, wiskundige formules, enz.

#### Vraag: Hoe voeg ik een veld in een Word-document in?

A: Om een veld in een Word-document in te voegen, kunt u deze stappen volgen:

1. Plaats uw cursor op de plek waar u het veld wilt invoegen.
2. Ga naar het tabblad "Invoegen" in het lint.
3. Klik op de knop "Veld" in de groep "Tekst" om het dialoogvenster met velden te openen.
4. Selecteer het type veld dat u wilt invoegen in de vervolgkeuzelijst.
5. Configureer de veldopties indien nodig.
6. Klik op de knop "OK" om het veld in uw document in te voegen.

#### Vraag: Wat zijn de veelgebruikte veldtypen in Word?

A: Word biedt een grote verscheidenheid aan veldtypen die u in uw documenten kunt gebruiken. Hier volgen enkele veelgebruikte veldtypen:

- Datum en tijd: toont de huidige datum en tijd.
- Paginanummer: toont het huidige paginanummer.
- Inhoudsopgave: genereert automatisch een inhoudsopgave op basis van de stijlen van uw titels.
- Berekening: voert wiskundige berekeningen uit met behulp van formules.
- Vultekst: Genereert willekeurige tekst om uw document te vullen.

#### Vraag: Kan ik de weergave van velden in Word aanpassen?

A: Ja, u kunt het uiterlijk van velden in Word aanpassen met behulp van de beschikbare opmaakopties. U kunt bijvoorbeeld het lettertype, de grootte, de kleur en de stijl van tekst in een veld wijzigen. U kunt ook opmaakeffecten toepassen, zoals vet, cursief en onderstrepen.
  