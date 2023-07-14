---
title: Aktivieren Sie „Schriftartersetzung deaktivieren“.
linktitle: Aktivieren Sie „Schriftartersetzung deaktivieren“.
second_title: Aspose.Words-Dokumentverarbeitungs-API
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
// Laden Sie das Dokument
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

//Pfad zu Ihrem Dokumentenverzeichnis
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

### FAQs

#### F: Wie kann ich mit Aspose.Words die Schriftartersetzung in einem Word-Dokument aktivieren?

A: Um die Schriftartersetzung in einem Word-Dokument mit Aspose.Words zu aktivieren, können Sie die API verwenden, um Ersatzschriftarten anzugeben, die verwendet werden sollen, wenn erforderliche Schriftarten nicht verfügbar sind. Dadurch wird eine konsistente Textvisualisierung gewährleistet, auch ohne die Originalschriftarten.

#### F: Ist es möglich, die Schriftartersetzung in einem Word-Dokument mit Aspose.Words zu deaktivieren?

A: Ja, mit Aspose.Words können Sie die Schriftartersetzung in einem Word-Dokument deaktivieren. Mithilfe der API können Sie verhindern, dass Word erforderliche Schriftarten durch andere Schriftarten ersetzt, wodurch das ursprüngliche Erscheinungsbild des Textes erhalten bleibt.

#### F: Was passiert, wenn beim Ersetzen in einem Word-Dokument erforderliche Schriftarten fehlen?

A: Wenn beim Ersetzen in einem Word-Dokument erforderliche Schriftarten fehlen, kann Aspose.Words dieses Problem erkennen und Ihnen Optionen zur Behebung anbieten. Sie können fehlende Schriftarten durch alternative Schriftarten ersetzen oder fehlende Schriftarten in das Dokument aufnehmen, um eine korrekte Anzeige sicherzustellen.

#### F: Wie kann ich mit fehlenden Schriftarten umgehen, wenn ich sie in einem Word-Dokument mit Aspose.Words ersetze?

A: Um fehlende Schriftarten beim Ersetzen in einem Word-Dokument mit Aspose.Words zu behandeln, können Sie die API verwenden, um fehlende Schriftarten zu erkennen und Auflösungsoptionen bereitzustellen. Je nach Bedarf können Sie fehlende Schriftarten durch alternative Schriftarten ersetzen oder fehlende Schriftarten in das Dokument einfügen.

#### F: Ist es wichtig, die Schriftartersetzung in einem Word-Dokument zu steuern?

A: Ja, es ist wichtig, die Schriftartersetzung in einem Word-Dokument zu kontrollieren, um die visuelle Integrität des Textes zu wahren. Durch die Verwendung von Aspose.Words zum Aktivieren oder Deaktivieren der Schriftartenersetzung können Sie sicherstellen, dass die erforderlichen Schriftarten verwendet werden, und Probleme mit fehlenden oder ersetzten Schriftarten vermeiden.