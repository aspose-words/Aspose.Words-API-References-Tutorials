---
title: Schriftartenersetzung aktivieren/deaktivieren
linktitle: Schriftartenersetzung aktivieren/deaktivieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: In diesem Tutorial erfahren Sie, wie Sie die Schriftartenersetzung in einem Word-Dokument mit Aspose.Words für .NET aktivieren oder deaktivieren.
type: docs
weight: 10
url: /de/net/working-with-fonts/enable-disable-font-substitution/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie die Schriftartenersetzung in einem Word-Dokument aktivieren oder deaktivieren, wenn Sie es mit der Aspose.Words-Bibliothek für .NET rendern. Durch Aktivieren oder Deaktivieren der Schriftartenersetzung können Sie steuern, ob fehlende Schriftarten automatisch durch eine Standardschriftart ersetzt werden. Wir führen Sie Schritt für Schritt durch, damit Sie den Code verstehen und in Ihrem .NET-Projekt implementieren können.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Elemente verfügen:
- Gute Kenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET
- Ein Word-Dokument, das Sie mit oder ohne Schriftartenersetzung rendern möchten

## Schritt 1: Dokumentverzeichnis festlegen
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments setzen. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument hoch und konfigurieren Sie die Schrifteinstellungen
 Als nächstes laden wir das Word-Dokument, das Sie rendern möchten, und erstellen eine Instanz des`FontSettings` Klasse zur Handhabung der Schrifteinstellungen. Wir legen die Standardschriftartüberschreibung fest, indem wir den Schriftnamen in`DefaultFontName` und deaktivieren Sie die Überschreibung der Schriftinformationen mit`Enabled` einstellen`false`.

```csharp
// Laden Sie das Dokument
Document doc = new Document(dataDir + "Rendering.docx");

// Konfigurieren der Schriftarteinstellungen
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// Anwenden der Schrifteinstellungen auf das Dokument
doc.FontSettings = fontSettings;
```

## Schritt 3: Speichern des gerenderten Dokuments
Abschließend speichern wir das gerenderte Dokument, wobei die definierten Einstellungen zur Schriftartüberschreibung berücksichtigt werden.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Beispielquellcode zum Aktivieren und Deaktivieren der Schriftartenersetzung mit Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man die Schriftartenersetzung in einem Word-Dokument aktiviert oder deaktiviert, wenn es mit Aspose.Words für .NET gerendert wird. Durch die Steuerung der Schriftartenersetzung können Sie beeinflussen, wie fehlende Schriftarten in Ihren gerenderten Dokumenten behandelt werden. Zögern Sie nicht, diese Funktion zu verwenden, um die Verwaltung der Schriftarten in Ihren Word-Dokumenten anzupassen.

### Häufig gestellte Fragen

#### F: Wie kann ich mit Aspose.Words die Schriftartenersetzung in einem Word-Dokument aktivieren?

A: Um die Schriftartenersetzung in einem Word-Dokument mit Aspose.Words zu aktivieren, können Sie die API verwenden, um Ersatzschriftarten anzugeben, die verwendet werden sollen, wenn erforderliche Schriftarten nicht verfügbar sind. Dadurch wird eine konsistente Textvisualisierung sichergestellt, auch ohne die Originalschriftarten.

#### F: Ist es möglich, die Schriftartenersetzung in einem Word-Dokument mit Aspose.Words zu deaktivieren?

A: Ja, mit Aspose.Words können Sie die Schriftartenersetzung in einem Word-Dokument deaktivieren. Mithilfe der API können Sie verhindern, dass Word erforderliche Schriftarten durch andere Schriftarten ersetzt, wodurch das ursprüngliche Erscheinungsbild des Textes erhalten bleibt.

#### F: Was passiert, wenn beim Ersetzen in einem Word-Dokument erforderliche Schriftarten fehlen?

A: Wenn beim Ersetzen in einem Word-Dokument erforderliche Schriftarten fehlen, kann Aspose.Words dieses Problem erkennen und Ihnen Optionen zur Behebung anbieten. Sie können fehlende Schriftarten durch alternative Schriftarten ersetzen oder fehlende Schriftarten in das Dokument aufnehmen, um eine korrekte Anzeige sicherzustellen.

#### F: Wie kann ich mit fehlenden Schriftarten umgehen, wenn ich sie in einem Word-Dokument mit Aspose.Words ersetze?

A: Um fehlende Schriftarten beim Ersetzen in einem Word-Dokument mit Aspose.Words zu behandeln, können Sie die API verwenden, um fehlende Schriftarten zu erkennen und Lösungsoptionen bereitzustellen. Sie können fehlende Schriftarten je nach Bedarf durch alternative Schriftarten ersetzen oder fehlende Schriftarten in das Dokument aufnehmen.

#### F: Ist es wichtig, die Schriftartenersetzung in einem Word-Dokument zu steuern?

A: Ja, es ist wichtig, die Schriftartenersetzung in einem Word-Dokument zu kontrollieren, um die visuelle Integrität des Textes zu wahren. Indem Sie Aspose.Words verwenden, um die Schriftartenersetzung zu aktivieren oder zu deaktivieren, können Sie sicherstellen, dass die erforderlichen Schriftarten verwendet werden und Probleme mit fehlenden oder ersetzten Schriftarten vermeiden.