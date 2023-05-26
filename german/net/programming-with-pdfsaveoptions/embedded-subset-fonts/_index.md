---
title: Eingebettete Teilsatzschriftarten
linktitle: Eingebettete Teilsatzschriftarten
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Einbetten von Schriftartteilmengen in ein PDF mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion zum Einbetten von Schriftartteilmengen mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie verstehen, wie Sie Teilsätze von Schriftarten in ein Dokument einbetten und eine PDF-Datei erstellen, die nur die im Dokument verwendeten Glyphen enthält.

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

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF

 Um eine PDF-Datei zu erstellen, die nur die Teilmengen der im Dokument verwendeten Schriftarten enthält, müssen wir die konfigurieren`PdfSaveOptions` Objekt mit dem`EmbedFullFonts` Eigenschaft festgelegt auf`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Schritt 4: Dokument als PDF mit Schriftart-Untergruppen speichern

 Schließlich können wir das Dokument mithilfe der Schriftarten-Untergruppen als PDF speichern. Geben Sie den Namen der Ausgabedatei und die Datei an`saveOptions` Objekt, das wir im vorherigen Schritt konfiguriert haben.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Das ist alles ! Sie haben Teilsätze von Schriftarten erfolgreich in ein Dokument eingebettet und mit Aspose.Words für .NET eine PDF-Datei generiert, die nur die im Dokument verwendeten Glyphen enthält.

### Beispielquellcode zum Einbetten von Schriftartteilmengen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Die Ausgabe-PDF enthält Teilmengen der Schriftarten im Dokument.
	// In den PDF-Schriftarten sind nur die im Dokument verwendeten Glyphen enthalten.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```
