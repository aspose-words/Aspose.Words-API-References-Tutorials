---
title: Voeg Bidi-markeringen toe aan een Word-document
linktitle: Voeg Bidi-markeringen toe aan een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer in deze handleiding hoe u bidirectionele (Bidi) markeringen kunt toevoegen aan Word-documenten met behulp van Aspose.Words voor .NET. Zorg voor de juiste tekstrichting voor meertalige inhoud.
type: docs
weight: 10
url: /nl/net/programming-with-txtsaveoptions/add-bidi-marks/
---
## Invoering

In de wereld van documentverwerking kan bidirectionele (Bidi) tekst vaak lastig te beheren zijn. Dit geldt vooral als het gaat om talen met verschillende tekstrichtingen, zoals Arabisch of Hebreeuws. Gelukkig maakt Aspose.Words voor .NET het gemakkelijk om met dergelijke scenario's om te gaan. In deze zelfstudie laten we zien hoe u Bidi-markeringen aan een Word-document kunt toevoegen met Aspose.Words voor .NET.

## Vereisten

Voordat we in de code duiken, zorg ervoor dat je het volgende hebt:

1.  Aspose.Words voor .NET: Aspose.Words voor .NET moet geïnstalleerd zijn. Je kunt het downloaden van de[Aspose Downloads-pagina](https://releases.aspose.com/words/net/).
2. .NET Framework of .NET Core: Zorg ervoor dat u een compatibele .NET-omgeving hebt ingesteld voor het uitvoeren van de voorbeelden.
3. Basiskennis van C#: Bekendheid met de programmeertaal C# en basisbewerkingen in .NET.

## Naamruimten importeren

Om aan de slag te gaan, moet u de benodigde naamruimten importeren. Zo kunt u ze in uw project opnemen:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Laten we het proces van het toevoegen van Bidi-markeringen in een Word-document in duidelijke stappen opsplitsen. Bij elke stap wordt u door de code en het doel ervan geleid.

## Stap 1: Stel uw document in

 Begin met het maken van een nieuw exemplaar van het`Document` klasse en een`DocumentBuilder` om inhoud aan het document toe te voegen.

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Maak het document en voeg inhoud toe
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 In deze stap initialiseert u een nieuw Word-document en stelt u een`DocumentBuilder` om het invoegen van inhoud te vergemakkelijken.

## Stap 2: Voeg inhoud toe aan uw document

Voeg vervolgens wat tekst toe aan uw document. Hier voegen we tekst in verschillende talen toe om de verwerking van Bidi-teksten te illustreren.

```csharp
builder.Writeln("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder.Writeln("שלום עולם!");
builder.Writeln("مرحبا بالعالم!");
```

Hier voegen we eerst een standaard Engelse zin toe. Vervolgens schakelen we Bidi-tekstopmaak in voor de daaropvolgende tekst, die in het Hebreeuws en Arabisch is geschreven. Dit laat zien hoe u bidirectionele tekst kunt opnemen.

## Stap 3: Configureer de opslagopties voor Bidi-markeringen

 Om ervoor te zorgen dat de Bidi-markeringen correct in het document worden opgeslagen, moet u het`TxtSaveOptions` en schakel de`AddBidiMarks` keuze.

```csharp
// Voeg Bidi-markeringen toe
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

 In deze stap maken we een exemplaar van`TxtSaveOptions` en stel de`AddBidiMarks`eigendom aan`true`. Dit zorgt ervoor dat de Bidi-markeringen worden meegenomen bij het opslaan van het document als tekstbestand.

## Conclusie

Het toevoegen van Bidi-markeringen aan uw Word-documenten kan een cruciale stap zijn bij het omgaan met meertalige inhoud die talen met verschillende tekstrichtingen omvat. Met Aspose.Words voor .NET is dit proces eenvoudig en efficiënt. Door de hierboven beschreven stappen te volgen, kunt u ervoor zorgen dat uw documenten de Bidi-tekst correct weergeven, waardoor de leesbaarheid en nauwkeurigheid worden verbeterd.

## Veelgestelde vragen

### Wat zijn Bidi-merken en waarom zijn ze belangrijk?
Bidi-markeringen zijn speciale tekens die worden gebruikt om de richting van tekst in documenten te bepalen. Ze zijn essentieel voor het correct weergeven van talen die van rechts naar links lezen, zoals Arabisch en Hebreeuws.

### Kan ik Aspose.Words voor .NET gebruiken om andere soorten problemen met de tekstrichting op te lossen?
Ja, Aspose.Words voor .NET biedt uitgebreide ondersteuning voor verschillende behoeften op het gebied van tekstrichting en opmaak, inclusief talen van rechts naar links en van links naar rechts.

### Is het mogelijk om Bidi-opmaak alleen op specifieke delen van een document toe te passen?
Ja, u kunt indien nodig Bidi-opmaak toepassen op specifieke alinea's of secties van uw document.

### In welke formaten kan ik het document opslaan met Bidi-markeringen?
In het gegeven voorbeeld wordt het document opgeslagen als een tekstbestand. Aspose.Words ondersteunt echter ook het opslaan van documenten in verschillende formaten met behoud van Bidi-markeringen.

### Waar kan ik meer informatie vinden over Aspose.Words voor .NET?
 U kunt meer te weten komen over Aspose.Words voor .NET via de[Aspose-documentatie](https://reference.aspose.com/words/net/) en toegang krijgen tot de[Helpforum](https://forum.aspose.com/c/words/8) voor extra hulp.