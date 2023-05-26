---
title: Überspringen Sie eingebettete Arial- und Times Roman-Schriftarten
linktitle: Überspringen Sie eingebettete Arial- und Times Roman-Schriftarten
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Generieren von PDF-Dateien ohne Einbetten der Schriftarten Arial und Times Roman mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion zum Überspringen eingebetteter Arial- und Times Roman-Schriftarten auf Metadateigröße mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials erfahren Sie, wie Sie die Option zum Einbetten von Schriftarten in einem Dokument konfigurieren und eine PDF-Datei erstellen, ohne die Schriftarten Arial und Times Roman einzubetten.

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Die Bibliothek und Installationsanweisungen finden Sie auf der Aspose-Website.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Zunächst müssen Sie den Pfad zu dem Verzeichnis definieren, in dem sich Ihre Dokumente befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument hoch

Als nächstes müssen wir das Dokument laden, das wir verarbeiten möchten. In diesem Beispiel gehen wir davon aus, dass das Dokument „Rendering.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF mit Schriftarteinbettung

 Um das Einbetten der Schriftarten Arial und Times Roman in das generierte PDF zu überspringen, müssen wir das konfigurieren`PdfSaveOptions` Objekt und legen Sie das fest`FontEmbeddingMode` Eigentum zu`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Schritt 4: Speichern Sie das Dokument als PDF ohne eingebettete Schriftarten

Schließlich können wir das Dokument mit den zuvor konfigurierten Speicheroptionen im PDF-Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

Das ist alles ! Sie haben mit Aspose.Words für .NET erfolgreich eine PDF-Datei ohne Einbettung der Schriftarten Arial und Times Roman generiert.

### Beispielquellcode zum Überspringen eingebetteter Arial- und Times Roman-Schriftarten in Metadateigröße mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```
