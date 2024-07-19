---
title: Schriftformatierung festlegen
linktitle: Schriftformatierung festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Schriftformatierung in Word-Dokumenten festlegen und attraktive Dokumente erstellen.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-font-formatting/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET die Schriftformatierung in einem Word-Dokument festlegen. Sie lernen, wie Sie Stile wie Fettdruck, Farbe, Kursivschrift, Schriftart, Größe, Abstand und Unterstreichung anwenden.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Elemente verfügen:
- Gute Kenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET

## Schritt 1: Dokumentverzeichnis festlegen
Legen Sie zunächst den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments fest. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen und Formatieren des Dokuments
 Erstellen Sie eine Instanz des`Document` Klasse und die`DocumentBuilder` Klasse, um das Dokument zu erstellen. Verwenden Sie die`Font` Eigentum der`DocumentBuilder` um auf die Schriftformatierungseigenschaften zuzugreifen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font. Bold = true;
font.Color = Color.DarkBlue;
font. Italic = true;
font.Name = "Arial";
font.Size = 24;
font. Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nicely formatted string.");
```

## Schritt 3: Speichern Sie das Dokument
 Verwenden Sie die`Save`Methode, um das Dokument mit der angewendeten Schriftformatierung zu speichern. Ersetzen Sie`"WorkingWithFonts.SetFontFormatting.docx"` durch den gewünschten Dateinamen.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");
```

### Beispielquellcode zum Festlegen der Schriftformatierung mit Aspose.Words für .NET 
```csharp

// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Bold = true;
font.Color = Color.DarkBlue;
font.Italic = true;
font.Name = "Arial";
font.Size = 24;
font.Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nice formatted string.");
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");

```

## Abschluss
Herzlichen Glückwunsch! Sie wissen jetzt, wie Sie mit Aspose.Words für .NET die Schriftformatierung in einem Word-Dokument festlegen. Sie können weitere Optionen zur Schriftformatierung erkunden und personalisierte und attraktive Word-Dokumente erstellen.

### Häufig gestellte Fragen

#### F: Wie kann ich mit Aspose.Words den Fettstil auf eine Schriftart in einem Word-Dokument anwenden?

A: Um den Fettstil mit Aspose.Words auf eine Schriftart in einem Word-Dokument anzuwenden, können Sie die API verwenden, um zur gewünschten Schriftart zu navigieren und ihren Stil auf „fett“ einzustellen. Dadurch wird der Fettstil auf die angegebene Schriftart angewendet.

#### F: Ist es mit Aspose.Words möglich, einen bestimmten Textteil in einem Word-Dokument kursiv zu formatieren?

A: Ja, mit Aspose.Words können Sie den Kursivstil auf einen bestimmten Textteil in einem Word-Dokument anwenden. Sie können die API verwenden, um den gewünschten Textbereich auszuwählen und seinen Stil auf „kursiv“ einzustellen.

#### F: Wie kann ich mit Aspose.Words die Schriftfarbe in einem Word-Dokument ändern?

A: Um die Schriftfarbe in einem Word-Dokument mit Aspose.Words zu ändern, können Sie über die API auf die gewünschte Schriftart zugreifen und ihre Farbe auf die gewünschte Farbe einstellen. Dadurch wird die Schriftfarbe im Dokument geändert.

#### F: Ist es möglich, die Schriftgröße in einem Word-Dokument mit Aspose.Words zu ändern?

A: Ja, Sie können die Schriftgröße in einem Word-Dokument mit Aspose.Words ändern. Über die API können Sie auf die Schriftart zugreifen und ihre Größe je nach Bedarf in Punkten oder Skalenpunkten festlegen.

#### F: Kann ich auf denselben Text in einem Word-Dokument mehrere Schriftformate anwenden, etwa Fett und Kursiv?

A: Ja, mit Aspose.Words können Sie mehrere Schriftformate, wie Fett und Kursiv, auf denselben Text in einem Word-Dokument anwenden. Sie können die API verwenden, um die gewünschten Schriftstile für verschiedene Teile des Textes festzulegen.