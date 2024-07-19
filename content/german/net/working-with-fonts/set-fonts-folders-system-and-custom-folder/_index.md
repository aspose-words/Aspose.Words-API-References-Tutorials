---
title: Legen Sie die Schriftartenordner System und benutzerdefinierte Ordner fest
linktitle: Legen Sie die Schriftartenordner System und benutzerdefinierte Ordner fest
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Einrichten von System- und benutzerdefinierten Schriftordnern beim Rendern eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen von Systemschriftartordnern und einem benutzerdefinierten Ordner beim Rendern eines Dokuments mit Aspose.Words für .NET. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie mehrere Schriftartenordner angeben, darunter den Systemordner und einen benutzerdefinierten Ordner, die beim Rendern Ihrer Dokumente mit Aspose.Words für .NET verwendet werden können.

## Schritt 1: Dokumentverzeichnis festlegen
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes, gerendertes Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das zu rendernde Dokument
 Anschließend können Sie das zu rendernde Dokument laden mit dem`Document` Klasse. Achten Sie darauf, den richtigen Dokumentpfad anzugeben.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 3: System- und benutzerdefinierte Schriftartordner festlegen
 Jetzt können Sie System-Schriftartenordner und einen benutzerdefinierten Ordner festlegen, indem Sie`FontSettings` Klasse und die`SetFontsSources()` Methode. Zuerst müssen Sie die Liste der umgebungsabhängigen Schriftquellen abrufen mit`GetFontsSources()` und speichern Sie es in einer Liste. Dann können Sie eine neue Instanz von`FolderFontSource` Geben Sie den Pfad zum benutzerdefinierten Ordner an, der Ihre Schriftarten enthält. Fügen Sie diese Instanz zur Liste der vorhandenen Schriftartquellen hinzu. Verwenden Sie abschließend`SetFontsSources()` um die Schriftartquellen mit der neuen Liste zu aktualisieren.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Schritt 4: Schrifteinstellungen anwenden
 Als nächstes müssen Sie die Schrifteinstellungen auf Ihr Dokument anwenden, indem Sie`FontSettings` Eigentum der`Document` Klasse.

```csharp
doc.FontSettings = fontSettings;
```

## Schritt 5: Speichern des gerenderten Dokuments
Abschließend können Sie das gerenderte Dokument in einer Datei speichern, indem Sie

   Verwendung der`Save()` Methode der`Document` Klasse. Achten Sie darauf, den richtigen Pfad und Dateinamen anzugeben.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Beispielquellcode für Set Fonts Folders System And Custom Folder mit Aspose.Words für .NET 

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Rufen Sie das Array der umgebungsabhängigen Schriftartquellen ab, nach denen standardmäßig gesucht wird.
// Auf einem Windows-Rechner enthält dies beispielsweise eine „Windows\Fonts\“-Quelle.
// Wir fügen dieses Array einer neuen Liste hinzu, um das Hinzufügen oder Entfernen von Schriftarteinträgen wesentlich zu vereinfachen.
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Fügen Sie eine neue Ordnerquelle hinzu, die Aspose.Words anweist, im folgenden Ordner nach Schriftarten zu suchen.
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
// Fügen Sie den benutzerdefinierten Ordner, der unsere Schriftarten enthält, zur Liste der vorhandenen Schriftartenquellen hinzu.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man beim Rendern eines Dokuments mit Aspose.Words für .NET Systemschriftordner und einen benutzerdefinierten Ordner einstellt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie problemlos mehrere Schriftartordner angeben, darunter den Systemordner und einen benutzerdefinierten Ordner, die beim Rendern Ihrer Dokumente verwendet werden sollen. Aspose.Words bietet eine leistungsstarke und flexible API für die Textverarbeitung mit Schriftarten in Ihren Dokumenten. Mit diesem Wissen können Sie die beim Rendern Ihrer Dokumente verwendeten Schriftartquellen steuern und an Ihre spezifischen Anforderungen anpassen.

### Häufig gestellte Fragen

#### F: Wie kann ich Systemschriftordner in Aspose.Words festlegen?

A: Um Systemschriftordner in Aspose.Words einzurichten, müssen Sie nichts tun. Aspose.Words verwendet automatisch die auf Ihrem Betriebssystem installierten Systemschriftarten.

#### F: Wie kann ich in Aspose.Words benutzerdefinierte Schriftartordner festlegen?

 A: Um die benutzerdefinierten Schriftartordner in Aspose.Words festzulegen, können Sie die`SetFontsFolders` Methode der`Fonts` Klasse, die die Speicherorte der benutzerdefinierten Schriftartordner angibt.

#### F: Kann ich in Aspose.Words mehrere benutzerdefinierte Schriftartordner angeben?

 A: Ja, Sie können mehrere benutzerdefinierte Schriftartordner in Aspose.Words angeben, indem Sie`SetFontsFolders` Methode der`Fonts` Klasse mit einer Liste von Ordnerspeicherorten.

#### F: Wie kann ich die in Aspose.Words definierten Schriftartordner überprüfen?

 Um die in Aspose.Words definierten Schriftordner zu überprüfen, können Sie den`GetFolders` Methode der`Fonts` Klasse, um die Liste der konfigurierten Schriftartordner abzurufen.

#### F: Haben benutzerdefinierte Ordnerschriftarten in Aspose.Words Vorrang vor Systemschriftarten?

A: Ja, benutzerdefinierte Ordnerschriftarten haben in Aspose.Words Vorrang vor Systemschriftarten. Wenn eine Schriftart sowohl in benutzerdefinierten Ordnern als auch in Systemschriftarten vorhanden ist, verwendet Aspose.Words die Version aus dem benutzerdefinierten Ordner.