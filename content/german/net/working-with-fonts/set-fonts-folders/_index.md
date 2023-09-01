---
title: Legen Sie Schriftartenordner fest
linktitle: Legen Sie Schriftartenordner fest
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Festlegen von Schriftartenordnern beim Rendern eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-fonts-folders/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen von Schriftartenordnern beim Rendern eines Dokuments mit Aspose.Words für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie die Schriftartenordner angeben, die beim Rendern Ihrer Dokumente mit Aspose.Words für .NET verwendet werden sollen.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes gerendertes Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Schriftartquellen festlegen
 Anschließend können Sie die Schriftartquellen mithilfe von festlegen`FontSettings.DefaultInstance` Klasse und die`SetFontsSources()` Methode. In diesem Beispiel verwenden wir sowohl eine Systemschriftquelle als auch eine benutzerdefinierte Ordnerschriftquelle. Stellen Sie sicher, dass Sie den Pfad zum Ordner für benutzerdefinierte Schriftarten entsprechend Ihren Anforderungen anpassen.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
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
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Beispielquellcode für „Fonts-Ordner festlegen“ mit Aspose.Words für .NET 
```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man Schriftartenordner beim Rendern eines Dokuments mit Aspose.Words für .NET festlegt. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie ganz einfach die Schriftartquellen angeben, die Sie beim Rendern Ihrer Dokumente verwenden möchten. Aspose.Words bietet eine leistungsstarke und flexible API für die Textverarbeitung mit Schriftarten in Ihren Dokumenten. Mit diesem Wissen können Sie die beim Rendern Ihrer Dokumente verwendeten Schriftartquellen steuern und an Ihre spezifischen Anforderungen anpassen.

### FAQs

#### F: Wie kann ich mit Aspose.Words Schriftartenordner in einem Word-Dokument konfigurieren?

A: Um Schriftartenordner in einem Word-Dokument mit Aspose.Words zu konfigurieren, können Sie die API verwenden, um benutzerdefinierte Schriftartenordner anzugeben, die beim Generieren oder Bearbeiten des Dokuments verwendet werden sollen. Dadurch kann Word die für die korrekte Darstellung erforderlichen Schriftarten finden.

#### F: Ist es möglich, mit Aspose.Words benutzerdefinierte Schriftarten zu einem Word-Dokument hinzuzufügen?

A: Ja, mit Aspose.Words können Sie benutzerdefinierte Schriftarten zu einem Word-Dokument hinzufügen. Mit der API können Sie bestimmte Schriftarten in Ihr Dokument einbetten und so sicherstellen, dass diese korrekt angezeigt werden, auch wenn die Schriftarten nicht auf dem System des Endbenutzers installiert sind.

#### F: Was passiert, wenn in einem Word-Dokument erforderliche Schriftarten fehlen?

A: Wenn in einem Word-Dokument erforderliche Schriftarten fehlen, kann Aspose.Words dieses Problem erkennen und Ihnen Optionen zur Behebung anbieten. Sie können fehlende Schriftarten durch alternative Schriftarten ersetzen oder fehlende Schriftarten in das Dokument aufnehmen, um eine korrekte Anzeige sicherzustellen.

#### F: Wie kann ich mit Aspose.Words benutzerdefinierte Schriftarten aus einem Word-Dokument entfernen?

A: Um benutzerdefinierte Schriftarten aus einem Word-Dokument mit Aspose.Words zu entfernen, können Sie die API verwenden, um das Dokument zu bereinigen und benutzerdefinierte Schriftarten zu entfernen, die nicht mehr benötigt werden. Dadurch wird die Dateigröße reduziert und die Schriftartenverwaltung einfacher.

#### F: Ist es wichtig, Schriftartenordner in einem Word-Dokument zu konfigurieren?

A: Ja, es ist wichtig, Schriftartenordner in einem Word-Dokument zu konfigurieren, um sicherzustellen, dass die verwendeten Schriftarten korrekt angezeigt werden. Durch die Angabe benutzerdefinierter Schriftartenordner für die Verwendung mit Aspose.Words stellen Sie sicher, dass die erforderlichen Schriftarten für die korrekte Darstellung von Word-Dokumenten verfügbar sind.