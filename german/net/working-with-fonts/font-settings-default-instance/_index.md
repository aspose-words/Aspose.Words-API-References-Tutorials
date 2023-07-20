---
title: Standardinstanz der Schriftarteinstellungen
linktitle: Standardinstanz der Schriftarteinstellungen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET Standardschriftarteinstellungen in einem Word-Dokument konfigurieren.
type: docs
weight: 10
url: /de/net/working-with-fonts/font-settings-default-instance/
---

In diesem Tutorial führen wir Sie durch die Konfiguration der Standardschrifteinstellungen in einem Word-Dokument mithilfe der Aspose.Words-Bibliothek für .NET. Mit den Standardschriftarteinstellungen können Sie die Schriftartquellen angeben, die beim Laden und Rendern von Dokumenten verwendet werden. Wir begleiten Sie Schritt für Schritt, um Ihnen zu helfen, den Code in Ihrem .NET-Projekt zu verstehen und zu implementieren.

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

## Schritt 2: Konfigurieren Sie die Standardschrifteinstellungen
 Als Nächstes erstellen wir eine Instanz von`FontSettings` verwenden`FontSettings.DefaultInstance`, und dann geben wir die Schriftartquellen an, die beim Laden und Rendern von Dokumenten verwendet werden. In diesem Beispiel verwenden wir eine Systemschriftquelle und eine Ordnerschriftquelle.

```csharp
// Konfigurieren Sie die Standardschriftarteinstellungen
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Schritt 3: Dokument mit Schriftarteinstellungen hochladen
 Jetzt laden wir das Dokument mit`LoadOptions` und Angabe der zu verwendenden Schriftarteinstellungen.

```csharp
// Laden Sie das Dokument mit den Schriftarteinstellungen
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Beispielquellcode für die Standardinstanz der Schriftarteinstellungen mit Aspose.Words für .NET 
```csharp

//Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man mit Aspose.Words für .NET Standardschriftarteinstellungen in einem Word-Dokument konfiguriert. Durch die Angabe der Schriftartquellen, die beim Laden und Rendern von Dokumenten verwendet werden, können Sie das Erscheinungsbild von Schriftarten in Ihren Dokumenten steuern. Nutzen Sie diese Funktion gerne, um die Schriftarteinstellungen in Ihren Projekten anzupassen.

### FAQs

#### F: Wie kann ich die Standardschriftart in Aspose.Words festlegen?

 A: Um die Standardschriftart in Aspose.Words festzulegen, können Sie die verwenden`FontSettings` Klasse und die`DefaultFontName` Eigenschaft, die den Namen der gewünschten Schriftart angibt.

#### F: Kann ich die Standardschriftgröße in Aspose.Words angeben?

 A: Ja, Sie können die Standardschriftgröße in Aspose.Words mithilfe von festlegen`DefaultFontSize` Eigentum der`FontSettings` Klasse. Sie können die gewünschte Punktgröße einstellen.

#### F: Ist es möglich, die Standardschriftfarbe in Aspose.Words festzulegen?

 A: Ja, Sie können die Standardschriftfarbe in Aspose.Words mithilfe von festlegen`DefaultColor` Eigentum der`FontSettings` Klasse. Sie können die Farbe mithilfe von RGB-Werten oder vordefinierten Namen angeben.

#### F: Gilt die Standardschriftart für alle Dokumente?

A: Ja, die Standardschriftarteinstellungen gelten für alle in Aspose.Words erstellten oder bearbeiteten Dokumente, es sei denn, für ein einzelnes Dokument werden spezielle Einstellungen festgelegt.