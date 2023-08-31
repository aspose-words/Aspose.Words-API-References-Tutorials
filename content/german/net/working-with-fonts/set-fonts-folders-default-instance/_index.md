---
title: Legen Sie die Standardinstanz für Schriftartenordner fest
linktitle: Legen Sie die Standardinstanz für Schriftartenordner fest
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Festlegen des Standardschriftartordners beim Rendern eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-fonts-folders-default-instance/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen des Standardschriftartordners beim Rendern eines Dokuments mit Aspose.Words für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie den Standardschriftartordner festlegen, der beim Rendern Ihrer Dokumente mit Aspose.Words für .NET verwendet werden soll.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes gerendertes Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Legen Sie den Standard-Schriftartenordner fest
Anschließend können Sie den Standard-Schriftartenordner mithilfe von festlegen`FontSettings.DefaultInstance` Klasse und die`SetFontsFolder()` Methode. Geben Sie den Pfad zum Schriftartenordner an, den Sie als Standardordner verwenden möchten.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## Schritt 3: Laden Sie das zu rendernde Dokument
 Jetzt können Sie das zu rendernde Dokument mit laden`Document` Klasse. Stellen Sie sicher, dass Sie den richtigen Dokumentpfad angeben.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 4: Speichern Sie das gerenderte Dokument
 Schließlich können Sie das gerenderte Dokument mithilfe von in einer Datei speichern`Save()` Methode der`Document` Klasse. Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen angeben.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Beispielquellcode für „Set Fonts Folders Default Instance“ mit Aspose.Words für .NET 

```csharp
//Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man den Standardschriftartordner beim Rendern eines Dokuments mit Aspose.Words für .NET festlegt. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie ganz einfach angeben, welcher Schriftartenordner beim Rendern Ihrer Dokumente als Standardordner verwendet werden soll. Aspose.Words bietet eine leistungsstarke und flexible API für die Textverarbeitung mit Schriftarten in Ihren Dokumenten. Mit diesem Wissen können Sie die beim Rendern Ihrer Dokumente verwendeten Schriftartquellen steuern und an Ihre spezifischen Anforderungen anpassen.

### FAQs

#### F: Wie kann ich in Aspose.Words Standardschriftartenordner festlegen?

 A: Um Standardschriftartordner in Aspose.Words festzulegen, müssen Sie die verwenden`Fonts` Klasse und die`SetFontsFolders` Methode zum Angeben benutzerdefinierter Schriftartenordnerspeicherorte.

#### F: Hat das Festlegen von Standardschriftordnern Auswirkungen auf alle mit Aspose.Words verarbeiteten Word-Dokumente?

A: Ja, das Festlegen von Standardschriftartenordnern wirkt sich auf alle Word-Dokumente aus, die mit Aspose.Words verarbeitet werden. Sobald Sie die Standardschriftartenordner festgelegt haben, verwendet Aspose.Words diese Speicherorte, um in allen Dokumenten nach Schriftarten zu suchen.

#### F: Kann ich in Aspose.Words mehrere Standardschriftartenordner festlegen?

 A: Ja, Sie können in Aspose.Words mehrere Standardschriftartenordner festlegen. Sie müssen lediglich die Speicherorte der benutzerdefinierten Schriftartenordner mithilfe von angeben`SetFontsFolders` Methode der`Fonts` Klasse.

#### F: Wie kann ich die derzeit in Aspose.Words festgelegten Standard-Schriftartordner überprüfen?

 A: Um die derzeit in Aspose.Words definierten Standardschriftordner zu überprüfen, können Sie die verwenden`GetFolders` Methode der`Fonts` Klasse, um die Speicherorte der konfigurierten Schriftartenordner abzurufen.

#### F: Erlaubt mir das Festlegen von Standardschriftartenordnern die Verwendung benutzerdefinierter Schriftarten in meinen Word-Dokumenten?

A: Ja, indem Sie Standardschriftartordner festlegen, können Sie in Ihren Word-Dokumenten benutzerdefinierte Schriftarten verwenden. Sie müssen die Schriftarten nur in den angegebenen Ordnern ablegen und Aspose.Words verwendet sie beim Generieren oder Bearbeiten der Dokumente.