---
title: Erhalten Sie Substitution ohne Suffixe
linktitle: Erhalten Sie Substitution ohne Suffixe
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Schriftartersetzung ohne Suffixe in Aspose.Words für .NET verwalten. Befolgen Sie unsere Schritt-für-Schritt-Anleitung, um sicherzustellen, dass Ihre Dokumente jedes Mal perfekt aussehen.
type: docs
weight: 10
url: /de/net/working-with-fonts/get-substitution-without-suffixes/
---

Willkommen zu diesem umfassenden Leitfaden zum Verwalten der Schriftartersetzung mit Aspose.Words für .NET. Wenn Sie schon einmal damit zu kämpfen hatten, dass Schriftarten in Ihren Dokumenten nicht korrekt angezeigt wurden, sind Sie hier genau richtig. Dieses Tutorial führt Sie Schritt für Schritt durch den effizienten Umgang mit der Schriftartersetzung ohne Suffixe. Lass uns anfangen!

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse in C#: Wenn Sie die C#-Programmierung verstehen, können Sie die Schritte leichter befolgen und implementieren.
-  Aspose.Words für .NET-Bibliothek: Laden Sie die Bibliothek von herunter und installieren Sie sie[Download-Link](https://releases.aspose.com/words/net/).
- Entwicklungsumgebung: Richten Sie eine Entwicklungsumgebung wie Visual Studio ein, um Ihren Code zu schreiben und auszuführen.
-  Beispieldokument: Ein Beispieldokument (z. B.`Rendering.docx`), mit denen Sie während dieses Tutorials arbeiten können.

## Namespaces importieren

Zuerst müssen wir die notwendigen Namespaces importieren, um auf die von Aspose.Words bereitgestellten Klassen und Methoden zuzugreifen.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using Aspose.Words.WarningInfo;
using System.Collections.Generic;
```

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

Geben Sie zunächst das Verzeichnis an, in dem sich Ihr Dokument befindet. Dies hilft beim Auffinden des Dokuments, an dem Sie arbeiten möchten.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Richten Sie den Substitutionswarnungshandler ein

Als Nächstes müssen wir einen Warnhandler einrichten, der uns benachrichtigt, wenn während der Dokumentverarbeitung eine Schriftartersetzung auftritt. Dies ist entscheidend für das Erkennen und Behandeln von Schriftartproblemen.

```csharp
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
Document doc = new Document(dataDir + "Rendering.docx");
doc.WarningCallback = substitutionWarningHandler;
```

## Schritt 3: Benutzerdefinierte Schriftartquellen hinzufügen

In diesem Schritt fügen wir benutzerdefinierte Schriftartquellen hinzu, um sicherzustellen, dass Aspose.Words die richtigen Schriftarten finden und verwenden kann. Dies ist besonders nützlich, wenn Sie bestimmte Schriftarten in benutzerdefinierten Verzeichnissen gespeichert haben.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());

FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

In diesem Code:
-  Wir rufen die aktuellen Schriftartquellen ab und fügen eine neue hinzu`FolderFontSource` Verweis auf unser benutzerdefiniertes Schriftartenverzeichnis (`C:\\MyFonts\\`).
- Anschließend aktualisieren wir die Schriftartquellen mit dieser neuen Liste.

## Schritt 4: Speichern Sie das Dokument

Speichern Sie abschließend das Dokument, nachdem Sie die Einstellungen für die Schriftartersetzung angewendet haben. Für dieses Tutorial speichern wir es als PDF.

```csharp
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

## Schritt 5: Erstellen Sie die Warnungshandlerklasse

Um Warnungen effektiv zu verarbeiten, erstellen Sie eine benutzerdefinierte Klasse, die Folgendes implementiert`IWarningCallback` Schnittstelle. Diese Klasse erfasst und protokolliert alle Warnungen zur Schriftartersetzung.

```csharp
public class DocumentSubstitutionWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

In dieser Klasse:
-  Der`Warning` Die Methode erfasst Warnungen im Zusammenhang mit der Schriftartersetzung.
-  Der`FontWarnings` Die Sammlung speichert diese Warnungen zur weiteren Überprüfung oder Protokollierung.

## Abschluss

Sie beherrschen jetzt den Prozess der Schriftartersetzung ohne Suffixe mit Aspose.Words für .NET. Dieses Wissen stellt sicher, dass Ihre Dokumente unabhängig von den im System verfügbaren Schriftarten ihr beabsichtigtes Aussehen behalten. Experimentieren Sie weiter mit verschiedenen Einstellungen und Quellen, um die Leistungsfähigkeit von Aspose.Words voll auszuschöpfen.

## FAQs

### F1: Wie kann ich Schriftarten aus mehreren benutzerdefinierten Verzeichnissen verwenden?

 Sie können mehrere hinzufügen`FolderFontSource` Instanzen zum`fontSources` Listen Sie die Schriftartquellen auf und aktualisieren Sie sie entsprechend.

### F2: Wo kann ich eine kostenlose Testversion von Aspose.Words für .NET herunterladen?

 Sie können eine kostenlose Testversion herunterladen[Aspose kostenlose Testseite](https://releases.aspose.com/).

###  F3: Kann ich mit mehreren Arten von Warnungen umgehen?`IWarningCallback`?

 Ja das`IWarningCallback` Mit der Benutzeroberfläche können Sie verschiedene Arten von Warnungen verarbeiten, nicht nur das Ersetzen von Schriftarten.

### F4: Wo erhalte ich Unterstützung für Aspose.Words?

 Für Unterstützung besuchen Sie die[Aspose.Words-Supportforum](https://forum.aspose.com/c/words/8).

### F5: Ist es möglich, eine temporäre Lizenz zu erwerben?

 Ja, Sie können eine temporäre Lizenz von erhalten[temporäre Lizenzseite](https://purchase.aspose.com/temporary-license/).