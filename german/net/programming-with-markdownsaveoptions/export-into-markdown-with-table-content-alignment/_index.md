---
title: Export in Markdown mit Tabelleninhaltsausrichtung
linktitle: Export in Markdown mit Tabelleninhaltsausrichtung
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Tabelleninhalte mit unterschiedlichen Ausrichtungen in Markdown-Dateien exportieren.
type: docs
weight: 10
url: /de/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der beim Exportieren von Inhalten in eine Markdown-Datei mit Tabelleninhaltsausrichtung mithilfe der Aspose.Words-Bibliothek für .NET hilft. Stellen Sie sicher, dass Sie die Aspose.Words-Bibliothek in Ihr Projekt eingebunden haben, bevor Sie diesen Code verwenden.

## Schritt 1: Legen Sie den Pfad zum Dokumentverzeichnis fest

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Stellen Sie sicher, dass Sie den korrekten Pfad zu Ihrem Dokumentenverzeichnis angeben, in dem das bearbeitete Dokument gespeichert wird.

## Schritt 2: Erstellen Sie ein Dokument und einen Dokumentengenerator

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Hier erstellen wir eine Instanz von`Document` Klasse und eine Instanz davon`DocumentBuilder` Klasse, die es uns ermöglicht, das Dokument zu bearbeiten und Elemente hinzuzufügen.

## Schritt 3: Fügen Sie Zellen mit unterschiedlichen Absatzausrichtungen in die Tabelle ein

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

Wir verwenden den Document Builder, um Zellen in die Tabelle einzufügen und für jede Zelle unterschiedliche Absatzausrichtungen festzulegen.

## Schritt 4: Markdown-Exportoptionen festlegen und das geänderte Dokument speichern

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

Wir legen die Markdown-Exportoptionen mit unterschiedlichen Tabelleninhaltsausrichtungen fest und speichern dann das geänderte Dokument mit jeder Ausrichtungsoption.

### Beispielquellcode zum Exportieren nach Markdown mit Tabelleninhaltsausrichtung mithilfe von Aspose.Words für .NET

```csharp

            
	// Der Pfad zum Dokumentenverzeichnis.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// Alle Absätze in der Tabelle werden ausgerichtet.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// Die Ausrichtung wird in diesem Fall dem ersten Absatz in der entsprechenden Tabellenspalte entnommen.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Speichern Sie das geänderte Dokument
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
