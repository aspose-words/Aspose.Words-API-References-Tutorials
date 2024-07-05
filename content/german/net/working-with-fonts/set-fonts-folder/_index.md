---
title: Schriftartenordner festlegen
linktitle: Schriftartenordner festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie das Schriftartenverzeichnis in Aspose.Words für .NET festlegen und die Verfügbarkeit der in Ihren Dokumenten verwendeten Schriftarten sicherstellen.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-fonts-folder/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie das Schriftartenverzeichnis in Aspose.Words für .NET festlegen. Sie erfahren, wie Sie das Verzeichnis angeben, das die in Ihrem Word-Dokument verwendeten Schriftarten enthält.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Elemente verfügen:
- Gute Kenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET

## Schritt 1: Dokumentverzeichnis festlegen
Legen Sie zunächst den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments fest. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Schriftartenverzeichnis festlegen
 Erstellen Sie eine Instanz des`FontSettings` Klasse und verwenden Sie die`SetFontsFolder` Methode, um das Verzeichnis anzugeben, das die Schriftarten enthält. Ersetzen Sie`"Fonts"` durch den Namen des aktuellen Schriftartenverzeichnisses.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Schritt 3: Laden Sie das Dokument mit den Schrifteinstellungen
 Verwenden Sie die`LoadOptions` Klasse zum Festlegen von Schrifteinstellungen in der`FontSettings` Option. Verwenden Sie dann die`Document` Klasse, um das Dokument mit diesen Optionen zu laden.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Beispielquellcode für Set Fonts Folder mit Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Abschluss
Herzlichen Glückwunsch! Sie wissen jetzt, wie Sie das Schriftartenverzeichnis in Aspose.Words für .NET festlegen. Mit dieser Funktion können Sie die Verfügbarkeit der in Ihrem Dokument verwendeten Schriftarten sicherstellen und eine einheitliche Anzeige der Schriftarten gewährleisten.

### Häufig gestellte Fragen

#### F: Wie kann ich in Aspose.Words einen benutzerdefinierten Schriftartordner festlegen?

 A: Um einen benutzerdefinierten Schriftartenordner in Aspose.Words einzurichten, können Sie den`FontsFolder` Klasse und die`SetFontsFolders` Methode, die den Pfad zum Ordner angibt, der Ihre Schriftarten enthält.

#### F: Kann ich in Aspose.Words mehrere Schriftartenordner festlegen?

 A: Ja, Sie können mehrere Schriftartenordner in Aspose.Words festlegen, indem Sie den`SetFontsFolders` Methode mehrmals mit den Pfaden der verschiedenen Schriftartordner, die Sie verwenden möchten.

#### F: Was passiert, wenn eine im Dokument verwendete Schriftart nicht in den definierten Schriftartenordnern vorhanden ist?

A: Wenn eine im Dokument verwendete Schriftart nicht in den in Aspose.Words definierten Schriftartenordnern vorhanden ist, wird stattdessen eine Ersatzschriftart verwendet. Dadurch wird sichergestellt, dass der Text im Dokument immer korrekt angezeigt wird, auch wenn die Originalschriftart nicht verfügbar ist.

#### F: Haben in Aspose.Words definierte Schriftartenordner Vorrang vor auf dem System installierten Schriftarten?

A: Ja, in Aspose.Words definierte Schriftartenordner haben Vorrang vor auf dem System installierten Schriftarten. Das bedeutet, dass bei der Verarbeitung von Word-Dokumenten die Version im Schriftartenordner verwendet wird, wenn eine Schriftart mit demselben Namen sowohl in den definierten Schriftartenordnern als auch in den Systemschriftarten vorhanden ist.