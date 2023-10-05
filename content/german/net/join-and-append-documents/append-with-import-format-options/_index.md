---
title: Mit Importformatoptionen anhängen
linktitle: Mit Importformatoptionen anhängen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Dokument mit Importformatoptionen anhängen.
type: docs
weight: 10
url: /de/net/join-and-append-documents/append-with-import-format-options/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET den Inhalt eines Dokuments mit Importformatoptionen an ein anderes anhängen. Der bereitgestellte Quellcode zeigt, wie Sie die Quell- und Zieldokumente öffnen, Importformatoptionen festlegen und das Quelldokument an das Zieldokument anhängen.

## Schritt 1: Richten Sie das Projekt ein

Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

-  Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen unter[Aspose.Releases]https://releases.aspose.com/words/net/ oder verwenden Sie den NuGet-Paketmanager, um es zu installieren.
- Ein Dokumentverzeichnispfad, in dem sich die Quell- und Zieldokumente befinden.

## Schritt 2: Öffnen Sie die Quell- und Zieldokumente

 Öffnen Sie die Quell- und Zieldokumente mit`Document` Klassenkonstruktor. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Schritt 3: Geben Sie die Optionen für das Importformat an

 Erstellen Sie eine Instanz von`ImportFormatOptions` Klasse, um die Importformatoptionen anzugeben. In diesem Beispiel verwenden wir die`KeepSourceNumbering` Eigenschaft, um sicherzustellen, dass die Nummerierung aus dem Quelldokument verwendet wird, wenn es zu Konflikten mit dem Zieldokument kommt.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Schritt 4: Hängen Sie das Quelldokument an das Zieldokument an

 Benutzen Sie die`AppendDocument` Methode des Zieldokuments, um das Quelldokument anzuhängen. Passieren`ImportFormatMode.UseDestinationStyles` als zweiten Parameter, um die Stile und Formatierungen des Zieldokuments zu verwenden.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Schritt 5: Speichern Sie das Zieldokument

 Speichern Sie abschließend das geänderte Zieldokument mit`Save` Methode der`Document` Objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Damit ist die Implementierung des Anhängens eines Dokuments mit Importformatoptionen mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für Append With Import Format Options mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Geben Sie an, dass bei Nummerierungskonflikten in Quell- und Zieldokumenten
	//dann wird die Nummerierung aus dem Quelldokument verwendet.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```