---
title: Legen Sie die Umrissoptionen fest
linktitle: Legen Sie die Umrissoptionen fest
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Festlegen von Gliederungsoptionen in einem PDF-Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/set-outline-options/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion „Gliederungsoptionen auf Metadateigröße festlegen“ mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie verstehen, wie Sie Gliederungsoptionen in einem Dokument festlegen und ein PDF mit den entsprechenden Gliederungsoptionen erstellen.

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

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF mit Planoptionen

 Um Gliederungsoptionen im generierten PDF festzulegen, müssen wir die konfigurieren`PdfSaveOptions` Objekt. Wir können die Anzahl der Überschriftengliederungsebenen festlegen (`HeadingsOutlineLevels`) und die Anzahl der erweiterten Gliederungsebenen (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Schritt 4: Dokument als PDF mit Gliederungsoptionen speichern

Schließlich können wir das Dokument mit den zuvor konfigurierten Speicheroptionen im PDF-Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

Das ist alles ! Sie haben erfolgreich Gliederungsoptionen in einem Dokument festgelegt und mit Aspose.Words für .NET eine PDF-Datei mit entsprechenden Gliederungsoptionen generiert.

### Beispielquellcode zum Festlegen von Planoptionen auf Metadateigröße mit Aspose.Words für .NET


```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```
