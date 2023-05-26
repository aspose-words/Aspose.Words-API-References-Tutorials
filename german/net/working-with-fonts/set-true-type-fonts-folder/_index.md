---
title: Legen Sie den Ordner für True-Type-Schriftarten fest
linktitle: Legen Sie den Ordner für True-Type-Schriftarten fest
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Festlegen des Ordners für True-Type-Schriftarten beim Rendern eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-true-type-fonts-folder/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen des Ordners für True-Type-Schriftarten beim Rendern eines Dokuments mit Aspose.Words für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie einen benutzerdefinierten Ordner mit True Type-Schriftarten angeben, der beim Rendern Ihrer Dokumente mit Aspose.Words für .NET verwendet werden soll.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes gerendertes Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das zu rendernde Dokument
 Als Nächstes müssen Sie das zu rendernde Dokument mit laden`Document` Klasse. Stellen Sie sicher, dass Sie den richtigen Dokumentpfad angeben.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 3: Legen Sie den Ordner für True-Type-Schriftarten fest
 Jetzt können Sie den Ordner der True-Type-Schriftarten angeben, die beim Rendern verwendet werden sollen, indem Sie eine Instanz davon erstellen`FontSettings` Klasse und Verwendung der`SetFontsFolder()` Methode zum Festlegen des Schriftartenordners. Sie können einen benutzerdefinierten Ordner angeben, der Ihre True Type-Schriftarten enthält. Der zweite Parameter für`SetFontsFolder()` Gibt an, ob Sie auch Unterordner des angegebenen Ordners durchsuchen möchten.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## Schritt 4: Speichern Sie das gerenderte Dokument
 Schließlich können Sie das gerenderte Dokument mithilfe von in einer Datei speichern`Save()` Methode der`Document` Klasse. Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen angeben.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Beispielquellcode für „Ordner für True Type-Schriftarten festlegen“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	// Beachten Sie, dass diese Einstellung alle Standardschriftquellen überschreibt, die standardmäßig durchsucht werden. Jetzt wird nur noch nach diesen Ordnern gesucht
	// Schriftarten beim Rendern oder Einbetten von Schriftarten. Um eine zusätzliche Schriftartquelle hinzuzufügen und gleichzeitig die Schriftartquellen des Systems beizubehalten, verwenden Sie sowohl FontSettings.GetFontSources als auch
	// Stattdessen FontSettings.SetFontSources
	fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
	// Legen Sie die Schriftarteinstellungen fest
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man beim Rendern eines Dokuments mit Aspose.Words für .NET den Ordner für True-Type-Schriftarten festlegt. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie ganz einfach einen benutzerdefinierten Ordner mit True Type-Schriftarten angeben, die Sie beim Rendern Ihrer Dokumente verwenden möchten. Aspose.Words bietet eine leistungsstarke und flexible API für die Arbeit mit Schriftarten in Ihren Dokumenten. Mit diesem Wissen können Sie die beim Rendern Ihrer Dokumente verwendeten Schriftarten steuern und an Ihre spezifischen Anforderungen anpassen.