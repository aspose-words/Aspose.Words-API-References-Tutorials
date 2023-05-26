---
title: Legen Sie das Schriftartenordnersystem und den benutzerdefinierten Ordner fest
linktitle: Legen Sie das Schriftartenordnersystem und den benutzerdefinierten Ordner fest
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Festlegen von System- und benutzerdefinierten Schriftartenordnern beim Rendern eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen von Systemschriftartenordnern und eines benutzerdefinierten Ordners beim Rendern eines Dokuments mit Aspose.Words für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie mehrere Schriftartenordner angeben, einschließlich des Systemordners und eines benutzerdefinierten Ordners, die Sie beim Rendern Ihrer Dokumente mit Aspose.Words für .NET verwenden können.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes gerendertes Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das zu rendernde Dokument
 Anschließend können Sie das zu rendernde Dokument mit laden`Document` Klasse. Stellen Sie sicher, dass Sie den richtigen Dokumentpfad angeben.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 3: Legen Sie Systemordner und benutzerdefinierte Schriftartenordner fest
 Jetzt können Sie mit dem Systemschriftartenordner und einen benutzerdefinierten Ordner festlegen`FontSettings` Klasse und die`SetFontsSources()` Methode. Zuerst müssen Sie die Liste der umgebungsabhängigen Schriftartquellen mithilfe von abrufen`GetFontsSources()` und speichern Sie es in einer Liste. Anschließend können Sie eine neue Instanz von erstellen`FolderFontSource`Geben Sie den Pfad zum benutzerdefinierten Ordner an, der Ihre Schriftarten enthält. Fügen Sie diese Instanz zur Liste der vorhandenen Schriftartquellen hinzu. Endlich verwenden`SetFontsSources()` um die Schriftartquellen mit der neuen Liste zu aktualisieren.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Schritt 4: Schriftarteinstellungen anwenden
 Als nächstes müssen Sie die Schriftarteinstellungen mithilfe von auf Ihr Dokument anwenden`FontSettings` Eigentum der`Document` Klasse.

```csharp
doc.FontSettings = fontSettings;
```

## Schritt 5: Speichern Sie das gerenderte Dokument
Abschließend können Sie das gerenderte Dokument in einer Datei speichern

   Verwendung der`Save()` Methode der`Document` Klasse. Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen angeben.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Beispielquellcode für „Fonts-Ordnersystem und benutzerdefinierten Ordner festlegen“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	// Rufen Sie das Array umgebungsabhängiger Schriftartquellen ab, die standardmäßig durchsucht werden.
	// Dies enthält beispielsweise eine „Windows\Fonts\“-Quelle auf einem Windows-Computer.
	// Wir fügen dieses Array einer neuen Liste hinzu, um das Hinzufügen oder Entfernen von Schriftarteinträgen erheblich zu vereinfachen.
	List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
	// Fügen Sie eine neue Ordnerquelle hinzu, die Aspose.Words anweist, den folgenden Ordner nach Schriftarten zu durchsuchen.
	FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
	// Fügen Sie den benutzerdefinierten Ordner, der unsere Schriftarten enthält, zur Liste der vorhandenen Schriftartquellen hinzu.
	fontSources.Add(folderFontSource);
	FontSourceBase[] updatedFontSources = fontSources.ToArray();
	fontSettings.SetFontsSources(updatedFontSources);
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man beim Rendern eines Dokuments mit Aspose.Words für .NET Systemschriftartenordner und einen benutzerdefinierten Ordner einrichtet. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie ganz einfach mehrere Schriftartenordner angeben, einschließlich des Systemordners und eines benutzerdefinierten Ordners, die Sie beim Rendern Ihrer Dokumente verwenden möchten. Aspose.Words bietet eine leistungsstarke und flexible API für die Arbeit mit Schriftarten in Ihren Dokumenten. Mit diesem Wissen können Sie die beim Rendern Ihrer Dokumente verwendeten Schriftartquellen steuern und an Ihre spezifischen Anforderungen anpassen.