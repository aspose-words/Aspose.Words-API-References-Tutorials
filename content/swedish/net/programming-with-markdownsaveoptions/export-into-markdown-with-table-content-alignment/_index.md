---
title: Exportera till Markdown med tabellinnehållsjustering
linktitle: Exportera till Markdown med tabellinnehållsjustering
second_title: Aspose.Words Document Processing API
description: Lär dig hur du exporterar tabellinnehåll med olika justeringar till Markdown-filer med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Här är en steg-för-steg-guide för att förklara följande C#-källkod som hjälper till att exportera innehåll till en Markdown-fil med tabellinnehållsjustering med hjälp av Aspose.Words-biblioteket för .NET. Se till att du har inkluderat Aspose.Words-biblioteket i ditt projekt innan du använder den här koden.

## Steg 1: Ange sökväg till dokumentkatalogen

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Var noga med att ange rätt sökväg till din dokumentkatalog där det redigerade dokumentet kommer att sparas.

## Steg 2: Skapa ett dokument och en dokumentgenerator

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Här skapar vi en instans av`Document` klass och en instans av`DocumentBuilder` klass som gör att vi kan manipulera dokumentet och lägga till element.

## Steg 3: Infoga celler i tabellen med olika styckejusteringar

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

Vi använder Document Builder för att infoga celler i tabellen och ställa in olika styckejusteringar för varje cell.

## Steg 4: Ställ in Markdown-exportalternativ och spara det ändrade dokumentet

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

Vi ställer in Markdown-exportalternativen med olika tabellinnehållsjusteringar och sparar sedan det modifierade dokumentet med varje justeringsalternativ.

### Exempel på källkod att exportera till Markdown med tabellinnehållsjustering med Aspose.Words för .NET

```csharp

            
	// Sökvägen till dokumentkatalogen.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// Gör att alla stycken i tabellen justeras.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// Justeringen i detta fall kommer att tas från första stycket i motsvarande tabellkolumn.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Spara det ändrade dokumentet
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
