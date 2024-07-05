---
title: Standardinstanz für Schriftartenordner festlegen
linktitle: Standardinstanz für Schriftartenordner festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Festlegen des Standardschriftordners beim Rendern eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-fonts-folders-default-instance/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen des Standardschriftordners beim Rendern eines Dokuments mit Aspose.Words für .NET. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie den Standardschriftordner festlegen, der beim Rendern Ihrer Dokumente mit Aspose.Words für .NET verwendet werden soll.

## Schritt 1: Dokumentverzeichnis festlegen
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes, gerendertes Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Standard-Schriftartenordner festlegen
 Anschließend können Sie den Standard-Schriftartenordner mit dem`FontSettings.DefaultInstance` Klasse und die`SetFontsFolder()`Methode. Geben Sie den Pfad zum Schriftartenordner an, den Sie als Standardordner verwenden möchten.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## Schritt 3: Laden Sie das zu rendernde Dokument
 Nun können Sie das zu rendernde Dokument laden mit dem`Document` Klasse. Achten Sie darauf, den richtigen Dokumentpfad anzugeben.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 4: Speichern des gerenderten Dokuments
 Abschließend können Sie das gerenderte Dokument in einer Datei speichern mit dem`Save()` Methode der`Document` Klasse. Achten Sie darauf, den richtigen Pfad und Dateinamen anzugeben.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Beispielquellcode für Set Fonts Folders Default Instance mit Aspose.Words für .NET 

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man den Standard-Schriftartenordner beim Rendern eines Dokuments mit Aspose.Words für .NET einstellt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie ganz einfach angeben, welcher Schriftartenordner beim Rendern Ihrer Dokumente als Standardordner verwendet werden soll. Aspose.Words bietet eine leistungsstarke und flexible API für die Textverarbeitung mit Schriftarten in Ihren Dokumenten. Mit diesem Wissen können Sie die beim Rendern Ihrer Dokumente verwendeten Schriftartenquellen steuern und an Ihre spezifischen Anforderungen anpassen.

### Häufig gestellte Fragen

#### F: Wie kann ich in Aspose.Words Standardschriftordner festlegen?

 A: Um Standard-Schriftordner in Aspose.Words festzulegen, müssen Sie den`Fonts` Klasse und die`SetFontsFolders` Methode zum Angeben benutzerdefinierter Speicherorte für Schriftartordner.

#### F: Hat das Festlegen von Standardschriftartordnern Auswirkungen auf alle mit Aspose.Words verarbeiteten Word-Dokumente?

A: Ja, das Festlegen von Standardschriftartenordnern wirkt sich auf alle Word-Dokumente aus, die mit Aspose.Words verarbeitet werden. Sobald Sie die Standardschriftartenordner festgelegt haben, verwendet Aspose.Words diese Speicherorte, um in allen Dokumenten nach Schriftarten zu suchen.

#### F: Kann ich in Aspose.Words mehrere Standardschriftordner festlegen?

 A: Ja, Sie können in Aspose.Words mehrere Standard-Schriftordner festlegen. Sie müssen lediglich die Speicherorte der benutzerdefinierten Schriftartordner mithilfe der`SetFontsFolders` Methode der`Fonts` Klasse.

#### F: Wie kann ich die aktuell in Aspose.Words festgelegten Standardschriftordner überprüfen?

 A: Um die derzeit in Aspose.Words definierten Standard-Schriftordner zu überprüfen, können Sie den`GetFolders` Methode der`Fonts` Klasse, um die Speicherorte der konfigurierten Schriftartordner abzurufen.

#### F: Kann ich durch das Festlegen von Standardschriftartordnern benutzerdefinierte Schriftarten in meinen Word-Dokumenten verwenden?

A: Ja, indem Sie Standard-Schriftartenordner festlegen, können Sie benutzerdefinierte Schriftarten in Ihren Word-Dokumenten verwenden. Sie müssen die Schriftarten nur in den angegebenen Ordnern platzieren und Aspose.Words verwendet sie beim Erstellen oder Bearbeiten der Dokumente.