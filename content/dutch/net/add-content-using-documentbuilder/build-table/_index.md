---
title: Tabel maken in Word-document
linktitle: Tabel maken in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een tabel in een Word-document kunt maken met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/add-content-using-documentbuilder/build-table/
---
In deze stapsgewijze zelfstudie leert u hoe u een tabel in een Word-document kunt bouwen met Aspose.Words voor .NET. Wij begeleiden u door het proces en voorzien u van de benodigde C#-codefragmenten. Aan het einde van deze handleiding kunt u een tabel maken met aangepaste opmaak en inhoud met behulp van de klasse DocumentBuilder.

## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Aspose.Words voor .NET-bibliotheek geïnstalleerd op uw systeem.

## Stap 1: Maak een nieuw document
Maak om te beginnen een nieuw document met behulp van de Document-klasse:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Start de tabel
Gebruik vervolgens de StartTable-methode van de DocumentBuilder-klasse om te beginnen met het bouwen van de tabel:

```csharp
Table table = builder.StartTable();
```

## Stap 3: cellen invoegen en inhoud toevoegen
Nu kunt u cellen in de tabel invoegen en er inhoud aan toevoegen met behulp van de methoden InsertCell en Write van de klasse DocumentBuilder. Pas de celopmaak indien nodig aan:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Stap 4: Beëindig de rij
Nadat u inhoud aan de cellen van de eerste rij hebt toegevoegd, gebruikt u de EndRow-methode van de DocumentBuilder-klasse om de rij te beëindigen:

```csharp
builder.EndRow();
```

## Stap 5: Rijopmaak aanpassen
U kunt de opmaak van een rij aanpassen door de eigenschappen van de objecten RowFormat en CellFormat in te stellen:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Stap 6: Beëindig de tabel
Om de tabel te voltooien, gebruikt u de EndTable-methode van de DocumentBuilder-klasse:

```csharp
builder.EndTable();
```

### Voorbeeldbroncode voor het bouwen van een tabel met Aspose.Words voor .NET
Hier is de volledige broncode voor het bouwen van een tabel met Aspose.Words voor .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Conclusie
Gefeliciteerd! Je hebt met succes geleerd hoe je een tabel in een Word-document kunt bouwen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u nu tabellen met aangepaste opmaak maken.

### Veelgestelde vragen over het bouwen van een tabel in een Word-document

#### Vraag: Wat is Aspose.Words voor .NET?

A: Aspose.Words voor .NET is een krachtige bibliotheek voor documentverwerking waarmee ontwikkelaars Microsoft Word-documenten programmatisch kunnen maken, lezen, bewerken en converteren in .NET-toepassingen. Het biedt een breed scala aan functies om met Word-documenten te werken, zoals tekstmanipulatie, het maken van tabellen, documentbeveiliging, opmaak en meer.

#### Vraag: Hoe kan ik een tabel in een Word-document bouwen met Aspose.Words voor .NET?

A: Om een tabel in een Word-document te bouwen met Aspose.Words voor .NET, kunt u deze stappen volgen:
1.  Maak een nieuw exemplaar van de`Document` klasse en een`DocumentBuilder` voorwerp.
2.  Gebruik de`StartTable` werkwijze van de`DocumentBuilder`klas om te beginnen met het bouwen van de tafel.
3.  Voeg cellen in de tabel in en voeg inhoud toe met behulp van de`InsertCell` En`Write` methoden van de`DocumentBuilder` klas.
4.  Beëindig de rij met behulp van de`EndRow` werkwijze van de`DocumentBuilder` klas.
5.  Pas de rijopmaak aan door de eigenschappen van de`RowFormat` En`CellFormat` voorwerpen.
6.  Beëindig de tabel met behulp van de`EndTable` werkwijze van de`DocumentBuilder` klas.
7. Bewaar het document.

#### Vraag: Hoe kan ik de opmaak van de tabel en de cellen ervan aanpassen?

 A: U kunt de opmaak van de tabel en de cellen aanpassen door verschillende eigenschappen van de tabel in te stellen`RowFormat` En`CellFormat` voorwerpen. U kunt bijvoorbeeld de celuitlijning, de verticale en horizontale tekstrichting, celhoogte, rijhoogte en meer aanpassen. Door deze eigenschappen te gebruiken, kunt u het gewenste uiterlijk van de tabel en de inhoud ervan bereiken.

#### Vraag: Kan ik complexe tabellen bouwen met samengevoegde cellen en andere geavanceerde functies?

 A: Ja, Aspose.Words voor .NET biedt geavanceerde functies voor het bouwen van complexe tabellen, inclusief ondersteuning voor samengevoegde cellen, geneste tabellen en complexe tabelindelingen. U kunt gebruik maken van de`MergeCells` methode om cellen samen te voegen,`StartTable`methode om geneste tabellen te maken, en andere methoden om de gewenste tabelstructuur te bereiken.

#### Vraag: Is Aspose.Words voor .NET compatibel met verschillende Word-documentformaten?

A: Ja, Aspose.Words voor .NET is compatibel met verschillende Word-documentformaten, waaronder DOC, DOCX, RTF en meer. Het ondersteunt zowel oudere formaten (DOC) als moderne op XML gebaseerde formaten (DOCX) en stelt u in staat zonder problemen met documenten in verschillende formaten te werken.

#### Vraag: Waar kan ik meer informatie en documentatie vinden voor Aspose.Words voor .NET?

 A: U kunt uitgebreide documentatie en codevoorbeelden vinden op[API-referenties](https://reference.aspose.com/words/net/). De documentatie biedt gedetailleerde informatie over de functies van de bibliotheek en hoe u deze kunt gebruiken in uw .NET-toepassingen.