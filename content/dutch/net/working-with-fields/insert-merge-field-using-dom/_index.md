---
title: Samenvoegveld invoegen met DOM
linktitle: Samenvoegveld invoegen met DOM
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u samenvoegvelden in Word-documenten invoegt en configureert met Aspose.Words voor .NET met deze uitgebreide, stapsgewijze zelfstudie.
type: docs
weight: 10
url: /nl/net/working-with-fields/insert-merge-field-using-dom/
---

Als u met documentverwerking in .NET werkt, bent u waarschijnlijk Aspose.Words tegengekomen. Deze krachtige bibliotheek biedt een breed scala aan functies voor het programmatisch manipuleren van Word-documenten. In deze zelfstudie concentreren we ons op één specifieke functie: het invoegen van een samenvoegveld met behulp van het Document Object Model (DOM) in Aspose.Words voor .NET. Deze handleiding begeleidt u bij elke stap, van het opzetten van uw omgeving tot het invoegen en bijwerken van een samenvoegveld in een Word-document.

## Vereisten

Voordat we in de code duiken, zorgen we ervoor dat je alles hebt wat je nodig hebt om deze tutorial te volgen.

1. **Basic Knowledge of C#:** Je moet vertrouwd zijn met programmeren in C#.
2. **Visual Studio Installed:** Zorg ervoor dat Visual Studio of een andere C# IDE op uw computer is geïnstalleerd.
3. **Aspose.Words for .NET:** Download en installeer de nieuwste versie van Aspose.Words voor .NET vanaf de[Releases](https://releases.aspose.com/words/net/).
4. **Valid License:** Als u geen vergunning heeft, kunt u een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) voor evaluatie.

## Stap 1: Stel uw project in

Laten we eerst een nieuw project opzetten in Visual Studio.

1. **Open Visual Studio.**
2. **Create a New Project:** Ga naar Bestand > Nieuw > Project. Selecteer een C# Console-app.
3. **Name Your Project:** Geef uw project een betekenisvolle naam en klik op Maken.

## Stap 2: Installeer Aspose.Words

Om Aspose.Words te gebruiken, moet u het aan uw project toevoegen. Dit kan gedaan worden via NuGet Package Manager.

1. **Open NuGet Package Manager:** Klik met de rechtermuisknop op uw project in de Solution Explorer en selecteer vervolgens NuGet-pakketten beheren.
2. **Search for Aspose.Words:** Zoek in NuGet Package Manager naar "Aspose.Words".
3. **Install the Package:** Klik op Installeren om Aspose.Words aan uw project toe te voegen.

## Stap 3: Naamruimten importeren

Om Aspose.Words te gaan gebruiken, moet u de benodigde naamruimten in uw project importeren. Hier ziet u hoe u het kunt doen:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

## Stap 4: Initialiseer uw document

Nu alles is ingesteld, gaan we een nieuw Word-document maken en de DocumentBuilder initialiseren.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Maak het document en de DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 5: Verplaats de cursor naar een specifieke paragraaf

Vervolgens moeten we de cursor naar een specifieke paragraaf in het document verplaatsen waar we het samenvoegveld willen invoegen.

```csharp
// Cursor naar alinea verplaatsen.
builder.MoveToParagraph(2, 0);
```

## Stap 6: Voeg het samenvoegveld in

 Het invoegen van een samenvoegveld is eenvoudig. Wij zullen gebruik maken van de`InsertField` werkwijze van de`DocumentBuilder` klas.

```csharp
// Veldsamenvoegveld invoegen.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

## Stap 7: Configureer het samenvoegveld

Nadat u het samenvoegveld hebt ingevoegd, kunt u verschillende eigenschappen instellen om het naar uw wensen te configureren.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field.TextAfter = "Test3";
field.IsMapped = true;
field.IsVerticalFormatting = true;
```

## Stap 8: Werk het document bij en sla het op

Werk ten slotte het veld bij om ervoor te zorgen dat alle instellingen worden toegepast en sla het document op.

```csharp
// Werk het veld bij.
field.Update();

// Bewaar het document.
doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

## Conclusie

Door deze stappen te volgen, kunt u eenvoudig samenvoegvelden in een Word-document invoegen en configureren met behulp van Aspose.Words voor .NET. In deze zelfstudie werden de essentiële stappen behandeld, vanaf het instellen van uw omgeving tot het opslaan van het definitieve document. Met Aspose.Words kunt u complexe documentverwerkingstaken automatiseren, waardoor uw .NET-applicaties krachtiger en efficiënter worden.

## Veelgestelde vragen

### 1. Wat is een samenvoegveld?
Een samenvoegveld is een tijdelijke aanduiding in een document die dynamisch kan worden vervangen door gegevens uit een gegevensbron, zoals een database of een CSV-bestand.

### 2. Kan ik Aspose.Words gratis gebruiken?
 Aspose.Words biedt een gratis proefversie die u kunt downloaden[hier](https://releases.aspose.com/). Voor langdurig gebruik moet u een licentie aanschaffen.

### 3. Hoe krijg ik een tijdelijke licentie voor Aspose.Words?
 U kunt een tijdelijke licentie verkrijgen via de Aspose-website[hier](https://purchase.aspose.com/temporary-license/).

### 4. Welke versies van .NET worden ondersteund door Aspose.Words?
Aspose.Words ondersteunt meerdere versies van .NET, waaronder .NET Framework, .NET Core en .NET Standard.

### 5. Waar kan ik de API-documentatie voor Aspose.Words vinden?
 De API-documentatie is beschikbaar[hier](https://reference.aspose.com/words/net/).