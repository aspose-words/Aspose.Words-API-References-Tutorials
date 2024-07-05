---
title: Gliederungsoptionen in einem PDF-Dokument festlegen
linktitle: Gliederungsoptionen in einem PDF-Dokument festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Festlegen von Gliederungsoptionen in einem PDF-Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/set-outline-options/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion „Gliederungsoptionen auf Metadateigröße festlegen“ mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie wissen, wie Sie Gliederungsoptionen in einem Dokument festlegen und ein PDF mit den entsprechenden Gliederungsoptionen erstellen.

Stellen Sie vor dem Start sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Sie finden die Bibliothek und Installationsanweisungen auf der Aspose-Website.

## Schritt 1: Dokumentverzeichnis festlegen

 Zunächst müssen Sie den Pfad zum Verzeichnis angeben, in dem sich Ihre Dokumente befinden. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Dokument hochladen

Als nächstes müssen wir das Dokument laden, das wir verarbeiten möchten. In diesem Beispiel gehen wir davon aus, dass das Dokument „Rendering.docx“ heißt und sich im angegebenen Dokumentverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF mit den Planoptionen

Um die Gliederungsoptionen im generierten PDF festzulegen, müssen wir die`PdfSaveOptions` Objekt. Wir können die Anzahl der Gliederungsebenen für Überschriften festlegen (`HeadingsOutlineLevels`) und die Anzahl der erweiterten Gliederungsebenen (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Schritt 4: Dokument als PDF mit Gliederungsoptionen speichern

Abschließend können wir das Dokument mit den zuvor konfigurierten Speicheroptionen im PDF-Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

Das ist alles! Sie haben erfolgreich Gliederungsoptionen in einem Dokument festgelegt und mit Aspose.Words für .NET ein PDF mit entsprechenden Gliederungsoptionen erstellt.

### Beispielquellcode zum Festlegen von Planoptionen auf die Metadateigröße mit Aspose.Words für .NET


```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie mit Aspose.Words für .NET Gliederungsoptionen in einem PDF-Dokument festlegen. Mit den beschriebenen Schritten können Sie ganz einfach Überschriften- und Gliederungsebenen in Ihrem Dokument festlegen und eine PDF-Datei mit entsprechenden Gliederungsoptionen erstellen. Profitieren Sie von den Vorteilen der Gliederungsoption, um mit Aspose.Words für .NET die Struktur und Navigation in Ihren PDF-Dokumenten zu verbessern.

### Häufig gestellte Fragen

#### F: Was ist die Gliederungsoption in einem PDF-Dokument?
A: Die Gliederungsoption in einem PDF-Dokument bezieht sich auf die hierarchische Struktur des Dokumentinhalts. Sie ermöglicht Ihnen die Erstellung eines interaktiven Inhaltsverzeichnisses und erleichtert die Navigation im Dokument. Gliederungsoptionen bestimmen die Titel- und Untertitelebenen, die in die Gliederung aufgenommen werden sollen, und den Detaillierungsgrad, der in der generierten Gliederung angezeigt werden soll.

#### F: Wie kann ich mit Aspose.Words für .NET Gliederungsoptionen in einem PDF-Dokument festlegen?
A: Um Gliederungsoptionen in einem PDF-Dokument mit Aspose.Words für .NET festzulegen, folgen Sie diesen Schritten:

 Legen Sie den Verzeichnispfad fest, in dem sich Ihre Dokumente befinden, indem Sie ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad Ihres Dokumentverzeichnisses.

 Laden Sie das Dokument, das Sie in PDF konvertieren möchten, mit dem`Document` Klasse und geben Sie den Pfad zum Dokument im angegebenen Dokumentverzeichnis an.

 Konfigurieren Sie die Optionen zum Speichern als PDF, indem Sie eine Instanz des`PdfSaveOptions` Klasse und unter Verwendung der`OutlineOptions` -Eigenschaft, um die Gliederungsoptionen festzulegen. Sie können die Anzahl der Überschriftenebenen angeben, die in die Gliederung aufgenommen werden sollen, indem Sie`HeadingsOutlineLevels` und die Anzahl der erweiterten Gliederungsebenen mit dem`ExpandedOutlineLevels` Eigentum.

 Speichern Sie das Dokument im PDF-Format mit dem`Save` Methode der`Document` Klasse, die den Pfad und die Speicheroptionen angibt.

#### F: Wozu dient die Planoption in einem PDF-Dokument?
A: Mit der Gliederungsoption in einem PDF-Dokument können Sie eine hierarchische Struktur des Inhalts erstellen, die die Navigation im Dokument und den Zugriff auf verschiedene Abschnitte erleichtert. So können Benutzer schnell zu bestimmten Teilen des Dokuments springen, indem sie auf Einträge im Inhaltsverzeichnis oder in der Gliederung klicken. Die Gliederungsoption verbessert außerdem das Leseerlebnis, indem sie einen Überblick über die Gesamtstruktur des Dokuments bietet.
