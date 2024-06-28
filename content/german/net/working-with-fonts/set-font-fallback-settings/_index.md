---
title: Legen Sie die Schriftart-Fallback-Einstellungen fest
linktitle: Legen Sie die Schriftart-Fallback-Einstellungen fest
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Schriftart-Fallback-Einstellungen in Aspose.Words für .NET einrichten. Diese umfassende Anleitung stellt sicher, dass alle Zeichen in Ihren Dokumenten korrekt angezeigt werden.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-font-fallback-settings/
---

Bei der Arbeit mit Dokumenten, die unterschiedliche Textelemente enthalten, beispielsweise verschiedene Sprachen oder Sonderzeichen, ist es wichtig, sicherzustellen, dass diese Elemente korrekt angezeigt werden. Aspose.Words für .NET bietet eine leistungsstarke Funktion namens „Font-Fallback-Einstellungen“, die beim Definieren von Regeln zum Ersetzen von Schriftarten hilft, wenn die Originalschriftart bestimmte Zeichen nicht unterstützt. In dieser Anleitung erfahren Sie in einer Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET Schriftart-Fallback-Einstellungen einrichten.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Grundkenntnisse in C#: Vertrautheit mit der Programmiersprache C# und dem .NET Framework.
-  Aspose.Words für .NET: Von herunterladen und installieren[Download-Link](https://releases.aspose.com/words/net/).
- Entwicklungsumgebung: Ein Setup wie Visual Studio zum Schreiben und Ausführen Ihres Codes.
-  Beispieldokument: Halten Sie ein Beispieldokument bereit (z. B.`Rendering.docx`) bereit zum Testen.
- Schriftart-Fallback-Regeln XML: Bereiten Sie eine XML-Datei vor, die die Schriftart-Fallback-Regeln definiert.

## Namespaces importieren

Um Aspose.Words verwenden zu können, müssen Sie die erforderlichen Namespaces importieren. Dies ermöglicht den Zugriff auf verschiedene Klassen und Methoden, die für die Dokumentenverarbeitung erforderlich sind.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using System;
```

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

Definieren Sie zunächst das Verzeichnis, in dem Ihr Dokument gespeichert ist. Dies ist für das Auffinden und Bearbeiten Ihres Dokuments unerlässlich.

```csharp
// Der Pfad zum Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument

 Laden Sie Ihr Dokument in ein Aspose.Words`Document` Objekt. Mit diesem Schritt können Sie programmgesteuert mit dem Dokument arbeiten.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 3: Schriftarteinstellungen konfigurieren

 Erstelle eine neue`FontSettings` Objekt und laden Sie die Schriftart-Fallback-Einstellungen aus einer XML-Datei. Diese XML-Datei enthält die Regeln für den Font-Fallback.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
```

## Schritt 4: Schriftarteinstellungen auf das Dokument anwenden

 Weisen Sie die konfigurierten zu`FontSettings`zum Dokument. Dadurch wird sichergestellt, dass beim Rendern des Dokuments die Schriftart-Fallback-Regeln angewendet werden.

```csharp
doc.FontSettings = fontSettings;
```

## Schritt 5: Speichern Sie das Dokument

Speichern Sie abschließend das Dokument. Die Schriftart-Fallback-Einstellungen werden während des Speichervorgangs verwendet, um eine ordnungsgemäße Schriftartersetzung sicherzustellen.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## XML-Datei: Font-Fallback-Regeln

Hier ist ein Beispiel dafür, wie Ihre XML-Datei, die die Schriftart-Fallback-Regeln definiert, aussehen sollte:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<FontFallbackSettings xmlns="Aspose.Words">
    <FallbackTable>
        <Rule Ranges="0B80-0BFF" FallbackFonts="Vijaya"/>
        <Rule Ranges="1F300-1F64F" FallbackFonts="Segoe UI Emoji, Segoe UI Symbol"/>
        <Rule Ranges="2000-206F, 2070-209F, 20B9" FallbackFonts="Arial" />
        <Rule Ranges="3040-309F" FallbackFonts="MS Gothic" BaseFonts="Times New Roman"/>
        <Rule Ranges="3040-309F" FallbackFonts="MS Mincho"/>
        <Rule FallbackFonts="Arial Unicode MS"/>
    </FallbackTable>
</FontFallbackSettings>
```

## Abschluss

Wenn Sie diese Schritte befolgen, können Sie Schriftart-Fallback-Einstellungen in Aspose.Words für .NET effektiv einrichten und verwenden. Dadurch wird sichergestellt, dass Ihre Dokumente alle Zeichen korrekt anzeigen, auch wenn die Originalschriftart bestimmte Zeichen nicht unterstützt. Durch die Implementierung dieser Einstellungen wird die Qualität und Lesbarkeit Ihrer Dokumente erheblich verbessert.

## FAQs

### F1: Was ist Font-Fallback?

Font Fallback ist eine Funktion, die das Ersetzen von Schriftarten ermöglicht, wenn die ursprüngliche Schriftart bestimmte Zeichen nicht unterstützt, und so die ordnungsgemäße Anzeige aller Textelemente gewährleistet.

### F2: Kann ich mehrere Fallback-Schriftarten angeben?

Ja, Sie können in den XML-Regeln mehrere Fallback-Schriftarten angeben. Aspose.Words überprüft jede Schriftart in der angegebenen Reihenfolge, bis eine Schriftart gefunden wird, die das Zeichen unterstützt.

### F3: Wo kann ich Aspose.Words für .NET herunterladen?

 Sie können es hier herunterladen[Aspose-Downloadseite](https://releases.aspose.com/words/net/).

### F4: Wie erstelle ich die XML-Datei für Schriftart-Fallback-Regeln?

Die XML-Datei kann mit jedem Texteditor erstellt werden. Es sollte der Struktur folgen, die im Beispiel in diesem Tutorial gezeigt wird.

### F5: Gibt es Unterstützung für Aspose.Words?

 Ja, Unterstützung finden Sie auf der[Aspose.Words-Supportforum](https://forum.aspose.com/c/words/8).