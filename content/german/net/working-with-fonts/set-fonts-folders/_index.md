---
title: Schriftartenordner festlegen
linktitle: Schriftartenordner festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Einrichten von Schriftartordnern beim Rendern eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-fonts-folders/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen von Schriftartordnern beim Rendern eines Dokuments mit Aspose.Words für .NET. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie die Schriftartordner angeben, die beim Rendern Ihrer Dokumente mit Aspose.Words für .NET verwendet werden sollen.

## Schritt 1: Dokumentverzeichnis festlegen
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes, gerendertes Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Schriftartquellen festlegen
 Anschließend können Sie die Schriftartquellen über die`FontSettings.DefaultInstance` Klasse und die`SetFontsSources()` Methode. In diesem Beispiel verwenden wir sowohl eine Systemschriftartquelle als auch eine benutzerdefinierte Ordnerschriftartquelle. Passen Sie den Pfad zum benutzerdefinierten Schriftartenordner Ihren Anforderungen entsprechend an.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
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
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Beispielquellcode für Set Fonts Folders mit Aspose.Words für .NET 
```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man beim Rendern eines Dokuments mit Aspose.Words für .NET Schriftartenordner einstellt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie ganz einfach die Schriftartenquellen angeben, die beim Rendern Ihrer Dokumente verwendet werden sollen. Aspose.Words bietet eine leistungsstarke und flexible API für die Textverarbeitung mit Schriftarten in Ihren Dokumenten. Mit diesem Wissen können Sie die Schriftartenquellen steuern und an Ihre spezifischen Anforderungen anpassen, die beim Rendern Ihrer Dokumente verwendet werden.

### Häufig gestellte Fragen

#### F: Wie kann ich mit Aspose.Words Schriftartenordner in einem Word-Dokument konfigurieren?

A: Um Schriftartordner in einem Word-Dokument mit Aspose.Words zu konfigurieren, können Sie die API verwenden, um benutzerdefinierte Schriftartordner anzugeben, die beim Erstellen oder Bearbeiten des Dokuments verwendet werden sollen. Dadurch kann Word die für die korrekte Darstellung erforderlichen Schriftarten finden.

#### F: Ist es mit Aspose.Words möglich, einem Word-Dokument benutzerdefinierte Schriftarten hinzuzufügen?

A: Ja, mit Aspose.Words können Sie einem Word-Dokument benutzerdefinierte Schriftarten hinzufügen. Mit der API können Sie bestimmte Schriftarten in Ihr Dokument einbetten und so sicherstellen, dass sie korrekt angezeigt werden, auch wenn die Schriftarten nicht auf dem System des Endbenutzers installiert sind.

#### F: Was passiert, wenn in einem Word-Dokument erforderliche Schriftarten fehlen?

A: Wenn in einem Word-Dokument erforderliche Schriftarten fehlen, kann Aspose.Words dieses Problem erkennen und Ihnen Optionen zur Behebung anbieten. Sie können fehlende Schriftarten durch alternative Schriftarten ersetzen oder fehlende Schriftarten in das Dokument aufnehmen, um eine korrekte Anzeige sicherzustellen.

#### F: Wie kann ich mit Aspose.Words benutzerdefinierte Schriftarten aus einem Word-Dokument entfernen?

A: Um benutzerdefinierte Schriftarten mit Aspose.Words aus einem Word-Dokument zu entfernen, können Sie die API verwenden, um das Dokument zu bereinigen und benutzerdefinierte Schriftarten zu entfernen, die nicht mehr benötigt werden. Dadurch wird die Dateigröße reduziert und die Schriftartenverwaltung vereinfacht.

#### F: Ist es wichtig, Schriftartenordner in einem Word-Dokument zu konfigurieren?

A: Ja, es ist wichtig, Schriftartenordner in einem Word-Dokument zu konfigurieren, um sicherzustellen, dass die verwendeten Schriftarten korrekt angezeigt werden. Indem Sie benutzerdefinierte Schriftartenordner für die Verwendung mit Aspose.Words angeben, stellen Sie sicher, dass die erforderlichen Schriftarten verfügbar sind, um Word-Dokumente korrekt darzustellen.