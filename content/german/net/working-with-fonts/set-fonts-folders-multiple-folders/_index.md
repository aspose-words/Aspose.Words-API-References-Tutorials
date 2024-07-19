---
title: Schriftartenordner festlegen Mehrere Ordner
linktitle: Schriftartenordner festlegen Mehrere Ordner
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Festlegen mehrerer Schriftartordner beim Rendern eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen mehrerer Schriftartenordner beim Rendern eines Dokuments mit Aspose.Words für .NET. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie mehrere Schriftartenordner angeben, die beim Rendern Ihrer Dokumente mit Aspose.Words für .NET verwendet werden sollen.

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

## Schritt 3: Schriftartenordner festlegen
 Jetzt können Sie mehrere Schriftartenordner festlegen mit dem`FontSettings` Klasse und die`SetFontsFolders()` Methode. Sie können die Pfade zu den Schriftartordnern angeben, die Sie in einem Array verwenden möchten. In diesem Beispiel haben wir zwei Schriftartordner angegeben: "C:\MyFonts\" und "D:\Misc\Fonts\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## Schritt 4: Schrifteinstellungen anwenden
 Als nächstes müssen Sie die Schrifteinstellungen auf Ihr Dokument anwenden, indem Sie`FontSettings` Eigentum der`Document` Klasse.

```csharp
doc.FontSettings = fontSettings;
```

## Schritt 5: Speichern des gerenderten Dokuments
 Abschließend können Sie das gerenderte Dokument in einer Datei speichern mit dem`Save()` Methode der`Document` Klasse. Achten Sie darauf, den richtigen Pfad und Dateinamen anzugeben.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Beispielquellcode für Set Fonts Folders Multiple Folders mit Aspose.Words für .NET 

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Beachten Sie, dass diese Einstellung alle standardmäßig durchsuchten Schriftartquellen überschreibt. Jetzt werden nur noch diese Ordner durchsucht
// Schriftarten beim Rendern oder Einbetten von Schriftarten. Um eine zusätzliche Schriftartquelle hinzuzufügen und gleichzeitig die Systemschriftartenquellen beizubehalten, verwenden Sie sowohl FontSettings.GetFontSources als auch
// Verwenden Sie stattdessen FontSettings.SetFontSources.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie Sie beim Rendern eines Dokuments mit Aspose.Words für .NET mehrere Schriftartenordner festlegen. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie problemlos mehrere Schriftartenordner angeben, die beim Rendern Ihrer Dokumente verwendet werden sollen. Aspose.Words bietet eine leistungsstarke und flexible API für die Textverarbeitung mit Schriftarten in Ihren Dokumenten. Mit diesem Wissen können Sie die beim Rendern Ihrer Dokumente verwendeten Schriftartenquellen steuern und an Ihre spezifischen Anforderungen anpassen.

### Häufig gestellte Fragen

#### F: Wie kann ich in Aspose.Words mehrere Schriftartenordner festlegen?

 A: Um mehrere Schriftartenordner in Aspose.Words einzurichten, können Sie den`SetFontsFolders` Methode der`Fonts` Klasse, die eine Liste mit Speicherorten für benutzerdefinierte Schriftartordner bereitstellt.

#### F: Wirkt sich das Festlegen mehrerer Schriftartordner auf alle mit Aspose.Words verarbeiteten Dokumente aus?

A: Ja, das Festlegen mehrerer Schriftartenordner wirkt sich auf alle mit Aspose.Words verarbeiteten Dokumente aus. Sobald Sie die Schriftartenordner definiert haben, verwendet Aspose.Words diese Speicherorte, um in allen Dokumenten nach Schriftarten zu suchen.

#### F: Wie viele Schriftartenordner kann ich in Aspose.Words definieren?

A: Sie können in Aspose.Words so viele Schriftartenordner definieren, wie Sie benötigen. Es gibt keine bestimmte Begrenzung für die Anzahl der Schriftartenordner, die Sie definieren können.

#### F: Wie kann ich die in Aspose.Words definierten Schriftartordner überprüfen?

 A: Um die in Aspose.Words definierten Schriftordner zu überprüfen, können Sie den`GetFolders` Methode der`Fonts` Klasse, um die Speicherorte der konfigurierten Schriftartordner abzurufen.

#### F: Müssen Schriftartenordner bestimmte Schriftarten enthalten?

A: Ja, Schriftartenordner sollten die Schriftarten enthalten, die Sie in Ihren Word-Dokumenten verwenden möchten. Aspose.Words sucht bei der Verarbeitung von Dokumenten in den angegebenen Ordnern nach Schriftarten.