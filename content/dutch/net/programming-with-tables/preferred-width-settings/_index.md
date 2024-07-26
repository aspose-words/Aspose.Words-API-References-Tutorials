---
title: Voorkeursbreedte-instellingen
linktitle: Voorkeursbreedte-instellingen
second_title: Aspose.Words-API voor documentverwerking
description: Leer met deze stapsgewijze handleiding hoe u tabellen kunt maken met absolute, relatieve en automatische breedte-instellingen in Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/preferred-width-settings/
---
## Invoering

Tabellen zijn een krachtige manier om informatie in uw Word-documenten te ordenen en presenteren. Wanneer u met tabellen werkt in Aspose.Words voor .NET, heeft u verschillende opties om de breedte van tabelcellen in te stellen, zodat deze perfect in de lay-out van uw document passen. Deze gids leidt u door het proces van het maken van tabellen met voorkeursbreedte-instellingen met behulp van Aspose.Words voor .NET, waarbij de nadruk ligt op absolute, relatieve en automatische formaatopties. 

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u over het volgende beschikt:

1.  Aspose.Words voor .NET: Zorg ervoor dat Aspose.Words voor .NET in uw ontwikkelomgeving is geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/words/net/).

2. .NET-ontwikkelomgeving: zorg dat u een .NET-ontwikkelomgeving hebt ingesteld, zoals Visual Studio.

3. Basiskennis van C#: Bekendheid met programmeren in C# zal u helpen de codefragmenten en voorbeelden beter te begrijpen.

4.  Aspose.Words Documentatie: Raadpleeg de[Aspose.Words-documentatie](https://reference.aspose.com/words/net/) voor gedetailleerde API-informatie en verder lezen.

## Naamruimten importeren

Voordat u begint met coderen, moet u de benodigde naamruimten in uw C#-project importeren:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Deze naamruimten bieden toegang tot de kernfunctionaliteiten van Aspose.Words en het Table-object, waardoor u documenttabellen kunt manipuleren.

Laten we het proces van het maken van een tabel met verschillende voorkeursbreedte-instellingen opsplitsen in duidelijke, beheersbare stappen.

## Stap 1: Initialiseer het document en DocumentBuilder

Kop: Een nieuw document maken en DocumentBuilder

 Uitleg: Begin met het maken van een nieuw Word-document en een`DocumentBuilder` voorbeeld. De`DocumentBuilder` class biedt een eenvoudige manier om inhoud aan uw document toe te voegen.

```csharp
// Definieer het pad om het document op te slaan.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Maak een nieuw document.
Document doc = new Document();

// Maak een DocumentBuilder voor dit document.
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Hier geeft u de map op waar het document zal worden opgeslagen en initialiseert u het`Document`En`DocumentBuilder` voorwerpen.

## Stap 2: Voeg de eerste tabelcel met absolute breedte in

Voeg de eerste cel in de tabel in met een vaste breedte van 40 punten. Dit zorgt ervoor dat deze cel altijd een breedte van 40 punten behoudt, ongeacht de tabelgrootte.

```csharp

// Voeg een cel van absolute grootte in.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell at 40 points width");
```

In deze stap begint u met het maken van de tabel en voegt u een cel met een absolute breedte in. De`PreferredWidth.FromPoints(40)` methode stelt de celbreedte in op 40 punten, en`Shading.BackgroundPatternColor` past een lichtgele achtergrondkleur toe.

## Stap 3: Voeg een cel van relatieve grootte in

Voeg nog een cel in met een breedte die 20% van de totale breedte van de tabel bedraagt. Deze relatieve grootte zorgt ervoor dat de cel zich proportioneel aanpast aan de breedte van de tabel.

```csharp
// Voeg een cel met relatieve grootte (percentage) in.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell at 20% width");
```

De breedte van deze cel bedraagt 20% van de totale breedte van de tabel, waardoor deze kan worden aangepast aan verschillende schermformaten of documentindelingen.

### Stap 4: Voeg een cel met automatische grootte in

Voeg ten slotte een cel in die zich automatisch aanpast aan de hand van de resterende beschikbare ruimte in de tabel.

```csharp
// Voeg een cel met automatische grootte in.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Cell automatically sized. The size of this cell is calculated from the table preferred width.");
builder.Writeln("In this case the cell will fill up the rest of the available space.");
```

 De`PreferredWidth.Auto` Met deze instelling kan deze cel uitzetten of inkrimpen op basis van de ruimte die overblijft nadat rekening is gehouden met de andere cellen. Hierdoor ziet de tafelindeling er evenwichtig en professioneel uit.

## Stap 5: Voltooi het document en sla het op

Nadat u al uw cellen heeft ingevoegd, voltooit u de tabel en slaat u het document op in het opgegeven pad.

```csharp
// Bewaar het document.
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Met deze stap wordt de tabel voltooid en wordt het document opgeslagen met de bestandsnaam "WorkingWithTables.PreferredWidthSettings.docx" in de door u aangegeven map.

## Conclusie

Het maken van tabellen met voorkeursbreedte-instellingen in Aspose.Words voor .NET is eenvoudig als u eenmaal de verschillende beschikbare formaatopties begrijpt. Of u nu vaste, relatieve of automatische celbreedtes nodig heeft, Aspose.Words biedt de flexibiliteit om verschillende tabelindelingsscenario's efficiënt af te handelen. Door de stappen in deze handleiding te volgen, kunt u ervoor zorgen dat uw tabellen goed gestructureerd en visueel aantrekkelijk zijn in uw Word-documenten.

## Veelgestelde vragen

### Wat is het verschil tussen absolute en relatieve celbreedtes?
Absolute celbreedtes staan vast en veranderen niet, terwijl relatieve breedtes worden aangepast op basis van de totale breedte van de tabel.

### Kan ik negatieve percentages gebruiken voor relatieve breedtes?
Nee, negatieve percentages zijn niet geldig voor celbreedtes. Alleen positieve percentages zijn toegestaan.

### Hoe werkt de functie voor automatisch aanpassen van de afmetingen?
Automatische grootte past de breedte van de cel aan om de resterende ruimte in de tabel op te vullen nadat de grootte van andere cellen is aangepast.

### Kan ik verschillende stijlen toepassen op cellen met verschillende breedte-instellingen?
Ja, u kunt verschillende stijlen en opmaak op cellen toepassen, ongeacht hun breedte-instellingen.

### Wat gebeurt er als de totale breedte van de tabel kleiner is dan de som van alle celbreedtes?
De tabel past automatisch de breedte van de cellen aan, zodat deze binnen de beschikbare ruimte past, waardoor sommige cellen kleiner kunnen worden.