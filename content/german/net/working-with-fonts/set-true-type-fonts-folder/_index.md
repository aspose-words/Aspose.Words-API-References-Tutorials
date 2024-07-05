---
title: Ordner für TrueType-Schriftarten festlegen
linktitle: Ordner für TrueType-Schriftarten festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Einrichten des TrueType-Schriftartenordners beim Rendern eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-true-type-fonts-folder/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen des TrueType-Schriftartenordners beim Rendern eines Dokuments mit Aspose.Words für .NET. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie einen benutzerdefinierten Ordner mit TrueType-Schriftarten angeben, der beim Rendern Ihrer Dokumente mit Aspose.Words für .NET verwendet werden soll.

## Schritt 1: Dokumentverzeichnis festlegen
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes, gerendertes Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das zu rendernde Dokument
 Als nächstes müssen Sie das zu rendernde Dokument laden, indem Sie`Document` Klasse. Achten Sie darauf, den richtigen Dokumentpfad anzugeben.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 3: TrueType-Schriftartenordner festlegen
Jetzt können Sie den Ordner mit den TrueType-Schriftarten angeben, der beim Rendern verwendet werden soll, indem Sie eine Instanz des`FontSettings` Klasse und unter Verwendung der`SetFontsFolder()` Methode zum Festlegen des Schriftartenordners. Sie können einen benutzerdefinierten Ordner angeben, der Ihre True Type-Schriftarten enthält. Der zweite Parameter für`SetFontsFolder()` gibt an, ob auch Unterordner des angegebenen Ordners durchsucht werden sollen.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## Schritt 4: Speichern des gerenderten Dokuments
 Abschließend können Sie das gerenderte Dokument in einer Datei speichern mit dem`Save()` Methode der`Document` Klasse. Achten Sie darauf, den richtigen Pfad und Dateinamen anzugeben.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Beispielquellcode für „Set True Type Fonts Folder“ mit Aspose.Words für .NET 

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Beachten Sie, dass diese Einstellung alle standardmäßig durchsuchten Schriftartquellen überschreibt. Jetzt werden nur noch diese Ordner durchsucht
// Schriftarten beim Rendern oder Einbetten von Schriftarten. Um eine zusätzliche Schriftartquelle hinzuzufügen und gleichzeitig die Systemschriftartenquellen beizubehalten, verwenden Sie sowohl FontSettings.GetFontSources als auch
// FontSettings.SetFontSources stattdessen
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
// Festlegen der Schrifteinstellungen
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man den Ordner für TrueType-Schriftarten beim Rendern eines Dokuments mit Aspose.Words für .NET einstellt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie ganz einfach einen benutzerdefinierten Ordner mit TrueType-Schriftarten angeben, der beim Rendern Ihrer Dokumente verwendet werden soll. Aspose.Words bietet eine leistungsstarke und flexible API für die Textverarbeitung mit Schriftarten in Ihren Dokumenten. Mit diesem Wissen können Sie die beim Rendern Ihrer Dokumente verwendeten Schriftarten steuern und an Ihre spezifischen Anforderungen anpassen.

### Häufig gestellte Fragen

#### F: Wie kann ich den TrueType-Schriftartenordner in Aspose.Words konfigurieren?

 A: Um den TrueType-Schriftartenordner in Aspose.Words zu konfigurieren, können Sie den`SetTrueTypeFontsFolder` Methode der`Fonts` Klasse, die den Speicherort des Ordners angibt, der die TrueType-Schriftarten enthält.

#### F: Welche Schriftarten gelten als TrueType-Schriftarten?

A: TrueType-Schriftarten sind ein beliebtes Schriftformat. Sie werden häufig in Word-Dokumenten verwendet und haben die Dateierweiterung .ttf oder .ttc.

#### F: Kann ich in Aspose.Words mehrere TrueType-Schriftordner angeben?

A: Ja, Sie können mehrere TrueType-Schriftordner in Aspose.Words angeben, indem Sie`SetTrueTypeFontsFolder` Methode der`Fonts` Klasse mit einer Liste von Ordnerspeicherorten.

#### F: Wie kann ich den in Aspose.Words konfigurierten TrueType-Schriftartenordner überprüfen?

 A: Um den konfigurierten TrueType Fonts-Ordner in Aspose.Words zu überprüfen, können Sie den`GetTrueTypeFontsFolder` Methode der`Fonts` Klasse, um den Speicherort des konfigurierten TrueType-Schriftartenordners abzurufen.

#### F: Warum ist es wichtig, den TrueType-Schriftartenordner in Aspose.Words zu konfigurieren?

A: Das Einrichten des TrueType-Schriftartenordners in Aspose.Words ist wichtig, da es Aspose.Words dabei hilft, die bei der Verarbeitung von Word-Dokumenten benötigten Schriftarten zu finden. Dadurch wird eine einheitliche Formatierung und Darstellung von Dokumenten sichergestellt, auch über verschiedene Systeme hinweg.