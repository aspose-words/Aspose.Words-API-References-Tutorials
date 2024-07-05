---
title: Liste der verfügbaren Schriftarten abrufen
linktitle: Liste der verfügbaren Schriftarten abrufen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in diesem Tutorial, wie Sie die Liste der in Aspose.Words für .NET verfügbaren Schriftarten erhalten.
type: docs
weight: 10
url: /de/net/working-with-fonts/get-list-of-available-fonts/
---
In diesem Tutorial erklären wir, wie Sie die Liste der in Aspose.Words für .NET verfügbaren Schriftarten abrufen. Die Liste der verfügbaren Schriftarten informiert Sie darüber, welche Schriftarten Sie in Ihren Dokumenten verwenden können. Wir führen Sie Schritt für Schritt durch, damit Sie den Code in Ihrem .NET-Projekt verstehen und implementieren können.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Elemente verfügen:
- Gute Kenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET

## Schritt 1: Dokumentverzeichnis festlegen
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments setzen. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Schriftartquellen konfigurieren
 Als nächstes erstellen wir eine Instanz von`FontSettings` und holen Sie sich die bestehenden Fontquellen mit dem`GetFontsSources()` Methode. Wir werden auch eine neue Schriftartquelle hinzufügen, indem wir einen Ordner mit Schriftarten angeben.

```csharp
// Konfigurieren von Schriftartquellen
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Hinzufügen einer neuen Schriftartquelle
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## Schritt 3: Liste der verfügbaren Schriftarten abrufen
 Nun durchsuchen wir die verfügbaren Schriftarten mit dem`GetAvailableFonts()` Methode für die erste aktualisierte Schriftartquelle.

```csharp
// Liste der verfügbaren Schriftarten abrufen
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Beispielquellcode zum Abrufen einer Liste verfügbarer Schriftarten mit Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Fügen Sie eine neue Ordnerquelle hinzu, die Aspose.Words anweist, im folgenden Ordner nach Schriftarten zu suchen.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
//Fügen Sie den benutzerdefinierten Ordner, der unsere Schriftarten enthält, zur Liste der vorhandenen Schriftartquellen hinzu.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man die Liste der in Aspose.Words für .NET verfügbaren Schriftarten erhält. So erfahren Sie, welche Schriftarten Sie in Ihren Dokumenten verwenden können. Nutzen Sie diese Funktion, um geeignete Schriftarten für Ihre Anforderungen auszuwählen.

### Häufig gestellte Fragen

#### F: Wie kann ich die Liste der in Aspose.Words verfügbaren Schriftarten abrufen?

 A: Um die Liste der in Aspose.Words verfügbaren Schriftarten abzurufen, können Sie den`FontsProvider` Klasse und die`GetAvailableFonts` Methode. Diese Methode gibt eine Liste aller auf Ihrem System installierten Schriftarten zurück.

#### F: Kann ich die Liste der verfügbaren Schriftarten in Aspose.Words nach bestimmten Kriterien filtern?

A: Ja, Sie können die Liste der in Aspose.Words verfügbaren Schriftarten nach bestimmten Kriterien filtern. Sie können Schriftarten beispielsweise nach Familie, Stil oder Sprache filtern.

#### F: Wie kann ich die Liste der verfügbaren Schriftarten in meinen Word-Dokumenten verwenden?

A: Um die Liste der in Ihren Word-Dokumenten verfügbaren Schriftarten zu verwenden, können Sie die Liste durchsuchen und die entsprechenden Schriftarten mithilfe der Methoden und Eigenschaften des`FontSettings` Klasse in Aspose.Words.