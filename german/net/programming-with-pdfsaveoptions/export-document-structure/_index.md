---
title: Dokumentstruktur exportieren
linktitle: Dokumentstruktur exportieren
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Exportieren der Dokumentstruktur mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/export-document-structure/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion „Dokumentstruktur exportieren“ mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie verstehen, wie Sie die Struktur eines Dokuments exportieren und ein PDF mit sichtbarer Struktur des Dokuments erstellen.

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Die Bibliothek und Installationsanweisungen finden Sie auf der Aspose-Website.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Zunächst müssen Sie den Pfad zu dem Verzeichnis definieren, in dem sich Ihre Dokumente befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument hoch

Als nächstes müssen wir das Dokument laden, das wir verarbeiten möchten. In diesem Beispiel gehen wir davon aus, dass das Dokument „Paragraphs.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF

 Um die Dokumentstruktur zu exportieren und die Struktur beim Bearbeiten der PDF-Datei im Navigationsbereich „Inhalt“ von Adobe Acrobat Pro sichtbar zu machen, müssen wir das konfigurieren`PdfSaveOptions` Objekt mit dem`ExportDocumentStructure` Eigenschaft festgelegt auf`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## Schritt 4: Speichern Sie das Dokument als PDF mit der Dokumentstruktur

Schließlich können wir das Dokument mit den zuvor konfigurierten Speicheroptionen im PDF-Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

Das ist alles ! Sie haben mit Aspose.Words für .NET erfolgreich eine Dokumentstruktur exportiert und eine PDF-Datei mit sichtbarer Dokumentstruktur generiert.

### Beispielquellcode zum Exportieren der Dokumentstruktur mit Aspose.Words für .NET


```csharp

            // Der Pfad zum Dokumentenverzeichnis.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // Die Dateigröße wird erhöht und die Struktur wird im Navigationsbereich „Inhalt“ sichtbar
            // von Adobe Acrobat Pro, während Sie die PDF-Datei bearbeiten.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```
