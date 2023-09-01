---
title: Legen Sie mehrere Ordner für Schriftartenordner fest
linktitle: Legen Sie mehrere Ordner für Schriftartenordner fest
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Festlegen mehrerer Schriftartenordner beim Rendern eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen mehrerer Schriftartenordner beim Rendern eines Dokuments mit Aspose.Words für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie mehrere Schriftartenordner angeben, die beim Rendern Ihrer Dokumente mit Aspose.Words für .NET verwendet werden sollen.

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

## Schritt 3: Schriftartenordner festlegen
 Jetzt können Sie mit dem mehrere Schriftartenordner festlegen`FontSettings` Klasse und die`SetFontsFolders()` Methode. Sie können die Pfade zu den Schriftartenordnern angeben, die Sie in einem Array verwenden möchten. In diesem Beispiel haben wir zwei Schriftartenordner angegeben: „C:\MyFonts\" und "D:\Misc\Fonts\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## Schritt 4: Schriftarteinstellungen anwenden
 Als nächstes müssen Sie die Schriftarteinstellungen mithilfe von auf Ihr Dokument anwenden`FontSettings` Eigentum der`Document` Klasse.

```csharp
doc.FontSettings = fontSettings;
```

## Schritt 5: Speichern Sie das gerenderte Dokument
 Schließlich können Sie das gerenderte Dokument mithilfe von in einer Datei speichern`Save()` Methode der`Document` Klasse. Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen angeben.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Beispielquellcode für Set Fonts Folders Multiple Folders mit Aspose.Words für .NET 

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Beachten Sie, dass diese Einstellung alle Standardschriftquellen überschreibt, die standardmäßig durchsucht werden. Jetzt wird nur noch nach diesen Ordnern gesucht
// Schriftarten beim Rendern oder Einbetten von Schriftarten. Um eine zusätzliche Schriftartquelle hinzuzufügen und gleichzeitig die Schriftartquellen des Systems beizubehalten, verwenden Sie sowohl FontSettings.GetFontSources als auch
// Stattdessen FontSettings.SetFontSources.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man beim Rendern eines Dokuments mit Aspose.Words für .NET mehrere Schriftartenordner festlegt. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie ganz einfach mehrere Schriftartenordner angeben, die beim Rendern Ihrer Dokumente verwendet werden sollen. Aspose.Words bietet eine leistungsstarke und flexible API für die Textverarbeitung mit Schriftarten in Ihren Dokumenten. Mit diesem Wissen können Sie die beim Rendern Ihrer Dokumente verwendeten Schriftartquellen steuern und an Ihre spezifischen Anforderungen anpassen.

### FAQs

#### F: Wie kann ich in Aspose.Words mehrere Schriftartenordner festlegen?

 A: Um mehrere Schriftartenordner in Aspose.Words festzulegen, können Sie die verwenden`SetFontsFolders` Methode der`Fonts` Klasse, die eine Liste der Ordnerspeicherorte für benutzerdefinierte Schriftarten bereitstellt.

#### F: Hat das Festlegen mehrerer Schriftartenordner Auswirkungen auf alle mit Aspose.Words verarbeiteten Dokumente?

A: Ja, das Festlegen mehrerer Schriftartenordner wirkt sich auf alle mit Aspose.Words verarbeiteten Dokumente aus. Sobald Sie die Schriftartenordner definiert haben, verwendet Aspose.Words diese Speicherorte, um in allen Dokumenten nach Schriftarten zu suchen.

#### F: Wie viele Schriftartenordner kann ich in Aspose.Words definieren?

A: Sie können in Aspose.Words beliebig viele Schriftartenordner definieren. Es gibt keine bestimmte Begrenzung für die Anzahl der Schriftartenordner, die Sie definieren können.

#### F: Wie kann ich die in Aspose.Words definierten Schriftartenordner überprüfen?

 A: Um die in Aspose.Words definierten Schriftartenordner zu überprüfen, können Sie die verwenden`GetFolders` Methode der`Fonts` Klasse, um die Speicherorte der konfigurierten Schriftartenordner abzurufen.

#### F: Müssen Schriftartenordner bestimmte Schriftarten enthalten?

A: Ja, Schriftartenordner sollten die Schriftarten enthalten, die Sie in Ihren Word-Dokumenten verwenden möchten. Aspose.Words sucht bei der Verarbeitung von Dokumenten in den angegebenen Ordnern nach Schriftarten.