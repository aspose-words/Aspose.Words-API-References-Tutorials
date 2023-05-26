---
title: Legen Sie die Schriftart-Fallback-Einstellungen fest
linktitle: Legen Sie die Schriftart-Fallback-Einstellungen fest
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie die Schriftartersetzungseinstellungen in Aspose.Words für .NET festlegen und die Schriftartenersetzung in Ihren Word-Dokumenten anpassen.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-font-fallback-settings/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Schriftartersetzungseinstellungen in einem Word-Dokument festlegen. Mit den Schriftartersetzungseinstellungen können Sie Ersatzschriftarten angeben, die verwendet werden sollen, wenn die angegebenen Schriftarten nicht verfügbar sind.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Legen Sie zunächst den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments fest. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie die Einstellungen für die Schriftartersetzung
 Erstellen Sie eine Instanz von`FontSettings` Klasse und nutzen Sie die`Load`Methode zum Laden von Einstellungen zum Überschreiben von Schriftarten aus einer XML-Datei. Die angegebene XML-Datei muss die zu verwendenden Schriftartersetzungsregeln enthalten.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font Fallback Rules.xml");
```

## Schritt 3: Wenden Sie die Einstellungen für die Schriftartersetzung an
 Ordnen Sie Schriftartersetzungseinstellungen dem Dokument zu, indem Sie sie dem Dokument zuweisen`FontSettings` Eigentum.

```csharp
doc.FontSettings = fontSettings;
```

## Schritt 4: Speichern Sie das Dokument
 Speichern Sie das Dokument mit`Save` Methode der`Document` mit dem entsprechenden Pfad und Dateinamen.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

### Beispielquellcode zum Festlegen von Font-Fallback-Einstellungen mit Aspose.Words für .NET 
```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET Schriftartersetzungseinstellungen in einem Word-Dokument festlegen. Experimentieren Sie mit verschiedenen Schriftartersetzungsregeln, um sicherzustellen, dass Ihr Dokument konsistent aussieht, auch wenn die angegebenen Schriftarten nicht verfügbar sind.
