---
title: Behalten Sie die Quellennummerierung bei
linktitle: Behalten Sie die Quellennummerierung bei
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie ein Dokument anhängen und dabei die Nummerierungsformatierung der Quelle in Aspose.Words für .NET beibehalten.
type: docs
weight: 10
url: /de/net/join-and-append-documents/keep-source-numbering/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET ein Quelldokument an ein Zieldokument anhängen und dabei die ursprüngliche Nummerierungsformatierung nummerierter Absätze beibehalten.

## Schritt 1: Richten Sie das Projekt ein

Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen unter[Aspose.Releases]https://releases.aspose.com/words/net/ oder verwenden Sie den NuGet-Paketmanager, um es zu installieren.
- Ein Dokumentverzeichnispfad, in dem die Quell- und Zieldokumente gespeichert werden.

## Schritt 2: Erstellen Sie die Ziel- und Quelldokumente

 Erstellen Sie Instanzen von`Document` für die Ziel- und Quelldokumente.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Schritt 3: Behalten Sie beim Import die Quellennummerierung bei

 Um die Nummerierungsformatierung nummerierter Absätze aus dem Quelldokument beizubehalten, erstellen Sie eine Instanz von`ImportFormatOptions` und eingestellt`KeepSourceNumbering` Zu`true` . Benutze einen`NodeImporter` um Knoten aus dem Quelldokument in das Zieldokument zu importieren, unter Angabe`ImportFormatMode.KeepSourceFormatting` und das`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Schritt 4: Absätze importieren und anhängen

 Durchlaufen Sie die Absätze im Quelldokument und importieren Sie jeden Absatz mithilfe von in das Zieldokument`importer`. Hängen Sie die importierten Knoten an den Hauptteil des Zieldokuments an.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Schritt 5: Speichern Sie das geänderte Dokument

 Speichern Sie das geänderte Dokument mit`Save` Methode der`Document` Objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

Damit ist die Implementierung des Anhängens eines Quelldokuments an ein Zieldokument unter Beibehaltung der ursprünglichen Nummerierungsformatierung mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für Keep Source Numbering mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Behalten Sie beim Importieren nummerierter Absätze die Formatierung der Quellenliste bei.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```