---
title: Exportieren in Markdown mit Ausrichtung des Tabelleninhalts
linktitle: Exportieren in Markdown mit Ausrichtung des Tabelleninhalts
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Tabelleninhalte mit unterschiedlichen Ausrichtungen in Markdown-Dateien exportieren.
type: docs
weight: 10
url: /de/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der mithilfe der Aspose.Words-Bibliothek für .NET beim Exportieren von Inhalten in eine Markdown-Datei mit Ausrichtung des Tabelleninhalts hilft. Stellen Sie sicher, dass Sie die Aspose.Words-Bibliothek in Ihr Projekt eingebunden haben, bevor Sie diesen Code verwenden.

## Schritt 1: Dokumentverzeichnispfad festlegen

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Geben Sie unbedingt den richtigen Pfad zu Ihrem Dokumentverzeichnis an, in dem das bearbeitete Dokument gespeichert wird.

## Schritt 2: Erstellen Sie ein Dokument und einen Dokumentgenerator

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Hier erstellen wir eine Instanz des`Document` Klasse und eine Instanz der`DocumentBuilder` Klasse, die es uns ermöglicht, das Dokument zu bearbeiten und Elemente hinzuzufügen.

## Schritt 3: Zellen mit unterschiedlicher Absatzausrichtung in die Tabelle einfügen

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

Mit dem Dokument-Generator fügen wir Zellen in die Tabelle ein und legen für jede Zelle eine andere Absatzausrichtung fest.

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

Wir legen die Markdown-Exportoptionen mit unterschiedlichen Ausrichtungen des Tabelleninhalts fest und speichern dann das geänderte Dokument mit jeder Ausrichtungsoption.

### Beispielquellcode zum Exportieren nach Markdown mit Ausrichtung des Tabelleninhalts unter Verwendung von Aspose.Words für .NET

```csharp

            
	// Der Pfad zum Dokumentverzeichnis.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// Sorgt dafür, dass alle Absätze innerhalb der Tabelle ausgerichtet werden.
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
	
	// Speichern des geänderten Dokuments
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
