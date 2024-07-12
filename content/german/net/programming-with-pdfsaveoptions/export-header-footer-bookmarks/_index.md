---
title: Kopf- und Fußzeilenlesezeichen eines Word-Dokuments in ein PDF-Dokument exportieren
linktitle: Kopf- und Fußzeilenlesezeichen eines Word-Dokuments in ein PDF-Dokument exportieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Exportieren von Kopf- und Fußzeilenlesezeichen aus Word-Dokumenten in PDF-Dokumentlesezeichen mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zum Exportieren von Lesezeichen aus Kopf- und Fußzeilen von Word-Dokumenten in PDF-Dokumente mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie wissen, wie Sie Lesezeichen aus Kopf- und Fußzeilen eines Dokuments exportieren und ein PDF mit den entsprechenden Lesezeichen erstellen.

Stellen Sie vor dem Start sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Sie finden die Bibliothek und Installationsanweisungen auf der Aspose-Website.

## Schritt 1: Dokumentverzeichnis festlegen

 Zunächst müssen Sie den Pfad zum Verzeichnis angeben, in dem sich Ihre Dokumente befinden. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Dokument hochladen

Als nächstes müssen wir das Dokument laden, das wir verarbeiten möchten. In diesem Beispiel gehen wir davon aus, dass das Dokument „Lesezeichen in Kopf- und Fußzeilen.docx“ heißt und sich im angegebenen Dokumentverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF

 Um Kopf- und Fußzeilen-Lesezeichen zu exportieren, müssen wir die`PdfSaveOptions` Objekt. In diesem Beispiel setzen wir die Standardgliederungsebene für Lesezeichen auf 1 und den Exportmodus für Kopf- und Fußzeilenlesezeichen auf „Erste“.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## Schritt 4: Speichern Sie das Dokument als PDF mit Kopf- und Fußzeilen-Lesezeichen

Abschließend können wir das Dokument mit den zuvor konfigurierten Speicheroptionen im PDF-Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Das ist alles! Sie haben erfolgreich Kopf- und Fußzeilenlesezeichen aus einem Dokument exportiert und mit Aspose.Words für .NET ein PDF mit den entsprechenden Lesezeichen erstellt.

### Beispielquellcode zum Exportieren von Kopf- und Fußzeilenlesezeichen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie Kopf- und Fußzeilen-Lesezeichen aus einem Word-Dokument mit Aspose.Words für .NET in ein PDF-Dokument exportieren. Exportierte Lesezeichen ermöglichen eine einfache Navigation und einen schnellen Verweis auf entsprechende Kopf- und Fußzeilen im generierten PDF-Dokument. Befolgen Sie die beschriebenen Schritte, um Kopf- und Fußzeilen-Lesezeichen aus einem Dokument zu exportieren und mit Aspose.Words für .NET ein PDF mit den entsprechenden Lesezeichen zu generieren. Geben Sie unbedingt den richtigen Pfad zu Ihren Dokumenten an und konfigurieren Sie die Speicheroptionen nach Bedarf.

### Häufig gestellte Fragen

### F: Was bedeutet das Exportieren von Kopf- und Fußzeilenlesezeichen aus einem Word-Dokument in ein PDF-Dokument?
A: Das Exportieren von Kopf- und Fußzeilen-Lesezeichen aus einem Word-Dokument in ein PDF-Dokument ist eine Funktion zum Beibehalten und Generieren von Lesezeichen im PDF-Dokument aus den Kopf- und Fußzeilen des ursprünglichen Word-Dokuments. Auf diese Weise können Benutzer schnell und einfach durch das PDF-Dokument navigieren, indem sie Lesezeichen verwenden, die den Kopf- und Fußzeilen entsprechen.

### F: Wie kann ich Aspose.Words für .NET verwenden, um Kopf- und Fußzeilenlesezeichen aus einem Word-Dokument in ein PDF-Dokument zu exportieren?
A: Um Kopf- und Fußzeilenlesezeichen aus einem Word-Dokument mit Aspose.Words für .NET in ein PDF-Dokument zu exportieren, folgen Sie diesen Schritten:

 Legen Sie den Verzeichnispfad fest, in dem sich Ihre Dokumente befinden, indem Sie ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad Ihres Dokumentverzeichnisses.

 Laden Sie das zu verarbeitende Dokument mit dem`Document` Klasse und geben Sie den Pfad zum Word-Dokument im angegebenen Dokumentverzeichnis an.

 Konfigurieren Sie die Optionen zum Speichern als PDF, indem Sie eine Instanz des`PdfSaveOptions` Klasse und Festlegen der entsprechenden Lesezeichenoptionen für Kopf- und Fußzeile.

 Speichern Sie das Dokument im PDF-Format mit dem`Save` Methode der`Document` Klasse, die den Pfad und die Speicheroptionen angibt.

### F: Welche Vorteile bietet das Exportieren von Kopf- und Fußzeilenlesezeichen in ein PDF-Dokument?
A: Der Export von Kopf- und Fußzeilenlesezeichen in ein PDF-Dokument bietet folgende Vorteile:

Einfache Navigation: Lesezeichen ermöglichen Benutzern die einfache Navigation in einem PDF-Dokument durch Verweisen auf bestimmte Kopf- und Fußzeilen.

Schnellreferenz: Lesezeichen ermöglichen es Benutzern, relevante Abschnitte des PDF-Dokuments anhand von Kopf- und Fußzeilen schnell zu finden.