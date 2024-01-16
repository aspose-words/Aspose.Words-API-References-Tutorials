---
title: Exporteren naar prijsverlaging met uitlijning van tabelinhoud
linktitle: Exporteren naar prijsverlaging met uitlijning van tabelinhoud
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u tabelinhoud met verschillende uitlijningen naar Markdown-bestanden kunt exporteren met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Hier is een stapsgewijze handleiding om de volgende C#-broncode uit te leggen die helpt bij het exporteren van inhoud naar een Markdown-bestand met uitlijning van tabelinhoud met behulp van de Aspose.Words-bibliotheek voor .NET. Zorg ervoor dat u de Aspose.Words-bibliotheek in uw project hebt opgenomen voordat u deze code gebruikt.

## Stap 1: Stel het documentmappad in

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Zorg ervoor dat u het juiste pad opgeeft naar uw documentenmap waar het bewerkte document zal worden opgeslagen.

## Stap 2: Maak een document en een documentgenerator

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Hier maken we een exemplaar van de`Document` klasse en een exemplaar van de`DocumentBuilder` class waarmee we het document kunnen manipuleren en elementen kunnen toevoegen.

## Stap 3: Voeg cellen in de tabel in met verschillende alinea-uitlijningen

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

We gebruiken de Document Builder om cellen in de tabel in te voegen en voor elke cel verschillende alinea-uitlijningen in te stellen.

## Stap 4: Stel Markdown-exportopties in en sla het gewijzigde document op

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

We stellen de Markdown-exportopties in met verschillende uitlijningen van de tabelinhoud en slaan vervolgens het gewijzigde document op met elke uitlijningsoptie.

### Voorbeeldbroncode om naar Markdown te exporteren met uitlijning van tabelinhoud met behulp van Aspose.Words voor .NET

```csharp

            
	// Het pad naar de documentenmap.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// Zorgt ervoor dat alle alinea's in de tabel worden uitgelijnd.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// De uitlijning wordt in dit geval overgenomen uit de eerste alinea in de overeenkomstige tabelkolom.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Sla het gewijzigde document op
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
