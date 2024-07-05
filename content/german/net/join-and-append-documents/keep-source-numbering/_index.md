---
title: Quellennummerierung beibehalten
linktitle: Quellennummerierung beibehalten
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie in Aspose.Words für .NET ein Dokument anhängen und dabei die Quellnummerierungsformatierung beibehalten.
type: docs
weight: 10
url: /de/net/join-and-append-documents/keep-source-numbering/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET ein Quelldokument an ein Zieldokument anhängen und dabei die ursprüngliche Nummerierungsformatierung nummerierter Absätze beibehalten.

## Schritt 1: Einrichten des Projekts

Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

-  Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen von[Aspose.Releases]https://releases.aspose.com/words/net/ oder verwenden Sie den NuGet-Paketmanager, um es zu installieren.
- Ein Dokumentverzeichnispfad, in dem die Quell- und Zieldokumente gespeichert werden.

## Schritt 2: Ziel- und Quelldokumente erstellen

 Erstellen Sie Instanzen von`Document` für die Ziel- und Quelldokumente.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Schritt 3: Quellennummerierung beim Importieren beibehalten

 Um die Nummerierungsformatierung nummerierter Absätze aus dem Quelldokument beizubehalten, erstellen Sie eine Instanz von`ImportFormatOptions` und setzen`KeepSourceNumbering` Zu`true` . Benutze einen`NodeImporter` um Knoten aus dem Quelldokument in das Zieldokument zu importieren, unter Angabe`ImportFormatMode.KeepSourceFormatting` und das`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Schritt 4: Absätze importieren und anhängen

 Durchlaufen Sie die Absätze im Quelldokument und importieren Sie jeden Absatz in das Zieldokument mit dem`importer`. Hängen Sie die importierten Knoten an den Hauptteil des Zieldokuments an.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Schritt 5: Speichern Sie das geänderte Dokument

 Speichern Sie das geänderte Dokument mit dem`Save` Methode der`Document` Objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

Damit ist die Implementierung des Anhängens eines Quelldokuments an ein Zieldokument unter Beibehaltung der ursprünglichen Nummerierungsformatierung mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für „Keep Source Numbering“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Behalten Sie die Formatierung der Quellenliste bei, wenn Sie nummerierte Absätze importieren.
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