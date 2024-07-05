---
title: Originalformatierung beibehalten
linktitle: Originalformatierung beibehalten
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Quelldokument an ein Zieldokument anhängen und dabei die ursprüngliche Formatierung beibehalten.
type: docs
weight: 10
url: /de/net/join-and-append-documents/keep-source-formatting/
---

Dieses Tutorial zeigt, wie Sie mit Aspose.Words für .NET ein Quelldokument an ein Zieldokument anhängen und dabei die ursprüngliche Formatierung des Quelldokuments beibehalten.

## Schritt 1: Einrichten des Projekts

Stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen von[Aspose.Releases]https://releases.aspose.com/words/net/ oder verwenden Sie den NuGet-Paketmanager, um es zu installieren.
- Ein Dokumentverzeichnispfad, in dem die Quell- und Zieldokumente gespeichert werden.

## Schritt 2: Ziel- und Quelldokumente erstellen

 Erstellen Sie Instanzen von`Document` für die Ziel- und Quelldokumente.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## Schritt 3: Anhängen des Quelldokuments an das Zieldokument

 Verwenden Sie die`AppendDocument` Methode des Zieldokuments, um das Quelldokument anzuhängen. Übergeben Sie`ImportFormatMode.KeepSourceFormatting` als Importformatmodus, um die ursprüngliche Formatierung des Quelldokuments beizubehalten.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 4: Speichern Sie das geänderte Dokument

 Speichern Sie das geänderte Dokument mit dem`Save` Methode der`Document` Objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

Damit ist die Implementierung des Anhängens eines Quelldokuments an ein Zieldokument unter Beibehaltung der ursprünglichen Formatierung mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für „Quellformatierung beibehalten“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// Hängt das Quelldokument an das Zieldokument an.
	// Übergeben Sie den Formatierungsmodus, um die ursprüngliche Formatierung des Quelldokuments beim Importieren beizubehalten.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```