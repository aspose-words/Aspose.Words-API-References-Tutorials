---
title: Exportieren Sie die Kopf- und Fußzeilen-Lesezeichen eines Word-Dokuments in ein PDF-Dokument
linktitle: Exportieren Sie die Kopf- und Fußzeilen-Lesezeichen eines Word-Dokuments in ein PDF-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Exportieren von Kopf- und Fußzeilen-Lesezeichen von Word-Dokumenten in PDF-Dokument-Lesezeichen mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zum Exportieren von Kopf- und Fußzeilen-Lesezeichen eines Word-Dokuments in die PDF-Dokumentfunktion mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials erfahren Sie, wie Sie Lesezeichen aus Kopf- und Fußzeilen eines Dokuments exportieren und ein PDF mit den entsprechenden Lesezeichen erstellen.

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

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie mit Aspose.Words für .NET Kopf- und Fußzeilen-Lesezeichen aus einem Word-Dokument in ein PDF-Dokument exportieren. Exportierte Lesezeichen ermöglichen eine einfache Navigation und einen schnellen Verweis auf entsprechende Kopf- und Fußzeilen im generierten PDF-Dokument. Befolgen Sie die beschriebenen Schritte, um Kopf- und Fußzeilen-Lesezeichen aus einem Dokument zu exportieren und mit Aspose.Words für .NET eine PDF-Datei mit den entsprechenden Lesezeichen zu generieren. Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihren Dokumenten angeben und die Speicheroptionen nach Bedarf konfigurieren.

# Häufig gestellte Fragen

### F: Was bedeutet der Export von Kopf- und Fußzeilen-Lesezeichen aus einem Word-Dokument in ein PDF-Dokument?
A: Das Exportieren von Kopf- und Fußzeilen-Lesezeichen aus einem Word-Dokument in ein PDF-Dokument ist eine Funktion zum Beibehalten und Generieren von Lesezeichen im PDF-Dokument aus den Kopf- und Fußzeilen. Fußzeilen des ursprünglichen Word-Dokuments. Dadurch können Benutzer schnell und einfach durch das PDF-Dokument navigieren, indem sie Lesezeichen für Kopf- und Fußzeilen verwenden.

### F: Wie kann ich Aspose.Words für .NET verwenden, um Kopf- und Fußzeilen-Lesezeichen aus einem Word-Dokument in ein PDF-Dokument zu exportieren?
A: Um mit Aspose.Words für .NET Kopf- und Fußzeilen-Lesezeichen aus einem Word-Dokument in ein PDF-Dokument zu exportieren, führen Sie die folgenden Schritte aus:

 Legen Sie den Verzeichnispfad fest, in dem sich Ihre Dokumente befinden, indem Sie ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad Ihres Dokumentenverzeichnisses.

 Laden Sie das Dokument, das Sie bearbeiten möchten, mit`Document` Klasse und geben Sie den Pfad zum Word-Dokument im angegebenen Dokumentenverzeichnis an.

 Konfigurieren Sie die Optionen zum Speichern als PDF, indem Sie eine Instanz davon erstellen`PdfSaveOptions` Klasse und Festlegen der entsprechenden Optionen für Kopf- und Fußzeilen-Lesezeichen.

 Speichern Sie das Dokument im PDF-Format mit`Save` Methode der`Document`Klasse, die den Pfad und die Speicheroptionen angibt.

### F: Welche Vorteile bietet der Export von Kopf- und Fußzeilen-Lesezeichen in ein PDF-Dokument?
A: Der Export von Kopf- und Fußzeilen-Lesezeichen in ein PDF-Dokument bietet folgende Vorteile:

Einfache Navigation: Lesezeichen ermöglichen Benutzern die einfache Navigation in einem PDF-Dokument, indem sie auf bestimmte Kopf- und Fußzeilen verweisen.

Schnellreferenz: Mit Lesezeichen können Benutzer relevante Abschnitte des PDF-Dokuments anhand von Kopf- und Fußzeilen schnell finden.