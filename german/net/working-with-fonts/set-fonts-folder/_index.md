---
title: Legen Sie den Schriftartenordner fest
linktitle: Legen Sie den Schriftartenordner fest
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie das Schriftartenverzeichnis in Aspose.Words für .NET festlegen und die Verfügbarkeit der in Ihren Dokumenten verwendeten Schriftarten sicherstellen.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-fonts-folder/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie das Schriftartenverzeichnis in Aspose.Words für .NET festlegen. Sie erfahren, wie Sie das Verzeichnis mit den in Ihrem Word-Dokument verwendeten Schriftarten angeben.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Legen Sie zunächst den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments fest. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Schriftartverzeichnis festlegen
 Erstellen Sie eine Instanz von`FontSettings` Klasse und nutzen Sie die`SetFontsFolder` Methode, um das Verzeichnis anzugeben, das die Schriftarten enthält. Ersetzen`"Fonts"` mit dem Namen des eigentlichen Schriftartenverzeichnisses.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Schritt 3: Laden Sie das Dokument mit den Schriftarteinstellungen
 Benutzen Sie die`LoadOptions` Klasse zum Angeben von Schriftarteinstellungen in der`FontSettings` Möglichkeit. Dann nutzen Sie die`Document` Klasse, um das Dokument mit diesen Optionen zu laden.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Beispielquellcode für Set Fonts Folder mit Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Abschluss
Herzlichen Glückwunsch! Sie wissen jetzt, wie Sie das Schriftartenverzeichnis in Aspose.Words für .NET festlegen. Mit dieser Funktion können Sie die Verfügbarkeit der in Ihrem Dokument verwendeten Schriftarten und die Konsistenz bei der Anzeige von Schriftarten sicherstellen.
