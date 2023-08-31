---
title: Legen Sie den Bilderordner fest
linktitle: Legen Sie den Bilderordner fest
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie den Bilderordner beim Exportieren nach Markdown mit Aspose.Words für .NET festlegen. Passen Sie die Platzierung von Bildern für eine bessere Organisation und Integration an.
type: docs
weight: 10
url: /de/net/programming-with-markdownsaveoptions/set-images-folder/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der dabei hilft, den Bildordner für Markdown-Exportoptionen mithilfe der Aspose.Words-Bibliothek für .NET festzulegen. Stellen Sie sicher, dass Sie die Aspose.Words-Bibliothek in Ihr Projekt eingebunden haben, bevor Sie diesen Code verwenden.

## Schritt 1: Legen Sie den Pfad zum Dokumentverzeichnis fest

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Stellen Sie sicher, dass Sie den korrekten Pfad zu Ihrem Dokumentenverzeichnis angeben, in dem sich das Dokument mit den Bildern befindet.

## Schritt 2: Laden Sie das Dokument mit den Bildern

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Wir laden das angegebene Dokument, das die Bilder enthält, die wir exportieren möchten, mit Markdown-Optionen.

## Schritt 3: Legen Sie den Bilderordner für Markdown-Exportoptionen fest

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 Wir erstellen eine Instanz von`MarkdownSaveOptions` und legen Sie den Pfad zum Bilderordner mit fest`ImagesFolder` Eigentum. Stellen Sie sicher, dass Sie den richtigen Pfad zu dem Ordner angeben, in dem Sie die exportierten Bilder speichern möchten.

## Schritt 4: Speichern Sie das Dokument mit den Markdown-Exportoptionen

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Wir speichern das Dokument mithilfe der angegebenen Markdown-Exportoptionen in einem Speicherstream. Anschließend können Sie den Flow verwenden, um andere Vorgänge auszuführen, beispielsweise das Speichern von Markdown-Inhalten in einer Datei.

### Beispielquellcode zum Festlegen des Bildordners für MarkdownSaveOptions mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Dieser Quellcode zeigt, wie Sie ein Dokument laden, das Bilder enthält, und dann den Bilderordner für Markdown-Exportoptionen festlegen. Unter Verwendung der angegebenen Optionen wird das Dokument dann in einem Speicherstream gespeichert. Dadurch können Sie den Speicherort des Bilderordners beim Exportieren von Markdown-Inhalten anpassen.