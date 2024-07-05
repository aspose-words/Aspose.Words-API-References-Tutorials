---
title: Exportieren der Word-Dokumentstruktur in ein PDF-Dokument
linktitle: Exportieren der Word-Dokumentstruktur in ein PDF-Dokument
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Exportieren der Word-Dokumentstruktur in ein PDF-Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/export-document-structure/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion „Word-Dokumentstruktur in PDF-Dokument exportieren“ mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie verstehen, wie Sie die Struktur eines Dokuments exportieren und ein PDF mit sichtbarer Struktur des Dokuments erstellen.

Stellen Sie vor dem Start sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Sie finden die Bibliothek und Installationsanweisungen auf der Aspose-Website.

## Schritt 1: Dokumentverzeichnis festlegen

 Zunächst müssen Sie den Pfad zum Verzeichnis angeben, in dem sich Ihre Dokumente befinden. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Dokument hochladen

Als nächstes müssen wir das Dokument laden, das wir verarbeiten möchten. In diesem Beispiel gehen wir davon aus, dass das Dokument „Paragraphs.docx“ heißt und sich im angegebenen Dokumentverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF

 Um die Dokumentstruktur zu exportieren und sie beim Bearbeiten der PDF-Datei im Navigationsbereich "Inhalt" von Adobe Acrobat Pro sichtbar zu machen, müssen wir die`PdfSaveOptions` Objekt mit dem`ExportDocumentStructure` Eigenschaft festgelegt auf`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## Schritt 4: Speichern Sie das Dokument als PDF mit der Dokumentstruktur

Abschließend können wir das Dokument mit den zuvor konfigurierten Speicheroptionen im PDF-Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

Das ist alles! Sie haben erfolgreich eine Dokumentstruktur exportiert und mit Aspose.Words für .NET ein PDF mit sichtbarer Dokumentstruktur generiert.

### Beispiel-Quellcode zum Exportieren der Dokumentstruktur mit Aspose.Words für .NET


```csharp

            // Der Pfad zum Dokumentverzeichnis.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // Die Dateigröße wird erhöht und die Struktur wird im Navigationsbereich „Inhalt“ sichtbar
            // von Adobe Acrobat Pro, während Sie die PDF-Datei bearbeiten.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie die Struktur eines Word-Dokuments mit Aspose.Words für .NET in ein PDF-Dokument exportieren. Indem Sie die beschriebenen Schritte befolgen, können Sie ganz einfach ein PDF mit sichtbarer Dokumentstruktur erstellen, was die Navigation und Suche im Dokument erleichtert. Verwenden Sie die Funktionen von Aspose.Words für .NET, um die Struktur Ihrer Word-Dokumente zu exportieren und gut strukturierte PDFs zu erstellen.

### Häufig gestellte Fragen

#### F: Was bedeutet das Exportieren der Struktur eines Word-Dokuments in ein PDF-Dokument?
A: Durch das Exportieren der Struktur eines Word-Dokuments in ein PDF-Dokument wird ein PDF mit einer sichtbaren Dokumentstruktur erstellt. Die Dokumentstruktur umfasst normalerweise Dinge wie Überschriften, Abschnitte, Absätze und andere strukturierte Elemente des Dokuments. Diese Struktur kann für die Navigation und Suche im PDF-Dokument nützlich sein.

#### F: Wie kann ich die Struktur eines Word-Dokuments mit Aspose.Words für .NET in ein PDF-Dokument exportieren?
A: Um die Struktur eines Word-Dokuments mit Aspose.Words für .NET in ein PDF-Dokument zu exportieren, gehen Sie folgendermaßen vor:

 Erstellen Sie eine Instanz des`Document` Klasse, die den Pfad zum Word-Dokument angibt.

 Erstellen Sie eine Instanz des`PdfSaveOptions` Klasse und legen Sie die`ExportDocumentStructure`Eigentum an`true`. Dadurch wird die Dokumentstruktur exportiert und beim Bearbeiten der PDF-Datei im Navigationsbereich „Inhalt“ von Adobe Acrobat Pro sichtbar gemacht.

 Verwenden Sie die`Save` Methode der`Document`Klasse, um das Dokument durch Angabe von Speicheroptionen im PDF-Format zu speichern.

#### F: Wie kann ich mit Adobe Acrobat Pro die Struktur eines PDF-Dokuments anzeigen?
A: Um die Struktur eines PDF-Dokuments mit Adobe Acrobat Pro anzuzeigen, gehen Sie folgendermaßen vor:

Öffnen Sie das PDF-Dokument in Adobe Acrobat Pro.

Klicken Sie in der linken Navigationsleiste auf das Symbol „Inhalt“, um den Navigationsbereich „Inhalt“ anzuzeigen.

Im Navigationsbereich „Inhalt“ wird Ihnen die Dokumentstruktur mit Überschriften, Abschnitten und weiteren Strukturelementen angezeigt.