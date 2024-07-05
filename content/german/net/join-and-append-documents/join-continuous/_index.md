---
title: Kontinuierlich beitreten
linktitle: Kontinuierlich beitreten
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET zwei Dokumente kontinuierlich zusammenführen und dabei die Formatierung beibehalten.
type: docs
weight: 10
url: /de/net/join-and-append-documents/join-continuous/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET zwei Dokumente kontinuierlich zusammenfügen. Der bereitgestellte Quellcode zeigt, wie Sie ein Dokument an das Ende eines anderen Dokuments anhängen und dabei die ursprüngliche Formatierung beibehalten.

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

## Schritt 3: Kontinuierlichen Abschnittsanfang einrichten

Um das Quelldokument direkt nach dem Inhalt des Zieldokuments erscheinen zu lassen, setzen Sie die`SectionStart` Eigenschaft des ersten Abschnitts im Quelldokument, um`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Schritt 4: Das Quelldokument anhängen

 Hängen Sie das Quelldokument an das Zieldokument an, indem Sie`AppendDocument` Methode der`Document` Klasse. Stellen Sie den Importformatmodus auf`ImportFormatMode.KeepSourceFormatting` um die ursprünglichen Stile aus dem Quelldokument beizubehalten.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 5: Speichern Sie das geänderte Dokument

Speichern Sie abschließend das geänderte Zieldokument mit dem`Save` Methode der`Document` Objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

Damit ist die Implementierung der kontinuierlichen Zusammenführung zweier Dokumente mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für Join Continuous mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Sorgen Sie dafür, dass das Dokument direkt nach dem Inhalt des Zieldokuments angezeigt wird.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Hängen Sie das Quelldokument unter Verwendung der im Quelldokument gefundenen Originalstile an.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```