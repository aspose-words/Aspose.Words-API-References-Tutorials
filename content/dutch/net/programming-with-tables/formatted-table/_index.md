---
title: Opgemaakte tabel
linktitle: Opgemaakte tabel
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u tabellen in Word-documenten kunt maken en opmaken met Aspose.Words voor .NET met deze gedetailleerde stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/programming-with-tables/formatted-table/
---
## Invoering

Het programmatisch maken en opmaken van tabellen in Word-documenten kan een hele klus lijken, maar met Aspose.Words voor .NET wordt het eenvoudig en beheersbaar. In deze zelfstudie laten we u zien hoe u een opgemaakte tabel in een Word-document kunt maken met Aspose.Words voor .NET. We behandelen alles, van het instellen van uw omgeving tot het opslaan van uw document met een prachtig opgemaakte tabel.

## Vereisten

Voordat we in de code duiken, zorgen we ervoor dat je alles hebt wat je nodig hebt:

1. Aspose.Words voor .NET Library: Download het van[hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: een IDE zoals Visual Studio.
3. .NET Framework: Zorg ervoor dat .NET Framework op uw computer is geïnstalleerd.

## Naamruimten importeren

Voordat u de daadwerkelijke code schrijft, moet u de benodigde naamruimten importeren:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Tables;
```

## Stap 1: Stel uw documentenmap in

Eerst moet u het pad definiëren waar uw document zal worden opgeslagen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad waar u het document wilt opslaan.

## Stap 2: Initialiseer het document en DocumentBuilder

Initialiseer nu een nieuw document en een DocumentBuilder-object.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 De`DocumentBuilder` is een helperklasse die het proces van het maken van documenten vereenvoudigt.

## Stap 3: Start de tabel

 Begin vervolgens met het maken van de tabel met behulp van de`StartTable` methode.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
```

Het invoegen van een cel is noodzakelijk om de tabel te starten.

## Stap 4: Pas tabelbrede opmaak toe

U kunt opmaak toepassen die van invloed is op de hele tabel. Als u bijvoorbeeld de linkerinspringing instelt:

```csharp
table.LeftIndent = 20.0;
```

## Stap 5: Formatteer de koprij

Stel de hoogte, uitlijning en andere eigenschappen voor de koprij in.

```csharp
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");
```

In deze stap zorgen we ervoor dat de koptekstrij opvalt door een achtergrondkleur, lettergrootte en uitlijning in te stellen.

## Stap 6: Voeg extra kopcellen in

Voeg meer cellen in voor de koprij:

```csharp
builder.InsertCell();
builder.Write("Header Row,\n Cell 2");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");
builder.EndRow();
```

## Stap 7: Formatteer de lichaamsrijen

Nadat u de koptekst heeft ingesteld, formatteert u de hoofdtekst van de tabel:

```csharp
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;
```

## Stap 8: Lichaamsrijen invoegen

Voeg de hoofdrijen met inhoud in:

```csharp
builder.InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Row 1, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 1, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 1, Cell 3 Content");
builder.EndRow();
```

Herhaal voor extra rijen:

```csharp
builder.InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Row 2, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 2, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 2, Cell 3 Content.");
builder.EndRow();
builder.EndTable();
```

## Stap 9: Sla het document op

Sla het document ten slotte op in de opgegeven map:

```csharp
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Hiermee wordt een Word-document met de opgemaakte tabel gemaakt en opgeslagen.

## Conclusie

En daar heb je het! Door deze stappen te volgen, kunt u met Aspose.Words voor .NET een goed opgemaakte tabel in een Word-document maken. Deze krachtige bibliotheek maakt het eenvoudig om Word-documenten programmatisch te manipuleren, waardoor u tijd en moeite bespaart.

## Veelgestelde vragen

### Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een krachtige bibliotheek voor het programmatisch maken, bewerken en converteren van Word-documenten.

### Kan ik verschillende kleuren gebruiken voor verschillende rijen?
Ja, u kunt verschillende opmaak, inclusief kleuren, toepassen op verschillende rijen of cellen.

### Is Aspose.Words voor .NET gratis?
 Aspose.Words voor .NET is een betaalde bibliotheek, maar je kunt ook een .NET-bibliotheek krijgen[gratis proefperiode](https://releases.aspose.com/).

### Hoe krijg ik ondersteuning voor Aspose.Words voor .NET?
 U kunt ondersteuning krijgen van de[Stel communityforums voor](https://forum.aspose.com/c/words/8).

### Kan ik andere soorten documenten maken met Aspose.Words voor .NET?
Ja, Aspose.Words voor .NET ondersteunt verschillende documentformaten, waaronder PDF, HTML en TXT.