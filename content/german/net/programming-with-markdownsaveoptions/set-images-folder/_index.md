---
title: Bilderordner festlegen
linktitle: Bilderordner festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie den Bilderordner beim Exportieren nach Markdown mit Aspose.Words für .NET festlegen. Passen Sie die Platzierung der Bilder für eine bessere Organisation und Integration an.
type: docs
weight: 10
url: /de/net/programming-with-markdownsaveoptions/set-images-folder/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erklärung des folgenden C#-Quellcodes, der dabei hilft, den Bilderordner für Markdown-Exportoptionen mithilfe der Aspose.Words-Bibliothek für .NET einzurichten. Stellen Sie sicher, dass Sie die Aspose.Words-Bibliothek in Ihr Projekt aufgenommen haben, bevor Sie diesen Code verwenden.

## Schritt 1: Dokumentverzeichnispfad festlegen

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Geben Sie unbedingt den richtigen Pfad zu Ihrem Dokumentverzeichnis an, in dem sich das Dokument mit den Bildern befindet.

## Schritt 2: Laden Sie das Dokument mit den Bildern

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Wir laden das angegebene Dokument, das die Bilder enthält, die wir mit Markdown-Optionen exportieren möchten.

## Schritt 3: Bilderordner für Markdown-Exportoptionen festlegen

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 Wir erstellen eine Instanz von`MarkdownSaveOptions` und legen Sie den Pfad zum Bilderordner mit dem`ImagesFolder` Eigenschaft. Stellen Sie sicher, dass Sie den richtigen Pfad zu dem Ordner angeben, in dem Sie die exportierten Bilder speichern möchten.

## Schritt 4: Speichern Sie das Dokument mit Markdown-Exportoptionen

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Wir speichern das Dokument in einem Speicherstream unter Verwendung der angegebenen Markdown-Exportoptionen. Anschließend können Sie den Flow verwenden, um andere Vorgänge auszuführen, z. B. das Speichern von Markdown-Inhalten in einer Datei.

### Beispielquellcode zum Festlegen des Bilderordners für MarkdownSaveOptions mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Dieser Quellcode zeigt, wie Sie ein Dokument laden, das Bilder enthält, und dann den Bilderordner für Markdown-Exportoptionen festlegen. Mit den angegebenen Optionen wird das Dokument dann in einem Speicherstream gespeichert. Auf diese Weise können Sie den Speicherort des Bilderordners beim Exportieren von Markdown-Inhalten anpassen.