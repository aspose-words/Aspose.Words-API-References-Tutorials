---
title: Liste der verfügbaren Schriftarten abrufen
linktitle: Liste der verfügbaren Schriftarten abrufen
second_title: Aspose.Words für .NET API-Referenz
description: In diesem Tutorial erfahren Sie, wie Sie die Liste der in Aspose.Words für .NET verfügbaren Schriftarten abrufen.
type: docs
weight: 10
url: /de/net/working-with-fonts/get-list-of-available-fonts/
---
In diesem Tutorial erklären wir, wie Sie die Liste der in Aspose.Words für .NET verfügbaren Schriftarten erhalten. Die Liste der verfügbaren Schriftarten zeigt Ihnen, welche Schriftarten Sie in Ihren Dokumenten verwenden können. Wir begleiten Sie Schritt für Schritt, um Ihnen zu helfen, den Code in Ihrem .NET-Projekt zu verstehen und zu implementieren.

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

## Schritt 2: Schriftartquellen konfigurieren
 Als Nächstes erstellen wir eine Instanz von`FontSettings` und rufen Sie die vorhandenen Schriftartquellen mithilfe von ab`GetFontsSources()` Methode. Wir werden auch eine neue Schriftartenquelle hinzufügen, indem wir einen Ordner mit Schriftarten angeben.

```csharp
// Konfigurieren Sie Schriftartquellen
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Fügen Sie eine neue Schriftartquelle hinzu
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## Schritt 3: Rufen Sie die Liste der verfügbaren Schriftarten ab
 Jetzt durchsuchen wir die verfügbaren Schriftarten mit`GetAvailableFonts()` Methode für die erste aktualisierte Schriftartquelle.

```csharp
// Rufen Sie die Liste der verfügbaren Schriftarten ab
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Beispielquellcode für „Liste der verfügbaren Schriftarten abrufen“ mit Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Fügen Sie eine neue Ordnerquelle hinzu, die Aspose.Words anweist, den folgenden Ordner nach Schriftarten zu durchsuchen.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// Fügen Sie den benutzerdefinierten Ordner, der unsere Schriftarten enthält, zur Liste der vorhandenen Schriftartquellen hinzu.
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
In diesem Tutorial haben wir gesehen, wie man die Liste der in Aspose.Words für .NET verfügbaren Schriftarten erhält. Dadurch erfahren Sie, welche Schriftarten Sie in Ihren Dokumenten verwenden können. Nutzen Sie diese Funktion gerne, um geeignete Schriftarten für Ihre Bedürfnisse auszuwählen.

### FAQs

#### F: Wie kann ich die Liste der in Aspose.Words verfügbaren Schriftarten abrufen?

 A: Um die Liste der in Aspose.Words verfügbaren Schriftarten abzurufen, können Sie die verwenden`FontsProvider` Klasse und die`GetAvailableFonts` Methode. Diese Methode gibt eine Liste aller auf Ihrem System installierten Schriftarten zurück.

#### F: Kann ich die Liste der verfügbaren Schriftarten in Aspose.Words nach bestimmten Kriterien filtern?

A: Ja, Sie können die Liste der in Aspose.Words verfügbaren Schriftarten nach bestimmten Kriterien filtern. Beispielsweise können Sie Schriftarten nach Familie, Stil oder Sprache filtern.

#### F: Wie kann ich die Liste der verfügbaren Schriftarten in meinen Word-Dokumenten verwenden?

 A: Um die Liste der in Ihren Word-Dokumenten verfügbaren Schriftarten zu verwenden, können Sie die Liste durchsuchen und mithilfe der Methoden und Eigenschaften von die entsprechenden Schriftarten auswählen`FontSettings` Klasse in Aspose.Words.