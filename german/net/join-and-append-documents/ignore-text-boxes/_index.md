---
title: Textfelder ignorieren
linktitle: Textfelder ignorieren
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Dokument anhängen und dabei die Textfeldformatierung ignorieren.
type: docs
weight: 10
url: /de/net/join-and-append-documents/ignore-text-boxes/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET ein Dokument anhängen und dabei die Formatierung von Textfeldern beibehalten. Der bereitgestellte Quellcode zeigt, wie die Importformatoptionen so eingerichtet werden, dass Textfelder während des Anhängevorgangs einbezogen werden.

## Schritt 1: Richten Sie das Projekt ein

Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Aspose.Words für .NET-Bibliothek installiert. Sie können es von der offiziellen Aspose-Website herunterladen oder den NuGet-Paketmanager verwenden, um es zu installieren.
- Ein Dokumentverzeichnispfad, in dem sich die Quell- und Zieldokumente befinden.

## Schritt 2: Öffnen Sie die Quell- und Zieldokumente

 Öffnen Sie die Quell- und Zieldokumente mit`Document` Klassenkonstruktor. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Schritt 3: Importformatoptionen einrichten

 Erstellen Sie eine Instanz von`ImportFormatOptions`Klasse und legen Sie die fest`IgnoreTextBoxes` Eigentum zu`false`. Dadurch wird sichergestellt, dass die Textfelder während des Anhängevorgangs einbezogen werden und ihre Formatierung erhalten bleibt.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## Schritt 4: Textfeldinhalt anhängen

 Ein ... kreieren`NodeImporter`Objekt und verwenden Sie es, um Textfeldknoten aus dem Quelldokument in das Zieldokument zu importieren. Gehen Sie jeden Absatz im Quelldokument durch und importieren Sie ihn in das Zieldokument.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Schritt 5: Speichern Sie das Zieldokument

 Speichern Sie abschließend das geänderte Zieldokument mit`Save` Methode der`Document` Objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

Damit ist die Implementierung des Anhängens eines Dokuments unter Beibehaltung der Textfeldformatierung mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für „Textfelder ignorieren“ mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
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