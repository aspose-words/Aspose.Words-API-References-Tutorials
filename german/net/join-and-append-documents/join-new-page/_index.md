---
title: Neuer Seite beitreten
linktitle: Neuer Seite beitreten
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET zwei Dokumente auf einer neuen Seite zusammenfügen und dabei die Formatierung beibehalten.
type: docs
weight: 10
url: /de/net/join-and-append-documents/join-new-page/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET zwei Dokumente auf einer neuen Seite zusammenfügen. Der bereitgestellte Quellcode zeigt, wie ein Dokument an das Ende eines anderen Dokuments angehängt wird, während das angehängte Dokument auf einer neuen Seite beginnt.

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

## Schritt 3: Richten Sie den Anfang des neuen Seitenabschnitts ein

 Um das angehängte Dokument auf einer neuen Seite zu beginnen, legen Sie fest`SectionStart` Eigenschaft des ersten Abschnitts im Quelldokument`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Schritt 4: Hängen Sie das Quelldokument an

 Hängen Sie das Quelldokument mit an das Zieldokument an`AppendDocument` Methode der`Document` Klasse. Stellen Sie den Importformatmodus auf ein`ImportFormatMode.KeepSourceFormatting` um die ursprünglichen Stile aus dem Quelldokument beizubehalten.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 5: Speichern Sie das geänderte Dokument

 Speichern Sie abschließend das geänderte Zieldokument mit`Save` Methode der`Document` Objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

Damit ist die Implementierung des Zusammenfügens zweier Dokumente auf einer neuen Seite mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für „Join New Page“ mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Legen Sie fest, dass das angehängte Dokument auf einer neuen Seite beginnt.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Hängen Sie das Quelldokument mit den im Quelldokument gefundenen Originalstilen an.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```