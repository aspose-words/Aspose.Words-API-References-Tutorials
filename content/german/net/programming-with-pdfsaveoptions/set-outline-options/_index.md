---
title: Legen Sie Gliederungsoptionen in einem PDF-Dokument fest
linktitle: Legen Sie Gliederungsoptionen in einem PDF-Dokument fest
second_title: Aspose.Words-Dokumentverarbeitungs-API
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

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie mithilfe von Aspose.Words für .NET Gliederungsoptionen in einem PDF-Dokument festlegen. Mit den beschriebenen Schritten können Sie ganz einfach Überschriften- und Gliederungsebenen in Ihrem Dokument festlegen und eine PDF-Datei mit entsprechenden Gliederungsoptionen generieren. Genießen Sie die Vorteile der Gliederungsoption zur Verbesserung der Struktur und Navigation in Ihren PDF-Dokumenten mit Aspose.Words für .NET.

### Häufig gestellte Fragen

#### F: Was ist die Gliederungsoption in einem PDF-Dokument?
A: Die Gliederungsoption in einem PDF-Dokument bezieht sich auf die hierarchische Struktur des Dokumentinhalts. Es ermöglicht die Erstellung eines interaktiven Inhaltsverzeichnisses und erleichtert die Navigation im Dokument. Mit den Gliederungsoptionen legen Sie die Titel- und Untertitelebenen fest, die in die Gliederung einbezogen werden sollen, sowie den Detaillierungsgrad, der in der generierten Gliederung angezeigt werden soll.

#### F: Wie kann ich mit Aspose.Words für .NET Gliederungsoptionen in einem PDF-Dokument festlegen?
A: Um Gliederungsoptionen in einem PDF-Dokument mit Aspose.Words für .NET festzulegen, führen Sie die folgenden Schritte aus:

 Legen Sie den Verzeichnispfad fest, in dem sich Ihre Dokumente befinden, indem Sie ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad Ihres Dokumentenverzeichnisses.

 Laden Sie das Dokument, das Sie in PDF konvertieren möchten, mit`Document` Klasse und geben Sie den Pfad zum Dokument im angegebenen Dokumentenverzeichnis an.

 Konfigurieren Sie die Optionen zum Speichern als PDF, indem Sie eine Instanz davon erstellen`PdfSaveOptions` Klasse und Verwendung der`OutlineOptions` -Eigenschaft, um die Umrissoptionen festzulegen. Mit können Sie die Anzahl der Überschriftenebenen angeben, die in die Gliederung einbezogen werden sollen`HeadingsOutlineLevels` Eigenschaft und die Anzahl der erweiterten Gliederungsebenen mithilfe der`ExpandedOutlineLevels` Eigentum.

 Speichern Sie das Dokument im PDF-Format mit`Save` Methode der`Document` Klasse, die den Pfad und die Speicheroptionen angibt.

#### F: Wozu dient die Planoption in einem PDF-Dokument?
A: Mit der Gliederungsoption in einem PDF-Dokument können Sie eine hierarchische Struktur des Inhalts erstellen, die die Navigation im Dokument und den Zugriff auf verschiedene Abschnitte erleichtert. Dadurch können Benutzer schnell zu bestimmten Teilen des Dokuments springen, indem sie auf Einträge im Inhaltsverzeichnis oder in der Gliederung klicken. Die Gliederungsoption verbessert auch das Leseerlebnis, indem sie einen Überblick über die gesamte Dokumentstruktur bietet.
