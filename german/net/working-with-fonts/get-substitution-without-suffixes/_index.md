---
title: Erhalten Sie Substitution ohne Suffixe
linktitle: Erhalten Sie Substitution ohne Suffixe
second_title: Aspose.Words für .NET API-Referenz
description: In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET suffixlose Überschreibungen in einem Word-Dokument erhalten.
type: docs
weight: 10
url: /de/net/working-with-fonts/get-substitution-without-suffixes/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mithilfe der Aspose.Words-Bibliothek für .NET die Überschreibungen ohne Suffixe in ein Word-Dokument abrufen. Ersetzungen ohne Suffixe werden zur Lösung von Schriftartersetzungsproblemen beim Anzeigen oder Drucken von Dokumenten verwendet. Wir begleiten Sie Schritt für Schritt, um Ihnen zu helfen, den Code in Ihrem .NET-Projekt zu verstehen und zu implementieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments festlegen. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und konfigurieren Sie Ersetzungen ohne Suffixe
 Als nächstes laden wir das Dokument mit`Document` Klasse und konfigurieren Sie suffixlose Ersetzungen mithilfe der`DocumentSubstitutionWarnings` Klasse. Wir werden auch eine Schriftartenquelle hinzufügen, indem wir einen Ordner angeben, der die Schriftarten enthält.

```csharp
//Laden Sie das Dokument und konfigurieren Sie Ersetzungen ohne Suffixe
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## Schritt 3: Speichern Sie das Dokument
Abschließend speichern wir das Dokument mit den angewendeten No-Suffix-Überschreibungen.

```csharp
// Speichern Sie das Dokument
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Beispielquellcode für Get Substitution Without Suffixes mit Aspose.Words für .NET 
```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man mit Aspose.Words für .NET die Überschreibungen ohne Suffixe in ein Word-Dokument erhält. Ersetzungen ohne Suffixe sind nützlich, um Probleme mit der Schriftartersetzung zu lösen. Nutzen Sie diese Funktion gerne, um die Anzeige und den Ausdruck Ihrer Dokumente zu verbessern.
