---
title: Hervorhebungszeichen für die Schriftart festlegen
linktitle: Hervorhebungszeichen für die Schriftart festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Hervorhebungsstil der Schrift in einem Word-Dokument festlegen.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-font-emphasis-mark/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET den Schrifthervorhebungsstil in einem Word-Dokument festlegen. Die Schrifthervorhebung wird verwendet, um bestimmte Wörter oder Ausdrücke im Text hervorzuheben.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Elemente verfügen:
- Gute Kenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET

## Schritt 1: Dokumentverzeichnis festlegen
Legen Sie zunächst den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments fest. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen und Anpassen des Dokuments
 Erstellen Sie eine Instanz des`Document` Klasse und eine zugehörige`DocumentBuilder` um den Dokumentinhalt zu erstellen. Verwenden Sie die`Font.EmphasisMark` Eigenschaft, um den Schrifthervorhebungsstil auf`EmphasisMark.UnderSolidCircle` . Dann verwenden Sie die`Write` Und`Writeln` Methoden der`DocumentBuilder` um Text mit der angegebenen Schrifthervorhebung hinzuzufügen.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## Schritt 3: Speichern Sie das Dokument
 Speichern Sie das Dokument mit dem`Save` Methode der`Document` mit dem entsprechenden Pfad und Dateinamen.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Beispielquellcode zum Festlegen von Schriftarthervorhebungszeichen mit Aspose.Words für .NET 

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET den Hervorhebungsstil der Schrift in einem Word-Dokument festlegen. Experimentieren Sie mit verschiedenen Hervorhebungsstilen und verwenden Sie diese Funktion, um Wörter oder Ausdrücke in Ihren Dokumenten hervorzuheben.

### Häufig gestellte Fragen

#### F: Wie kann ich mit Aspose.Words einer bestimmten Schriftart in einem Word-Dokument Akzentzeichen hinzufügen?

A: Um mit Aspose.Words einer bestimmten Schriftart in einem Word-Dokument Akzentzeichen hinzuzufügen, können Sie die API verwenden, um zur gewünschten Schriftart zu navigieren und die entsprechenden Akzentzeichen anzuwenden. Dadurch werden dem Text Akzentzeichen mit der ausgewählten Schriftart hinzugefügt.

#### F: Ist es mit Aspose.Words möglich, den Stil der Akzentzeichen in einem Word-Dokument zu ändern?

A: Ja, mit Aspose.Words können Sie den Stil von Akzentzeichen in einem Word-Dokument ändern. Mit der API können Sie Stileigenschaften wie Farbe, Größe, Linientyp usw. anpassen, um das Erscheinungsbild von Akzentzeichen anzupassen.

#### F: Wie kann ich mit Aspose.Words alle Akzentzeichen aus einem Word-Dokument entfernen?

A: Um alle Akzentzeichen aus einem Word-Dokument mit Aspose.Words zu entfernen, können Sie die API verwenden, um das Dokument zu durchsuchen, vorhandene Akzentzeichen zu erkennen und diese mit den entsprechenden Methoden zu entfernen. Dadurch werden alle Hervorhebungszeichen aus dem Dokument entfernt.

#### F: Kann ich einem bestimmten Textteil in einem Word-Dokument Akzentzeichen hinzufügen?

A: Ja, Sie können mit Aspose.Words einem bestimmten Textteil in einem Word-Dokument Akzentzeichen hinzufügen. Sie können mithilfe der API den gewünschten Textbereich auswählen und diesem Textteil entsprechende Hervorhebungszeichen hinzufügen.

#### F: Können die Akzentzeichen meinen Bedürfnissen entsprechend angepasst werden?

A: Ja, Akzentzeichen können mit Aspose.Words an Ihre Bedürfnisse angepasst werden. Sie können die Stileigenschaften von Akzentzeichen wie Farbe, Größe, Linientyp und mehr an Ihre Formatierungseinstellungen anpassen.