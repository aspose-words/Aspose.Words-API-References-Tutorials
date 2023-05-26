---
title: Alle Schriftarten eingebettet
linktitle: Alle Schriftarten eingebettet
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Einbetten aller Schriftarten in ein PDF mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/embedded-all-fonts/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion „Alle eingebetteten Schriftarten“ von Aspose.Words für .NET. Wir gehen das Code-Snippet durch und erklären jeden Teil im Detail. Am Ende dieses Tutorials werden Sie verstehen, wie Sie mit Aspose.Words für .NET alle Schriftarten in ein Dokument einbetten und eine PDF-Datei mit den eingebetteten Schriftarten erstellen.

Bevor wir beginnen, stellen Sie sicher, dass die Aspose.Words for .NET-Bibliothek in Ihrem Projekt installiert und eingerichtet ist. Die Bibliothek und Installationsanweisungen finden Sie auf der Aspose-Website.

## Schritt 1: Definieren Sie den Dokumentverzeichnispfad

Um zu beginnen, müssen Sie den Pfad zu dem Verzeichnis definieren, in dem sich Ihre Dokumente befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument

Als nächstes müssen wir das Dokument laden, das wir verarbeiten möchten. In diesem Beispiel gehen wir davon aus, dass das Dokument den Namen „Rendering.docx“ trägt und sich im angegebenen Dokumentverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 3: Konfigurieren Sie die PDF-Speicheroptionen

 Um alle Schriftarten in das resultierende PDF einzubetten, müssen wir die konfigurieren`PdfSaveOptions` Objekt mit dem`EmbedFullFonts` Eigenschaft festgelegt auf`true`. Dadurch wird sichergestellt, dass alle im Dokument verwendeten Schriftarten in der generierten PDF-Datei enthalten sind.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
```

## Schritt 4: Speichern Sie das Dokument als PDF mit eingebetteten Schriftarten

 Abschließend können wir das Dokument mit den eingebetteten Schriftarten als PDF-Datei speichern. Geben Sie den Namen der Ausgabedatei und die Datei an`saveOptions` Objekt, das wir im vorherigen Schritt konfiguriert haben.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
```

Das ist es! Sie haben alle Schriftarten erfolgreich in ein Dokument eingebettet und mit Aspose.Words für .NET eine PDF-Datei mit den eingebetteten Schriftarten generiert.

### Beispielquellcode für Embedded All Fonts mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Das Ausgabe-PDF wird mit allen im Dokument gefundenen Schriftarten eingebettet.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
  
```

## Abschluss

In diesem Tutorial haben wir den schrittweisen Prozess der Verwendung der Funktion „Alle eingebetteten Schriftarten“ von Aspose.Words für .NET behandelt. Wir haben gelernt, wie man ein Dokument lädt, die PDF-Speicheroptionen konfiguriert und das Dokument als PDF-Datei mit eingebetteten Schriftarten speichert. Wenn Sie dieser Anleitung folgen, können Sie sicherstellen, dass in Ihre PDF-Dokumente alle erforderlichen Schriftarten eingebettet sind, sodass eine konsistente und genaue Wiedergabe auf verschiedenen Geräten und Plattformen gewährleistet ist.
