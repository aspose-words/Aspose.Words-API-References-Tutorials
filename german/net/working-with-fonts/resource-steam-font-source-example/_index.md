---
title: Beispiel für eine Quelle einer Steam-Schriftart
linktitle: Beispiel für eine Quelle einer Steam-Schriftart
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie die Resource Stream Font Source verwenden, um benutzerdefinierte Schriftarten in Aspose.Words für .NET zu laden.
type: docs
weight: 10
url: /de/net/working-with-fonts/resource-steam-font-source-example/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie Resource Flow Font Source mit Aspose.Words für .NET verwenden. Mit dieser Schriftartenquelle können Sie Schriftarten aus einem Ressourcenstrom laden, was nützlich sein kann, wenn Sie benutzerdefinierte Schriftarten in Ihre Anwendung integrieren möchten.

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

## Schritt 2: Dokument hochladen und Ressourcen-Stream-Schriftquelle festlegen
 Als nächstes laden wir das Dokument mit`Document` Klasse und legen Sie die Schriftartquelle des Ressourcenstroms mithilfe von fest`FontSettings.DefaultInstance.SetFontsSources()` Klasse. Dadurch kann Aspose.Words die Schriftarten im Ressourcenstream finden.

```csharp
// Laden Sie das Dokument und legen Sie die Schriftartquelle für den Ressourcenstrom fest
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{ new SystemFontSource(), new ResourceSteamFontSource() });
```

## Schritt 3: Speichern Sie das Dokument
Abschließend speichern wir das Dokument. Schriftarten werden aus dem angegebenen Ressourcenstrom geladen und in das Dokument eingebettet.

```csharp
// Speichern Sie das Dokument
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Beispielquellcode für Resource Steam Font Source Beispiel mit Aspose.Words für .NET 

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{ new SystemFontSource(), new ResourceSteamFontSource() });
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie Resource Flow Font Source mit Aspose.Words für .NET verwenden. Mit dieser Funktion können Sie Schriftarten aus einem Ressourcen-Feed laden, was nützlich ist, wenn Sie benutzerdefinierte Schriftarten in Ihre Dokumente einbetten möchten. Experimentieren Sie mit verschiedenen Schriftarten und erkunden Sie die Möglichkeiten, die Aspose.Words für die Schriftartenverwaltung bietet.
