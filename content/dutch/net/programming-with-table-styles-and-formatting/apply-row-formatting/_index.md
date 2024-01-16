---
title: Rijopmaak toepassen
linktitle: Rijopmaak toepassen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het toepassen van rijopmaak op een tabel met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

In deze zelfstudie leiden we u stapsgewijs door het proces om rijopmaak toe te passen op een tabel met behulp van Aspose.Words voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze zelfstudie heeft u een duidelijk inzicht in de manier waarop u tabelrijen in uw Word-documenten kunt opmaken met Aspose.Words voor .NET.

## Stap 1: Definieer de documentmap
Eerst moet u het pad naar uw documentenmap instellen. Dit is de locatie waar u uw bewerkte Word-document wilt opslaan. Vervang "UW DOCUMENTENDIRECTORY" door het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Maak een nieuw document en een documentbuilder
 Vervolgens moet u een nieuw exemplaar van de`Document` klasse en een documentconstructor voor dat document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Start een nieuw bord
 Om rijopmaak toe te passen, moeten we eerst een nieuwe tabel starten met behulp van de`StartTable()` methode van de documentconstructor.

```csharp
Table table = builder. StartTable();
```

## Stap 4: Cel invoegen en naar rijopmaak gaan
Nu kunnen we een cel in de tabel invoegen en toegang krijgen tot de rijopmaak voor die cel met behulp van de documentbouwer`InsertCell()` En`RowFormat` methoden.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## Stap 5: Stel de rijhoogte in
 Om de rijhoogte in te stellen, gebruiken we de`Height` En`HeightRule` eigenschappen van het rijformaat. In dit voorbeeld stellen we een rijhoogte van 100 punten in en gebruiken we de`Exactly` regel.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Stap 6: Definieer de tabelopmaak
 Sommige opmaakeigenschappen kunnen in de tabel zelf worden ingesteld en worden op alle tabelrijen toegepast. In dit voorbeeld stellen we de eigenschappen van de tabelmarge in met behulp van de`LeftPadding`, `RightPadding`, `TopPadding` En`BottomPadding` eigenschappen.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Stap 7: Voeg inhoud toe aan de rij
Nu kunnen we dat

 We gaan inhoud aan de regel toevoegen met behulp van de methoden van de documentconstructor. In dit voorbeeld gebruiken we de`Writeln()` methode om tekst aan de regel toe te voegen.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Stap 8: Maak de lijn en de tafel af
 Nadat we de inhoud aan de rij hebben toegevoegd, kunnen we de rij beëindigen met behulp van de`EndRow()` methode en beëindig vervolgens de tabel met behulp van de`EndTable()` methode.

```csharp
builder. EndRow();
builder. EndTable();
```

## Stap 9: Sla het gewijzigde document op
Ten slotte slaan we het gewijzigde document op in een bestand. U kunt een geschikte naam en locatie voor het uitvoerdocument kiezen.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

Gefeliciteerd! U hebt nu rijopmaak op een tabel toegepast met Aspose.Words voor .NET.

### Voorbeeldbroncode voor rijopmaak toepassen met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Deze opmaakeigenschappen worden ingesteld op de tabel en worden toegepast op alle rijen in de tabel.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u rijopmaak op een tabel kunt toepassen met behulp van Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen, kunt u deze functionaliteit eenvoudig integreren in uw C#-projecten. Het manipuleren van de opmaak van tabelrijen is een essentieel aspect van documentverwerking, en Aspose.Words biedt een krachtige en flexibele API om dit te bereiken. Met deze kennis kunt u de visuele presentatie van uw Word-documenten verbeteren en aan specifieke eisen voldoen.