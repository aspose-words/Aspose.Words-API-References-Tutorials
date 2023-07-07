---
title: Legen Sie Schriftartenordner mit Priorität fest
linktitle: Legen Sie Schriftartenordner mit Priorität fest
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Festlegen von Schriftartenordnern mit Priorität beim Rendern eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-fonts-folders-with-priority/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen von Schriftartenordnern mit Priorität beim Rendern eines Dokuments mit Aspose.Words für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie beim Rendern Ihrer Dokumente mit Aspose.Words für .NET mehrere Schriftartenordner mit benutzerdefinierter Suchpriorität angeben.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes gerendertes Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Schriftartenordner mit Priorität festlegen
 Anschließend können Sie mithilfe von die Schriftartenordner mit Priorität festlegen`FontSettings` Klasse und die`SetFontsSources()`Methode. Sie können mithilfe von Instanzen von mehrere Schriftartquellen angeben`SystemFontSource` Und`FolderFontSource`. In diesem Beispiel haben wir zwei Schriftartenquellen definiert: die Standard-Systemschriftartquelle und einen benutzerdefinierten Schriftartenordner mit der Priorität 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## Schritt 3: Laden Sie das zu rendernde Dokument
 Jetzt können Sie das zu rendernde Dokument mit laden`Document` Klasse. Stellen Sie sicher, dass Sie den richtigen Dokumentpfad angeben.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 4: Speichern Sie das gerenderte Dokument
 Schließlich können Sie das gerenderte Dokument mithilfe von in einer Datei speichern`Save()` Methode der`Document` Klasse. Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen angeben.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Beispielquellcode für „Fonts-Ordner mit Priorität festlegen“ mit Aspose.Words für .NET 
```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man beim Rendern eines Dokuments mit Aspose.Words für .NET Schriftartenordner mit Priorität festlegt. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie beim Rendern Ihrer Dokumente ganz einfach mehrere Schriftartenordner mit benutzerdefinierter Suchpriorität angeben. Aspose.Words bietet eine leistungsstarke und flexible API für die Arbeit mit Schriftarten in Ihren Dokumenten. Mit diesem Wissen können Sie die beim Rendern Ihrer Dokumente verwendeten Schriftartquellen steuern und an Ihre spezifischen Anforderungen anpassen.

### FAQs

#### F: Wie kann ich in Aspose.Words Schriftartenordner mit Priorität festlegen?

 A: Um Schriftartenordner in Aspose.Words mit Priorität festzulegen, können Sie die verwenden`SetFontsFoldersWithPriority` Methode der`Fonts` Klasse, indem Sie die Speicherorte der Schriftartenordner und deren Prioritätsreihenfolge angeben.

#### F: Was passiert, wenn eine Schriftart in mehreren Ordnern mit unterschiedlicher Priorität vorhanden ist?

A: Wenn eine Schriftart in mehreren Ordnern mit unterschiedlicher Priorität vorhanden ist, verwendet Aspose.Words bei der Verarbeitung von Dokumenten die Version aus dem Ordner mit der höchsten Priorität.

#### F: Kann ich in Aspose.Words mehrere Schriftartenordner mit derselben Priorität angeben?

A: Ja, Sie können in Aspose.Words mehrere Schriftartenordner mit derselben Priorität angeben. Aspose.Words berücksichtigt sie alle mit gleicher Priorität bei der Suche nach Schriftarten in Ihren Dokumenten.

#### F: Wie kann ich die in Aspose.Words mit Priorität definierten Schriftartenordner überprüfen?

 A: Um die in Aspose.Words mit Priorität definierten Schriftartenordner zu überprüfen, können Sie die verwenden`GetFolders` Methode der`Fonts` Klasse, um die Liste der konfigurierten Schriftartenordner einschließlich ihrer Prioritätsreihenfolge abzurufen.

#### F: Welchen Nutzen hat es, in Aspose.Words Schriftartenordner mit Priorität festzulegen?

A: Wenn Sie in Aspose.Words Schriftartenordner mit Priorität festlegen, können Sie die Suchreihenfolge von Schriftarten in Ihren Word-Dokumenten steuern. Dadurch können Sie sicherstellen, dass die gewünschten Schriftarten verwendet werden, und unerwünschte Probleme beim Ersetzen von Schriftarten vermeiden.