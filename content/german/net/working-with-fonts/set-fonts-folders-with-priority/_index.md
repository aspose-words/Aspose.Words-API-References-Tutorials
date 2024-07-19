---
title: Legen Sie Schriftartenordner mit Priorität fest
linktitle: Legen Sie Schriftartenordner mit Priorität fest
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Festlegen der Priorität von Schriftartordnern beim Rendern eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-fonts-folders-with-priority/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess, um Schriftartordner mit Priorität festzulegen, wenn Sie ein Dokument mit Aspose.Words für .NET rendern. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie mehrere Schriftartordner mit benutzerdefinierter Suchpriorität angeben, wenn Sie Ihre Dokumente mit Aspose.Words für .NET rendern.

## Schritt 1: Dokumentverzeichnis festlegen
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes, gerendertes Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Schriftartenordner mit Priorität festlegen
 Anschließend können Sie die Schriftartenordner mit Priorität festlegen mit dem`FontSettings` Klasse und die`SetFontsSources()`Methode. Sie können mehrere Schriftartquellen angeben, indem Sie Instanzen von`SystemFontSource`Und`FolderFontSource`. In diesem Beispiel haben wir zwei Schriftartquellen definiert: die Standardsystemschriftartquelle und einen benutzerdefinierten Schriftartordner mit der Priorität 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## Schritt 3: Laden Sie das zu rendernde Dokument
 Nun können Sie das zu rendernde Dokument laden mit dem`Document` Klasse. Achten Sie darauf, den richtigen Dokumentpfad anzugeben.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 4: Speichern des gerenderten Dokuments
 Abschließend können Sie das gerenderte Dokument in einer Datei speichern mit dem`Save()` Methode der`Document` Klasse. Achten Sie darauf, den richtigen Pfad und Dateinamen anzugeben.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Beispielquellcode zum Festlegen von Schriftartordnern mit Priorität unter Verwendung von Aspose.Words für .NET 
```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man beim Rendern eines Dokuments mit Aspose.Words für .NET Schriftartenordner mit Priorität einstellt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie beim Rendern Ihrer Dokumente problemlos mehrere Schriftartenordner mit benutzerdefinierter Suchpriorität angeben. Aspose.Words bietet eine leistungsstarke und flexible API für die Textverarbeitung mit Schriftarten in Ihren Dokumenten. Mit diesem Wissen können Sie die beim Rendern Ihrer Dokumente verwendeten Schriftartenquellen steuern und an Ihre spezifischen Anforderungen anpassen.

### Häufig gestellte Fragen

#### F: Wie kann ich in Aspose.Words Schriftartordner mit Priorität festlegen?

 A: Um Schriftartenordner mit Priorität in Aspose.Words festzulegen, können Sie den`SetFontsFoldersWithPriority` Methode der`Fonts` Klasse, indem Sie die Speicherorte der Schriftartordner und deren Prioritätsreihenfolge angeben.

#### F: Was passiert, wenn eine Schriftart in mehreren Ordnern mit unterschiedlicher Priorität vorhanden ist?

A: Wenn eine Schriftart in mehreren Ordnern mit unterschiedlicher Priorität vorhanden ist, verwendet Aspose.Words bei der Verarbeitung von Dokumenten die Version aus dem Ordner mit der höchsten Priorität.

#### F: Kann ich in Aspose.Words mehrere Schriftartenordner mit derselben Priorität angeben?

A: Ja, Sie können in Aspose.Words mehrere Schriftartenordner mit derselben Priorität angeben. Aspose.Words berücksichtigt sie alle mit gleicher Priorität, wenn in Ihren Dokumenten nach Schriftarten gesucht wird.

#### F: Wie kann ich die in Aspose.Words mit Priorität definierten Schriftartordner überprüfen?

 A: Um die in Aspose.Words mit Priorität definierten Schriftordner zu überprüfen, können Sie den`GetFolders` Methode der`Fonts` Klasse, um die Liste der konfigurierten Schriftartordner einschließlich ihrer Prioritätsreihenfolge abzurufen.

#### F: Welchen Nutzen hat es, in Aspose.Words Schriftartordner mit Priorität zu versehen?

A: Indem Sie in Aspose.Words Schriftartordner mit Priorität festlegen, können Sie die Suchreihenfolge von Schriftarten in Ihren Word-Dokumenten steuern. Auf diese Weise können Sie sicherstellen, dass die gewünschten Schriftarten verwendet werden, und unerwünschte Probleme beim Ersetzen von Schriftarten vermeiden.