---
title: Horizontaal samenvoegen
linktitle: Horizontaal samenvoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u cellen in een Word-document horizontaal kunt samenvoegen met Aspose.Words voor .NET met deze gedetailleerde, stapsgewijze zelfstudie.
type: docs
weight: 10
url: /nl/net/programming-with-tables/horizontal-merge/
---
## Invoering

Hé daar! Klaar om in de wereld van Aspose.Words voor .NET te duiken? Vandaag gaan we een superhandige functie aanpakken: horizontaal samenvoegen van tabellen. Dit klinkt misschien een beetje technisch, maar maak je geen zorgen, ik sta achter je. Aan het einde van deze zelfstudie bent u een professional in het programmatisch samenvoegen van cellen in uw Word-documenten. Laten we dus onze mouwen opstropen en aan de slag gaan!

## Vereisten

Voordat we ingaan op de kern van de zaak, zijn er een paar dingen die je moet regelen:

1. Aspose.Words voor .NET-bibliotheek: Download de Aspose.Words voor .NET-bibliotheek als u dat nog niet heeft gedaan. Je kunt het pakken[hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: Zorg ervoor dat u over een geschikte ontwikkelomgeving beschikt, zoals Visual Studio.
3. Basiskennis van C#: Een basiskennis van programmeren in C# zal nuttig zijn.

Zodra je deze hebt gesorteerd, ben je helemaal klaar om te gaan!

## Naamruimten importeren

Voordat we in de code duiken, moeten we ervoor zorgen dat we de benodigde naamruimten hebben geïmporteerd. Zorg ervoor dat u in uw C#-project het volgende opneemt:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Oké, laten we het proces van het horizontaal samenvoegen van tabelcellen in een Word-document met Aspose.Words voor .NET eens nader bekijken.

## Stap 1: Uw document instellen

 Allereerst moeten we een nieuw Word-document maken en het`DocumentBuilder`:

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Met dit codefragment wordt een nieuw document opgezet en wordt het`DocumentBuilder` voor actie.

## Stap 2: De eerste cel invoegen

Vervolgens beginnen we met het invoegen van de eerste cel en markeren deze voor horizontaal samenvoegen:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
```

 Hier voegen we een nieuwe cel in en stellen deze in`HorizontalMerge`eigendom aan`CellMerge.First`, wat aangeeft dat deze cel het begin is van een samengevoegde celreeks.

## Stap 3: De samengevoegde cel invoegen

Nu voegen we de cel in die zal worden samengevoegd met de vorige:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
builder.EndRow();
```

 Deze cel is ingesteld om samen te voegen met de vorige cel met behulp van`CellMerge.Previous` . Merk op hoe we de rij eindigen met`builder.EndRow()`.

## Stap 4: Niet-samengevoegde cellen invoegen

Om het verschil te illustreren, voegen we een paar niet-samengevoegde cellen in:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in one cell.");
builder.InsertCell();
builder.Write("Text in another cell.");
builder.EndRow();
```

Hier voegen we twee cellen in zonder horizontale samenvoeging. Dit laat zien hoe cellen zich gedragen als ze geen deel uitmaken van een samengevoegde reeks.

## Stap 5: De tafel afmaken

Ten slotte beëindigen we de tabel en slaan we het document op:

```csharp
builder.EndTable();
doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

Met dit codefragment wordt de tabel voltooid en wordt het document in de opgegeven map opgeslagen.

## Conclusie

En daar heb je het! U beheerst zojuist de kunst van het horizontaal samenvoegen van cellen in een Word-document met Aspose.Words voor .NET. Door deze stappen te volgen, kunt u eenvoudig complexe tabelstructuren maken. Blijf experimenteren en ontdek de mogelijkheden van Aspose.Words om uw documenten zo dynamisch en flexibel te maken als u nodig heeft. Veel codeerplezier!

## Veelgestelde vragen

### Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een krachtige bibliotheek waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, bewerken en manipuleren in .NET-toepassingen.

### Kan ik cellen verticaal samenvoegen met Aspose.Words voor .NET?
 Ja, u kunt cellen ook verticaal samenvoegen met behulp van de`CellFormat.VerticalMerge` eigendom.

### Is Aspose.Words voor .NET gratis te gebruiken?
 Aspose.Words voor .NET biedt een gratis proefperiode, maar voor volledige functionaliteit moet u een licentie aanschaffen. U kunt een tijdelijke licentie krijgen[hier](https://purchase.aspose.com/temporary-license/).

### Hoe kan ik meer te weten komen over Aspose.Words voor .NET?
 U kunt de gedetailleerde documentatie verkennen[hier](https://reference.aspose.com/words/net/).

### Waar kan ik ondersteuning krijgen voor Aspose.Words voor .NET?
 Voor vragen of problemen kunt u het Aspose-ondersteuningsforum bezoeken[hier](https://forum.aspose.com/c/words/8).