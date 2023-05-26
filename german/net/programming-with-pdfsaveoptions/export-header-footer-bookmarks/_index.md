---
title: Kopf- und Fußzeilen-Lesezeichen exportieren
linktitle: Kopf- und Fußzeilen-Lesezeichen exportieren
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Exportieren von Kopf- und Fußzeilen-Lesezeichen mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion „Kopf- und Fußzeilen-Lesezeichen exportieren“ mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials erfahren Sie, wie Sie Lesezeichen aus Kopf- und Fußzeilen eines Dokuments exportieren und ein PDF mit den entsprechenden Lesezeichen erstellen.

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Die Bibliothek und Installationsanweisungen finden Sie auf der Aspose-Website.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Zunächst müssen Sie den Pfad zu dem Verzeichnis definieren, in dem sich Ihre Dokumente befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument hoch

Als nächstes müssen wir das Dokument laden, das wir verarbeiten möchten. In diesem Beispiel gehen wir davon aus, dass das Dokument „Lesezeichen in Kopf- und Fußzeilen.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF

 Um Kopf- und Fußzeilen-Lesezeichen zu exportieren, müssen wir die konfigurieren`PdfSaveOptions` Objekt. In diesem Beispiel setzen wir die Standard-Lesezeichen-Gliederungsebene auf 1 und den Exportmodus für Kopf- und Fußzeilen-Lesezeichen auf „Erste“.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## Schritt 4: Speichern Sie das Dokument als PDF mit Lesezeichen für Kopf- und Fußzeilen

Schließlich können wir das Dokument mit den zuvor konfigurierten Speicheroptionen im PDF-Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Das ist alles ! Sie haben erfolgreich Kopf- und Fußzeilen-Lesezeichen aus einem Dokument exportiert und mit Aspose.Words für .NET eine PDF-Datei mit den entsprechenden Lesezeichen generiert.

### Beispielquellcode zum Exportieren von Kopf- und Fußzeilen-Lesezeichen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```
