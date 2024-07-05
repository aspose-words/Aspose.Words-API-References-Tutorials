---
title: Textfelder ignorieren
linktitle: Textfelder ignorieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Dokument anhängen und dabei die Textfeldformatierung ignorieren.
type: docs
weight: 10
url: /de/net/join-and-append-documents/ignore-text-boxes/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET ein Dokument anhängen und dabei die Formatierung der Textfelder beibehalten. Der bereitgestellte Quellcode zeigt, wie Sie die Importformatoptionen einrichten, um während des Anhängevorgangs Textfelder einzuschließen.

## Schritt 1: Einrichten des Projekts

Stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen von[Aspose.Releases]https://releases.aspose.com/words/net/ oder verwenden Sie den NuGet-Paketmanager, um es zu installieren.
- Ein Dokumentverzeichnispfad, in dem sich die Quell- und Zieldokumente befinden.

## Schritt 2: Öffnen Sie die Quell- und Zieldokumente

 Öffnen Sie die Quell- und Zieldokumente mit dem`Document` Klassenkonstruktor. Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Schritt 3: Importformatoptionen einrichten

 Erstellen Sie eine Instanz des`ImportFormatOptions` Klasse und legen Sie die`IgnoreTextBoxes`Eigentum an`false`. Dadurch wird sichergestellt, dass die Textfelder beim Anhängen einbezogen werden und ihre Formatierung erhalten bleibt.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## Schritt 4: Textfeldinhalt anhängen

 Ein ... kreieren`NodeImporter`Objekt und verwenden Sie es, um Textfeldknoten aus dem Quelldokument in das Zieldokument zu importieren. Durchlaufen Sie jeden Absatz im Quelldokument und importieren Sie ihn in das Zieldokument.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Schritt 5: Zieldokument speichern

Speichern Sie abschließend das geänderte Zieldokument mit dem`Save` Methode der`Document` Objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

Damit ist die Implementierung des Anhängens eines Dokuments unter Beibehaltung der Textfeldformatierung mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode zum Ignorieren von Textfeldern mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Behalten Sie beim Importieren die Formatierung der Quelltextfelder bei.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```