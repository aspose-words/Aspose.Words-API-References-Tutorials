---
title: Anhängen mit Importformatoptionen
linktitle: Anhängen mit Importformatoptionen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Dokument mit Importformatoptionen anhängen.
type: docs
weight: 10
url: /de/net/join-and-append-documents/append-with-import-format-options/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET den Inhalt eines Dokuments mit Importformatoptionen an ein anderes anhängen. Der bereitgestellte Quellcode zeigt, wie Sie die Quell- und Zieldokumente öffnen, Importformatoptionen angeben und das Quelldokument an das Zieldokument anhängen.

## Schritt 1: Einrichten des Projekts

Stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen von[Aspose.Releases]https://releases.aspose.com/words/net/ oder verwenden Sie den NuGet-Paketmanager, um es zu installieren.
- Ein Dokumentverzeichnispfad, in dem sich die Quell- und Zieldokumente befinden.

## Schritt 2: Öffnen Sie die Quell- und Zieldokumente

 Öffnen Sie die Quell- und Zieldokumente mit dem`Document` Klassenkonstruktor. Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Schritt 3: Importformatoptionen festlegen

 Erstellen Sie eine Instanz des`ImportFormatOptions` Klasse, um die Importformatoptionen anzugeben. In diesem Beispiel verwenden wir die`KeepSourceNumbering` -Eigenschaft, um sicherzustellen, dass bei Konflikten mit dem Zieldokument die Nummerierung aus dem Quelldokument verwendet wird.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Schritt 4: Anhängen des Quelldokuments an das Zieldokument

 Verwenden Sie die`AppendDocument` Methode des Zieldokuments, um das Quelldokument anzuhängen. Übergeben Sie`ImportFormatMode.UseDestinationStyles` als zweiten Parameter, um die Stile und Formatierungen des Zieldokuments zu verwenden.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Schritt 5: Zieldokument speichern

Speichern Sie abschließend das geänderte Zieldokument mit dem`Save` Methode der`Document` Objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Damit ist die Implementierung des Anhängens eines Dokuments mit Importformatoptionen mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für „Anhängen mit Importformatoptionen“ unter Verwendung von Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Geben Sie an, dass bei Nummerierungskonflikten in Quell- und Zieldokumenten
	// dann wird die Nummerierung aus dem Quelldokument verwendet.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```