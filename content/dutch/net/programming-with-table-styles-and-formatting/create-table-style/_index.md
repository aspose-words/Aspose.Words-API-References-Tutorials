---
title: Tabelstijl maken
linktitle: Tabelstijl maken
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het maken van een aangepaste tabelstijl met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-table-styles-and-formatting/create-table-style/
---

In deze zelfstudie leiden we u stapsgewijs door het proces om een tabelstijl te maken met Aspose.Words voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze zelfstudie weet u hoe u een aangepaste stijl voor uw tabellen in uw Word-documenten kunt maken met Aspose.Words voor .NET.

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

## Stap 3: Start een nieuwe tabel en voeg cellen toe
Om te beginnen met het maken van de tabel, gebruiken we de`StartTable()` methode van de documentbouwer, vervolgens voegen we cellen aan de tabel toe met behulp van de`InsertCell()` methode en we schrijven de inhoud van de cellen naar de met behulp van de`Write()` methode.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## Stap 4: Maak een tabelstijl
 Nu kunnen we een tabelstijl maken met behulp van de`TableStyle` klasse en de`Add()` methode uit het document`s `Stijlencollectie. We definiëren de eigenschappen van de stijl, zoals randen, marges en opvullingen.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## Stap 5: Pas de tabelstijl toe op de tabel
 Ten slotte passen we de tabelstijl toe die we hebben gemaakt op de tabel met behulp van de`Style` eigendom van de tafel.

```csharp
table.Style = tableStyle;
```

## Stap 6: Sla het gewijzigde document op
Sla het gewijzigde document ten slotte op in een bestand. U kunt een geschikte naam en locatie voor het uitvoerdocument kiezen.

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

Gefeliciteerd! U hebt nu een aangepaste stijl voor uw tabel gemaakt met Aspose.Words voor .NET.

### Voorbeeldbroncode voor Tabelstijl maken met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een tabelstijl kunt maken met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen, kunt u eenvoudig de stijl van uw tabellen in uw Word-documenten aanpassen. Aspose.Words biedt een krachtige en flexibele API voor het manipuleren en opmaken van tabellen in uw documenten. Met deze kennis kunt u de visuele presentatie van uw Word-documenten verbeteren en aan specifieke behoeften voldoen.