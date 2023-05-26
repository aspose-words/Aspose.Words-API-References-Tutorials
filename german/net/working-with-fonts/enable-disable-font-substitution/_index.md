---
title: Aktivieren Sie „Schriftartersetzung deaktivieren“.
linktitle: Aktivieren Sie „Schriftartersetzung deaktivieren“.
second_title: Aspose.Words für .NET API-Referenz
description: In diesem Tutorial erfahren Sie, wie Sie die Schriftartersetzung in einem Word-Dokument mit Aspose.Words für .NET aktivieren oder deaktivieren.
type: docs
weight: 10
url: /de/net/working-with-fonts/enable-disable-font-substitution/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie die Schriftartersetzung in einem Word-Dokument aktivieren oder deaktivieren, wenn Sie es mit der Aspose.Words-Bibliothek für .NET rendern. Durch Aktivieren oder Deaktivieren der Schriftartenersetzung können Sie steuern, ob fehlende Schriftarten automatisch durch eine Standardschriftart ersetzt werden. Wir begleiten Sie Schritt für Schritt, um Ihnen zu helfen, den Code in Ihrem .NET-Projekt zu verstehen und zu implementieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET
- Ein Word-Dokument, das Sie mit oder ohne Schriftartersetzung rendern möchten

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments festlegen. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument hoch und konfigurieren Sie die Schriftarteinstellungen
 Als Nächstes laden wir das Word-Dokument, das Sie rendern möchten, und erstellen eine Instanz davon`FontSettings` Klasse, um die Schriftarteinstellungen zu verwalten. Wir legen die Standardschriftartüberschreibung fest, indem wir den Schriftartnamen in angeben`DefaultFontName` und deaktivieren Sie das Überschreiben von Schriftartinformationen mit`Enabled` einstellen`false`.

```csharp
//Laden Sie das Dokument
Document doc = new Document(dataDir + "Rendering.docx");

// Konfigurieren Sie die Schriftarteinstellungen
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// Wenden Sie die Schriftarteinstellungen auf das Dokument an
doc.FontSettings = fontSettings;
```

## Schritt 3: Speichern Sie das gerenderte Dokument
Abschließend speichern wir das gerenderte Dokument, wobei die definierten Einstellungen zum Überschreiben von Schriftarten berücksichtigt werden.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Beispielquellcode für „Enable Disable Font Substitution“ mit Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man die Schriftartersetzung in einem Word-Dokument beim Rendern mit Aspose.Words für .NET aktiviert oder deaktiviert. Durch die Steuerung der Schriftartersetzung können Sie beeinflussen, wie fehlende Schriftarten in Ihren gerenderten Dokumenten behandelt werden. Zögern Sie nicht, diese Funktion zu nutzen, um die Verwaltung von Schriftarten in Ihren Word-Dokumenten anzupassen.